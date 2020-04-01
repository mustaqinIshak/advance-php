# Struktur web php
------
in the folder private/initialize.php
```
//Assign file pathas to PHP constants
//__FILE__ returns the current path to this file
//dirname() returns the path to the parent directory
//explaine for define: https://www.php.net/manual/en/function.define.php
define("PRIVATE_PATH", dirname(__FILE__));
define("PROJECT_PATH", dirname(PRIVATE_PATH));
define("PUBLIC_PATH", PROJECT_PATH . "/public");
define("SHARED_PATH", PROJECTPATH."/shared");

//Assign the root URL to a PHP constant
// * Do not need to include the domain
// * Use same document root as webserver
// * Can set hardcoded value:
//define("WWW_ROOT", '/~grindpants/globe_bank/public');
//define("WWW_ROOT", '');
// * Can dynamically find everything in URL uip to "/public"
$public_end = strpos($_server['SCRIPT_NAME'], '/PUBLIC') + 7;
$doc_root = substr($_SERVER['SCRIPT_NAME'], 0, $public_end);
define('WWW_ROOT', $doc_root);

require_once('function.php')
```
in the private/function.php
```
function url_for($script_path) {
	if($script_path[0] != '/') {
	  $srcript_path = "/" . $script_path;
	}
	return WWW_ROOT . $script_path;
}
```
