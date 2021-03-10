# validation-laravel
validation laravel
```php
use Illuminate\Http\Request;
use Illuminate\Support\Facades\Validator;
```

```php
Route::get("/test",function(Request $request){
    $validator = Validator::make($request->input(), [
        'name' => 'required'
    ]);
    if ($validator->fails()) {
        return response()->json([
            'message' => $validator->errors()->all()
        ], 400);
    }

    return "success";

});
```
