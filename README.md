# task-2-in-the-fourth-track
<!DOCTYPE html>


<html>
    <head>
        <title>Control Panel</title>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.0/css/bootstrap.min.css">
        <link href='https://fonts.googleapis.com/css?family=Acme' rel='stylesheet'>

        <style>
            body{
                font-family: 'Acme';font-size: 22px;
                margin: 100px;
                padding: 0;
                height: 100vh;
                align-items: center;
                justify-content: center;
                text-align: center;
                background-color: #fecea8;
            }

            .btn{
                vertical-align: middle;
                text-align: center;
                margin:  20px;
                width: 240px;
                height: 80px;
                border: none;
                background-color: #2a363b;
                color: #e84a5f;
                font-size: 18px;
                border-radius: 6px;
                outline: none;
                cursor: pointer;
                transition: .3s linear;
            }

            .btnR:hover{
                transform: scale(0.97);
                box-shadow: 15px 0 0 0   #ff847c;
                color: #e84a5f;

            }

            .btnL:hover{
                transform: scale(0.97);
                box-shadow: -15px 0 0 0 #ff847c;
                color: #e84a5f;

            }

            .btnF:hover{

                transform: scale(0.97);
                box-shadow: 0 -15px 0 0 #ff847c;
                color: #e84a5f;

            }

            .btnB:hover{

                transform: scale(0.97);
                box-shadow: 0 15px 0 0 #ff847c;
                color: #e84a5f;

            }
            .btnS:hover{
                transform: scale(0.97);
                box-shadow: 0 0 0 15px #ff847c;
                color: #e84a5f;


            </style>


        </head>
        <body>
            <form action="index.php" method="post">

                <div>   
                    <button type="submit" name="btn" value="forward" class="btn btnF  "><h2>Forward</h2></button>    
                    <br>
                    <button type="submit" name="btn" value="left" class="btn btnL "><h2>Left</h2></button>
                    <button type="submit" name="btn" value="stop" class="btn btnS "><h2>Stop</h2></button>
                    <button type="submit" name="btn" value="right" class="btn btnR "><h2>Right</h2></button>
                    <br>
                    <button type="submit" name="btn" value="backward" class="btn btnB  "><h2>Backward</h2></button>
                </div>
                <form>
                    <br>        
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>
                    <br>

                    <p style="color:#2a363b;" >
                        Desighned by Khalid ALshahham


                    </p> 
                    </body>
                    </html>

                    <?php
                    $serverName = "localhost";
                    $userName = "root";
                    $password = "";
                    $dataBaseName = "khalid";

                    $conn = mysqli_connect($serverName, $userName, $password, $dataBaseName);

                    if (!$conn) {
                        die("connection failed:" . mysqli_connect_error());
                    }

                    echo $_POST['btn'];
                    $btn = mysqli_real_escape_string($conn, $_POST['btn']);
                    $btn = $_POST['btn'];
                    $query = "INSERT INTO `control-panel` (`move`) VALUES ( '$btn' )";
                    $conn->query($query);
                    print_r($_POST['btn']);
                    $conn->close();
                    ?>
