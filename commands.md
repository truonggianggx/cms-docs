# Commands

- [CMS Install](#install)
- [Create admin user](#create-admin-user)
- [Publish assets](#publish-assets)
- [Create a package](#create-package)
- [Create a plugin](#create-plugin)
- [Activate a plugin](#activate-plugin)
- [Deactivate a plugin](#deactivate-plugin)
- [Remove a plugin](#remove-plugin)
    
List of commands are used in Botble CMS

<a name="install"></a>
## CMS Install
It's used to install CMS.

```
php artisan cms:install
```

Ex:

![Install CMS](./images/install-command.png)

<a name="create-admin-user"></a>
## Create admin user
It's used to create an admin user.
```
php artisan cms:user:create
```

Ex:

![Create User](./images/create-user.png)

Then you can go to `/admin` and login using account `johnsmith` - `12345678`

## Publish assets
By default, CMS assets is located in `/platform` so to make it accessible we have to copy it into `/public/vendor/core`.
To do that, we need to run command:

```
php artisan vendor:publish --tag=cms-public --force
```

Ex: 

![Publish assets](./images/publish-assets.png)

<a name="create-package"></a>
## Create a package
It's used to create a package. The package created will be located in `/platform/packages`

```
php artisan cms:package:create <plugin>
```

Ex:

![Create package](./images/create-package.png)

Package isn't loaded after created. You need to add it into composer.json and run `composer update` to add it.

<a name="create-plugin"></a>
## Create a plugin
It's used to create a plugin. The plugin created will be located in `/platform/plugins`

```
php artisan cms:plugin:create <plugin>
```

Ex:

![Create plugin](./images/create-plugin.png)

<a name="activate-plugin"></a>
## Activate a plugin
Activate an existed plugin.

```
php artisan cms:plugin:activate <plugin>
```

Ex:

![Activate plugin](./images/activate-plugin.png)

That command will add that plugin into list activated plugin in table `settings`, run migrate to update database and clear cache.

<a name="deactivate-plugin"></a>
## Deactivate a plugin
Deactivate an existed plugin.

```
php artisan cms:plugin:deactivate <plugin>
```

Ex:

![Deactivate plugin](./images/deactivate-plugin.png)

That command will remove that plugin from list activated plugin in table `settings` so that plugin won't be loaded and clear cache.

<a name="remove-plugin"></a>
## Remove a plugin
Remove an existed plugin.

```
php artisan cms:plugin:remove <plugin>
```

Ex:

![Remove plugin](./images/remove-plugin.png)

That command will deactivate plugin, remove that plugin's assets, tables...

