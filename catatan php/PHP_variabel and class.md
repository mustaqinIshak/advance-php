### PHP string function
----

function | syntax
------------ | ----------
String | 
Lowercase | echo strtolower($var);
Uppercase | echo strtoupper($var);
Uppercase first | echo ucfirst($var);
Uppercase word | echo ucwords($var);
Length | echo strlen($var);
Trim | echo "A" . trim ("B C D") . "E";
Find | echo strstr($var, "word");
Replace by string | echo str_replace("quick", "super-farst", $var);
Repeat | echo str_repeat($var, 2);
Make substring (mengambil string dri index ke berapa sampai ke berapa)  | echo substr($var, 5, 10);
Find position | echo strpos($var, "brown");
Find character | echo strchr($var, "z");
 | 
Array |
Array function  :|
$arr = array(4, 8, 15, 13) / $array = [1, 2, 3] | 
count (menghitung panjang array)| echo count($arr);
max | echo max($arr);
min | echo min($arr);
sort | sort($arr); print_r($arr);
reverse sort | rsort($arr); print_r($arr));
implode(array ke string) | echo str_arr = implode(" ",$arr);
explode(string ke array) | print_r(explode(" ",$arr));
mengecek apakah ada value yg kita inginkan atau tidak dalam array | 
echo in_array(15, $arr); // return true | 
echo in_array(16, $arr); // return false |
console log nya array | print_r($number);
make array unique | array_unique($arr);
 |
Array association(mirip seperti json di nodejs) : | $biodata = array("firstName" => "takin", "lastName" => "ishak");
cara manggilnya | $biodata["firstName"];
 | 
Integer | 
make negatif integer | -1 * $n;
make positif integer or absolute value | abs($n);
Exponential (perkalian pangkat (2 pangkat 8))| pow(2,8);
Square root (akar pangkat dua)| sqrt(100); hasilnya = 10 karena 10 * 10 = 100
Modulo | fmod(20,7);
Random | rand();
Random (min,max) | rand(1, 10);
 | 
`+=` | `$int += 4;`
`-=` | `$int -= 4;`
`*=` | `$int *= 4;`
`/=` | `$int \= 4;`
 | 
di php integer ditambah string angka jadinya intger | echo 1 + "2 houses"
 | 
Floating Point Number | 
$float = 3.14; |
Round (pembulatan belakang koma) | round($float,1); = 3.1 
Ceiling (pembulatan ke atas) | ceil($float); = 4
Floor (pembulatan ke bawah) |floor($float); = 3
 |
cara mengecek tipe variabel, balikannya(true / false) |
integer | is_int($integer); balikannya (1)
 | is_int($float); balikannya("kosong")
float | is_float($float);  balikannya (1)
 | is_float($float); balikannya("kosong")
numeric | is_numeric($integer);  balikannya (1)
 | is_numeric($float); balikannya(1)
 | 
NULL and empty | 
NULL | $var = null //true
 | $var=" "//false
empty | "", null, 0, 0.0, "0", false, array() => ini semua contoh empty;
 | 
Type Juggling and Type Casting | 
Type Juggling (untuk mengetahui type data suatu variabel) : | 
$cats = "cats"; | cats: <?php echo  gettype($cats); ?> => cats: string 
$count = 2; | count: <?php echo gettype($count); ?> => count: integer
Type Casting(mengubah tipe data variabel) :| 
$test1 = 3 | settype($test1, "string");
$test2 = "2" | settype($test2, "integer");
 | 
Constant | 
cara penulisan constant : |
define("namaVariable", "isi variabel") | define("MAX_WIDTH", 981); echo MAX_WIDTH;

*	dont forget this after write syntax " ; "
*	referensi array function "http://php.net/maual/en/ref.array.php"
*	untuk mengecek tipe data ini empty => empty($varr)

### Reference Class in PHP
----
```
interface BinaryOperator {
  public function perform($value1, $value2);
}

class AdditionOperator implements BinaryOperator {
  public function perform($value1, $value2) {
    return $value1 + $value2;
  }
}

class SubtractionOperator implements BinaryOperator {
  public function perform($value1, $value2) {
    return $value1 - $value2;
  }
}

class MultiplicationOperator implements BinaryOperator {
  public function perform($value1, $value2) {
    return $value1 * $value2;
  }
}

class DivisionOperator implements BinaryOperator {
  public function perform($value1, $value2) {
    return $value1 / $value2;
  }
}

function get_operator($op)
{
  switch ($op)
  {
    case '+': return new AdditionOperator();
    case '-': return new SubtractionOperator();
    case '*': return new MultiplicationOperator();
    case '/': return new DivisionOperator();
  }
}

function basicOp($op, $val1, $val2)
{
  $operator = get_operator($op);
  return $operator->perform($val1, $val2);
}
```