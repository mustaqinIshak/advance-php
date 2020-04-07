### Encode URL Parameters
-----

kegunaannya untuk menghindari terjadinya kesalahan pembacaan url, jdi ketika user menulis search=tempat kerja, dengan menambahkan perintah urlencode atau rawurlencode

adapun perbedaannya urlencode dan rawurlencode
*	Letters , numbers, underscore, and dash are unchanged.
*	Reversed character are encoded.
*	urlencode: spaces become "+".
*	rawurlencode: spaces become "%20".
*	rawurlencode the path:
	*	paths is the parth before the "?".
	*	Spaces must be enoded as "%20".
*	urlencode the query strin:
	*	Query string is the part after the "?".
	*	Spaces are better encoded as "+".
*	Namun kenyataannya, akan jarang digunakan rawurlencode. 

```
urlencode($string)
rawurlencode($string)

//copy saja code di bawah ke file php dan run di localhost
<a href="show.php?name=<?php echo urlencode("John doe"); ?>">Link</a><br /> //show.php?name=John+doe
<a href="show.php?name=<?php echo urlencode("Widgets&More"); ?>">Link</a><br /> //show.php?name=Widget%26More
<a href="show.php?name=<?php echo urlencode("!#*?"); ?>">Link</a><br /> //show.php?name=!%23*%3F
```
* untuk lebih jelasnya berikut tabel Reserved Characters in URLs

! | # | $ | % | & | ' | ( | ) | * | + | , | / | : | ; | = | ? | @ | [ | ]
----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | ----- | -----
%21 | %23 | %24 |%25 | %26 | %27 | %28 | %29 | %2A | %2B | %2C | %2F | %3A |%3B | %3F | $3D | %40 | %5B | %5D
