# Query Builder Pada Laravel 8

Kita dapat melakukan mengambil data pada DBMS tanpa sintaks SQL dengan menggunakan Query Builder.
Dapat diketahui jika untuk melakukannya harus dilakukan di Controller dengan menambah sintaks diawal.

## Melakukan Query Builder

```
use Illuminate\Support\Facades\DB;
```

Dilanjutkan membuat method

```
public function store(Request $request){
    DB::table('tasks')->insert([
        'task' => $request->task,
        'user' => $request->user
    ]);
    return 'success';
}
```

## Menampilkan Seluruh Data

```
public function index(Request $request){
    if($request->search){
        return $this->taskList[$request->search];
    }
    $task = DB::table('tasks')->get();
    return $task;
}
```

## Menampilkan dengan search

```
public function index(Request $request){
    if($request->search){
        $tasks = DB::table('tasks')
        ->where('task', 'LIKE, "%$request->search%")
        ->get();
        return $tasks;
    }
    $tasks = DB::table('tasks')->get();
    return $tasks;
}
```

## Menampilkan Salah Satu Data Saja

kita dapat menggunakan method show untuk menampilkan salah satu data saja.
ubah parameter menjadi id pada route.

```
public function show(id){
    $task = DB::table('tasks')->where('id', $id)->first();
ddd($task);
}
```

## Mengubah Data dengan Query Builder

cara mengubah data dengan method update.
pastikan mengubah parameter route menjadi id pada method update.

```
public function update(Request $request, $id){
    $task = DB::table('tasks')->where('id', $id)->update([
        'task' => $request->task,
        'user' => $request->user
    ]);
    return 'success';
}
```
