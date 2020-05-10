<!DOCTYPE html>
<html>
    <body>
        <?php
            $link=mysqli_connect("localhost","root","","users");
            if($link==false)
            {
                die("ERROR: Could not connect. " . mysqli_connect_error());
            }
            $uname       = mysqli_real_escape_string($link, $_POST['uname']);
            $email  = mysqli_real_escape_string($link, $_POST['email']);
            $psw        = mysqli_real_escape_string($link, $_POST['psw']);
            $sql="INSERT INTO Registration(Email,Username,Passwd) 
            VALUES ('$email','$uname','$psw')";
            echo "<br>";
            $result=mysqli_query($link,$sql);
            if($result)
            {
                echo "Records inserted successfully.";
            }
            else
            {
                echo "ERROR: Could not able to execute $sql. " . mysqli_error($link);
            }
            echo "<br>";
            echo "<br> Login With These Details.... <br>";
            $sql="SELECT ID,Username FROM Registration";
            $result=mysqli_query($link,$sql);
            if($result->num_rows>0)
            {
                while($row=$result->fetch_assoc())
                {
                    echo "<br> ID: ".$row["ID"]." -Username: ".$row["Username"]." With your Password<br>";
                }
            }
            else
            {
                echo " 0 Results";
            }
            mysqli_close($link);
            
        ?>
    </body>
</html>