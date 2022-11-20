
#querying-relations
You may try this (Check [Querying Relations](https://laravel.com/docs/master/eloquent-relationships#querying-relations) on `Laravel` website):

```php
$movies = Movie::whereHas('director', function($q) {
    $q->where('name', 'great');
})->get();
```

Also if you reverse the query like:

```php
$directorsWithMovies = Director::with('movies')->where('name', 'great')->get();
// Access the movies collection
$movies = $directorsWithMovies->movies;
```

For this you need to declare a `hasmany` relationship in your `Director` model:

```php
public function movies()
{
    return $this->hasMany('Movie');
}
```

If you want to pass a variable into `function($q) { //$variable }` then

```php
function($q) use ($variable) { //$variable }
```

#session-variables
  
The correct syntax for this is:

```php
Session::set('variableName', $value);
```

For Laravel 5.4 and later, the correct method to use is `put`:

```php
Session::put('variableName', $value);
```

To get the variable, you would use:

```php
Session::get('variableName');
```

If you need to set it once, I'd figure out when exactly you want it set and use `Events` to do it.

For example, if you want to set it when someone logs in, you'd use:

```php
Event::listen('auth.login', function() {
    Session::set('variableName', $value);
});
```

#query-addselect

```php
$orders = Order::where('status', 'paid')
	->whereRelation('user', 'referrer_id', auth()->user()->id)
	->addSelect([
		'total_price' => OrderItem::whereColumn('order_id', 'orders.id')
		->selectRaw('sum((price * quantity) * 0.1) as total_price')
	])->pluck('total_price')->toArray(); 

$paidOrders = \array_sum($orders);
```

```json
array:1 [
  0 => "300887.1"
]

$paidOrders = 300887.1
```

