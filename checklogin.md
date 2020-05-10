<?php
$message="";
if(count($_POST)>0) 
{
    $conn = mysqli_connect("localhost","root","","users");
    $sql="SELECT * FROM Registration WHERE Username='" . $_POST["uname"] . "' and Passwd = '". $_POST["psw"]."'";
	$result = mysqli_query($conn,$sql);
	$count  = mysqli_num_rows($result);
    if($count==0) 
    {
		$message = "Invalid Username or Password!";
    } else 
    {
		$message = "You are successfully authenticated!";
	}
}
echo "<br>". $message;
?>