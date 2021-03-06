# Dashboard menu

## Add new menu

- Open `/platform/plugins/<your-plugin>/src/Providers/<YourPlugin>ServiceProvider.php`. Add below code to function `boot`

```php
\Event::listen(\Illuminate\Routing\Events\RouteMatched::class, function () {
    dashboard_menu()->registerItem([
        'id'          => 'cms-plugins-<your-plugin>', // key of menu, it should unique
        'priority'    => 1,
        'parent_id'   => null,
        'name'        => 'Your plugin name', // It should be a translation key. Ex: plugins/test::test.name
        'icon'        => 'fa fa-camera', // Fontawesome icon
        'url'         => route('<plugins>.index'), // route to your plugin list.
        'permissions' => ['<plugins>.index'], // permission should same with route name, you can see that flag in Plugin.php
    ]);
});
```

## Remove a menu

- Add to `/platform/themes/your-theme/functions/functions.php`

```php
\Event::listen(\Illuminate\Routing\Events\RouteMatched::class, function () {
    dashboard_menu()
        ->removeItem('menu-id-1')
        ->removeItem('menu-id-2');
});
```

Ex: If you want to remove menu "Media"

```php
\Event::listen(\Illuminate\Routing\Events\RouteMatched::class, function () {
    dashboard_menu()
        ->removeItem('cms-core-media');
});
```

You can find menu ID in source code

![Theme commands](./images/find-dashboard-menu-id.png)

Or from browser

![Theme commands](./images/find-dashboard-menu-id-1.png)