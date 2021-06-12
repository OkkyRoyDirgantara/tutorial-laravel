# Controller Pada Laravel 8

Pastikan controller sudah dipanggil pada route agar tidak mengalami error.

```
use App\Http\Controllers\HomeController;
```

cara sederhana menggunakan controller dengan menampilkan data yang berada pada view template blade.

```
public function index()
    {
        return view('welcome');
    }
```

contoh dengan menggunakan database.

```
https://github.com/OkkyRoyDirgantara/tutorial-laravel/blob/master/QUERYBUILDER.md
```
