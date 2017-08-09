```
// index.php
<html>
<head>

</head>
<body>

<a href="read.php?lang=swe"> Swedish</a><br>
<a href="read.php?lang=fin"> Finnish</a>

</body>
</html>
```
```
//read.php
//create a file 'flag.php' outside the webroot

<?php

    $lang = $_GET["lang"];
    if($lang == "swe")
    	echo '<img src="https://upload.wikimedia.org/wikipedia/en/thumb/4/4c/Flag_of_Sweden.svg/800px-Flag_of_Sweden.svg.png"></img><br>';
    elseif($lang == "fin")
    	echo '<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/b/bc/Flag_of_Finland.svg/800px-Flag_of_Finland.svg.png"></img>';
    else
	echo "only Finland and Sweden so far :(";
			
    error_reporting(E_ALL);
    ini_set('display_errors', 1);
    $h1 =  $_SERVER['HTTP_ACCEPT_LANGUAGE'];
    $h1 = explode(",",$h1);
    include_once("footer/". $h1[0] . ".php");
    include_once("footer/sv-fi.php");

?>
```
