# Commands

- [CMS Install](#install)
- [Create admin user](#create-admin-user)
- [Publish assets](#publish-assets)
- [Create a plugin](#create-plugin)
    
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

<a name="create-plugin"></a>
## Create a plugin
It's used to create a plugin. The plugin created will be located in `/platform/plugins`

```
php artisan cms:plugin:create <plugin>
```

Ex:

![Create plugin](./images/create-plugin.png)

