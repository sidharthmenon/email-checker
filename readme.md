Validation Email for Laravel
=================
[![Laravel 5.4](https://img.shields.io/badge/Laravel-5.3-orange.svg?style=flat-square)](http://laravel.com)
[![License](http://img.shields.io/badge/license-MIT-brightgreen.svg?style=flat-square)](https://tldrlegal.com/license/mit-license)


Quick Installation
------------------

```
composer require tintnaingwin/emailchecker
```

Once this operation is complete, simply add the service provider class to your project's `config/app.php` file:

#### Service Provider
```php
Tintnaingwin\EmailChecker\EmailCheckerServiceProvider::class,
```

#### Facade
To use facade you have to add this line in `config/app.php` in aliases array
```php
'EmailChecker' => Tintnaingwin\EmailChecker\Facades\EmailChecker::class,
```

#### Example
To add 'email-checker' at email rule
```php
  // [your site path]/app/Http/Requests/RegisterRequest.php
 public function rules()
     {
         return [
             'name'  => 'required|max:255',
             'email' => 'bail|required|email|max:255|unique:users|email_checker',
             'password' => 'bail|required|min:6|confirmed',
         ];
     }
```

#### Example Usage With Facade
 
 ```php
 // reture boolean
 EmailChecker::check('me@example.com');
```


## License

The MIT License (MIT). Please see [License File](https://github.com/tintnaingwinn/email-checker/blob/master/LICENSE.md) for more information.
