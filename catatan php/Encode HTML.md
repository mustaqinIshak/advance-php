### encode HTML for secure

menghindari beberapa case yang dapat merusak code atau bahkan mencoba menjebol dengan menulis syntax di dalam form data kita 
seperti contoh di bawah :
```
ex case: 

<?php $username = "Kevin"; ?>
<div id="name"><?php echo $username; ?></div>

$username = "<strong>Kevin</strong>"; //membuat tulisan menjadi besar
$username = "<strong>Kevin"; //typo
$username = "Kevin</div>"; //mencoba merusak layout 

```
Reserved Character in HTML

< | > | & | "
----- | ----- | ----- | -----
`&lt;` | `&gt;` | `&amp;` | `&quot;`

adapun perlu di perhatikan dalam encode HTML yaitu

### Cross Site Scripting
-----
menulis syntax javascript di dalam query atau form html
berikut ciri-ciri Cross Site Scripting

*   "XSS"
*   Attacker tricks a web page into outputting javascript.
*   Code is trusted by the browser and executed.
*   Majir security vulnerability!
```
contoh css : 
globalbank/public/staff/subject/show?id=<strong>1</strong> //membuat font nya jadi bold
globalbank/public/staff/subject/show?id=<script>alert('Gotcha')</script> //memunculkan allert lewat query

```
### cara menangulanginya
-----
adapun cara penangulangannya dengan menuliskan syntax dengan membuat *Dynamic Data*

```
function.php
// buat sebuah function yg berisikan method function htmlspcialchars($var);

function h ($string = "") {
	return htmlspecialchars($string);
}
```
```
show.php
//di variabel yg berisi $_GET['quey'] panggil function tersebut dan isi dengan variabel $_get
$id = isset($_GET['id']) ? $_get['id'] : '1';
echo h($id);
```