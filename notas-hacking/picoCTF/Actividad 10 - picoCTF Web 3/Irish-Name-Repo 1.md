# Irish-Name-Repo 1
There is a website running at `https://jupiter.challenges.picoctf.org/problem/39720/` ([link](https://jupiter.challenges.picoctf.org/problem/39720/)) or http://jupiter.challenges.picoctf.org:39720. Do you think you can log us in? Try to see if you can login!
There doesn't seem to be many ways to interact with this. I wonder if the users are kept in a database?
Try to think about how the website verifies your login.

## Solución
1. Entrar al sitio web, entrar al admin login, intentar loggearse
2. Inspeccionar el código fuente, cambiar el parámetro hidden value=0 a value =1
3. Como es una sentencia SQL, inyectar una ' or 1 == 1; para hacer la condición verdadera y obtener la bandera
```
<!doctype html>
<html>
<head>
    <title>Login</title>
    <link rel="stylesheet" type="text/css" href="[//maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css](view-source:https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css)">
</head>
<body>
<div class="container">
    <div class="row">
        <div class="col-md-12">
            <div class="panel panel-primary" style="margin-top:50px">
                <div class="panel-heading">
                    <h3 class="panel-title">Log In</h3>
                </div>
                <div class="panel-body">
                    <form action="[login.php](view-source:https://jupiter.challenges.picoctf.org/problem/39720/login.php)" method="POST">
                        <fieldset>
                            <div class="form-group">
                                <label for="username">Username:</label>
                                <input type="text" id="username" name="username" class="form-control">
                            </div>
                            <div class="form-group">
                                <label for="password">Password:</label>
                                <div class="controls">
                                    <input type="password" id="password" name="password" class="form-control">
                                </div>
                            </div>
                            <input type="hidden" name="debug" value="1">

                            <div class="form-actions">
                                <input type="submit" value="Login" class="btn btn-primary">
                            </div>
                        </fieldset>
                    </form>
                </div>
            </div>
        </div>
    </div>
</div>
</body>
</html>

username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_c218b685}
```