# Route Pada Laravel 8

Kita bisa melakukan routing di routes>web.php.
Routing ini berguna sebagai url.

sintaks tanpa controller

```
Route::get('/', function () {
    return view('welcome');
});
```

sintaks dengan menggunakan controller

```
Route::get('/', [HomeController::class, 'index']);

Route::get('/tasks', [TaskController::class, 'index']);
Route::get('/tasks/{id}', [TaskController::class, 'show']);
Route::post('/tasks', [TaskController::class, 'store']);
Route::patch('/tasks/{id}', [TaskController::class, 'update']);
Route::delete('/tasks/{id}', [HomeController::class, 'destroy']);
```

## Konsep routing

| HTTP VERB | CRUD           |
| --------- | -------------- |
| POST      | Create         |
| GET       | Read           |
| PUT       | Update/Replace |
| Patch     | Update/Modify  |
| DELETE    | Delete         |
