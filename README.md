# ip2city

17mon for Laravel 5

## 安装

1. 安装包文件
  ```shell
  composer require "mylukin/ip2city:dev-master"
  ```

2. 添加 `ServiceProvider` 到您项目 `config/app.php` 中的 `providers` 部分:

  ```php
  'MyLukin\IP2City\ServiceProvider',
  ```

3. 创建配置文件:

  ```shell
  php artisan vendor:publish --provider="MyLukin\IP2City\ServiceProvider"
  ```

  然后请修改 `config/ip2city.php` 中对应的项即可。

4. 添加下面行到 `config/app.php` 的 `aliases` 部分：

  ```php
  'IP2City' => 'MyLukin\IP2City\Facade',
  ```

## 使用


由于我们已经添加了Facade `IP2City`，那么我们可以在控制器或者其它任何地方使用 `IP2City::方法名` 方式调用。

下面写一个例子：


```php
<?php namespace App\Http\Controllers;

use IP2City;

class WelcomeController extends Controller {
    
    public function index()
    {
        var_dump(IP2City::ip2addr('115.28.212.163'));
    }
}
```

## License

MIT