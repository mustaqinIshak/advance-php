### syntax and flow GET
-----
flow untuk mengirim data dan mengambil data melalui query yg biasa di tulis di URL

ex : `globalbank/public/staff/subject/show?id=1`

```
show.php

<?php 
    $id = $_GET['id']; // ini untuk mengambl id dari url Query
    echo $id;
?>
```