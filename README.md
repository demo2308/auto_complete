# auto_complete
Autocomplete text box in php
<?php
 $q=$_GET['q'];
 $my_data=mysql_real_escape_string($q);
 $mysql=mysql_connect('localhost','root','') or die("Database Error");
 $mysql_connect=mysql_select_db('test',$mysql);
 $sql="SELECT name FROM autocomplete WHERE name LIKE '$q%'";
 $result = mysql_query($sql);

 if($result)
 {
  while($row=mysql_fetch_array($result))
  {
   echo $row['name']."\n";
  }
 }
?>

