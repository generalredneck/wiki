# Directory structure
Your Aquifer projects will contain the following directories by default:

## `/settings`
Contains settings.php files that will be placed into the Drupal `/sites/default` directory in the build. It will contain the following files:

- `settings.php`: Contains master module configuration and any other configuration that will be common to all environments for the site. This file will be under version control so do not put sensitive or local environment information in it.
- `secret.settings.php`: Contains database settings for the environment and any other sensitive configuration settings. **Important**: Be sure to configure your database settings in this file before you build your project. This file will not be under version control for security reasons.
- `local.settings.php`: Contains local configuration overrides for the current environment. This file will not be under version control as it contains environment specific settings.

## `/root`
Holds files that will be placed into the Drupal root directory in the build. By default it will contain the following files:

- `.htaccess`: This is Drupal's default .htaccess file. You can override it here and your changes will be incorporated into the build by overwriting the file installed by Drupal.
- `robots.txt`: This is Drupal's default robots.txt file. You can override it here and your changes will be incorporated into the build by overwriting the file installed by Drupal.
- You can also add your own files, like site verification files for example, that will get placed into the Drupal root directory during the build.

## `/modules`
Contains custom modules and features for the site. It will contain the following subdirectories by default:

- `/custom`: Should contain any custom modules you have developed for the site.
- `/features`: Should contain any custom Features modules you have created for the site.

## `/themes`
Holds custom themes for the site. It will contain the following subdirectory by default:

- `/custom`: Should contain any custom themes you have developed for the site.

## `/files` 
This directory is your files directory for Drupal and is symlinked to `/sites/default/files` in the build.

## `/build`
Contains the Drupal installation generated by Aquifer when you run `aquifer build`. You should never modify files in this directory without the understanding that your changes will be temporary. They are not under version control and will also be overwritten the next time you build the project.

## Customizing the directory structure
It should be noted that Aquifer's directory structure is completely configurable (see 'Using a config file' section [here](/sections/scaffold-system.html)). The folders specified in this list are sensible defaults, but if you prefer a different structure, checkout the Scaffolding documentation.
