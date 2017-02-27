#Laravel和前端那些事

```
composer create-project laravel/laravel laravel --prefer-dist "5.3.*"
cd laravel
npm install --save-dev gulp --registry https://registry.npm.taobao.org --no-bin-link
npm install --registry https://registry.npm.taobao.org --no-bin-link
npm rebuild node-sass --registry https://registry.npm.taobao.org --no-bin-link
gulp
npm install laravel-elixir-browsersync-official --save-dev --registry https://registry.npm.taobao.org --no-bin-link
gulp watch
gulp --production		// 压缩
```

###laravel-elixir
gulpfile.js (laravel5.2)
```
// elixir.config.assetsPath = 'assets';

elixir(function(mix) {
	// 使用Elixir编译Sass
    // mix.sass('app.scss');
    // mix.sass(['app.scss', 'front.scss']);
    // mix.sass(['app.scss', 'front.scss'], 'public/styles/style.css');
    // mix.sass(['app.scss', 'front.scss'], 'public/styles/style.css').sass('admin.scss', 'public/admin/admin.css');
    
    // 使用Elixir编译Less
    // mix.less('app.less');

    // 合并压缩静态文件
    // mix.styles(['1.css', '2.css', '3.css']);
    // mix.scripts(['1.js', '2.js', '3.js']);
    
    // 解决缓存问题 （对静态文件的版本管理）
    mix.styles(['1.css', '2.css', '3.css']).version('css/all.css');
});
```

gulpfile.js (laravel5.3)
```
elixir((mix) => {
    mix.sass('app.scss')
       .browserSync()
       .webpack('app.js');
});
```

welcome.blade.php
```
<link rel="stylesheet" href="{{ elixir('css/all.css') }}">
```

###laravel 表单和HTML扩展包
参考资料：[http://www.cnblogs.com/offcos/p/5840137.html](http://www.cnblogs.com/offcos/p/5840137.html)
```
"require": {
    "laravelcollective/html": "5.3.*"
}


```
