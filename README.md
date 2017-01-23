# WPDB Standalone

Use the wordpress database class 'wpdb' without using wordpress. Usefull for developers who want to develop small proof of concepts that later have to be implemented within a Wordpress environment.

### Installation

Add the 'WPDB Standalone' library to your composer.json file
```sh
"repositories": [
    {
        "type": "package",
        "package": {
            "name": "gavinlight/wpdb_standalone",
            "version": "1.0",
            "source": {
                "url": "https://github.com/gavinlight/wpdb_standalone.git",
                "type": "git",
                "reference": "master"
            }
        }
    }
],
"require": {
    "gavinlight/wpdb_standalone": "1.0"
}
```

Install the library
```sh
$ composer install
```

### Usage

Create a config file, containing the following code
```sh
define('DB_NAME', 'your database name');
define('DB_USER', 'your database user');
define('DB_PASSWORD', 'your database user password');
define('DB_HOST', 'localhost');
define('DB_CHARSET', 'utf8mb4');
define('DB_COLLATE', '');
```

Load your config file and the autoloader
```sh
require_once( __DIR__ . '/config.php' );
require_once( __DIR__ . '/vendor/autoload.php' );
```

You can now use the $wpdb variable
```sh
$users = $wpdb->get_results( "SELECT * FROM wp_users" );
```
