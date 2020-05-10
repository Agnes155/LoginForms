<!DOCTYPE html>
<?php
    session_start();
?>
<html>
    <head>
        <h1>
            <center>
                LOGIN FORM
            </center>
        </h1>
    </head>
    <body>
        <center>
            <form action="checklogin.php" method="post">
                <div class="container">
                    <br><label for="uname"><b>Username</b></label>
                    <input type="text" placeholder="Enter Username"name="uname"required></br><br>
                    <label for="psw"><b>Password</b></label>
                    <input type="password"placeholder="Enter Password"name="psw"required></br><br>
                    <input type="submit"value="Login"></br><br>
                    <label>
                </div>
            </form>
        </center>
    </body>
</html>