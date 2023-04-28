# Clock-in-js

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <script src="/script.js"></script>
    <title>Digital Clock</title>
</head>
<body>
    <div class="digital-clock">
        <div class="time">
            <div class="left-side">
                <span id="hours">00</span>
            </div>
            <div class="right-side">
                <div class="right-top">
                    <span id="dots">:</span>
                    <span id="minutes">00</span>
                </div>
                <div class="right-down">
                    <span id="period">PM</span>
                    <span id="seconds">00</span>
                </div>
            </div>
        </div>
    </div>
    <script>
        function clock() {
            let hours = document.getElementById('hours');
            let minutes = document.getElementById('minutes');
            let seconds = document.getElementById('seconds');
            let period = document.getElementById('period');


            let h =new Date().getHours();
            let m =new Date().getMinutes();
            let s =new Date().getSeconds();

            let ampm =h >= 12 ? "PM" : "AM";

            if( h > 12){
                h = h - 12;
            }
            h = (h < 10) ? "0" + h : h;
            m = (m < 10) ? "0" + m : m;
            s = (s < 10) ? "0" + s : s;

            hours.innerHTML = h;
            minutes.innerHTML = m;
            seconds.innerHTML = s;
            period.innerHTML = ampm;

        };
        setInterval(clock,1000)
    </script>
</body>
</html>


*{
    padding: 0;
    margin: 0;
    box-sizing: border-box;
    font-family: 'poppins', sens-serif;
}

body, .time, .left-side, .right-side,.right-top, .right-down{
    display: flex;
    justify-content: center;
    align-items: center;
}
.digital-clock,.time, .right-side, .right-top, .right-down{
    position: relative;

}
body{
    min-height: 80vh;
    background-image:radial-gradient(circle, rgba(63,94,251,1) 0%, rgb(179, 38, 167) 100%);
}
.digital-clock{
    color: #ffffff;
    background-color: #2d2f38;
    width: 425px;
    padding: 20px 45px;
    /* box-shadow: 0 5px 25px rgba(14, 21, 37, 0.8); */
    border-radius: 10px;
}
.digital-clock::before{
    content: '';
    position: absolute;
    background: linear-gradient(45deg,blue,orange,green);
    top: -5px;
    bottom: -5px;
    left: -5px;
    right: -5px;
    z-index: -1;
    filter: blur(30px);
}
#hours{
    font-weight: 600;
    padding: 0 10px;
    line-height: 125px;
    font-size: 8em;
    background: -webkit-linear-gradient(90deg,blue,white);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}
.right-side{
    flex-direction: column;
}
#dots{
    font-size: 4em;
    transform: translateY(-3px);
    color: gray;
}
#minutes{
    font-size: 5em;
    font-weight: 500;
    margin-left: 10px;
    /* transform: translateY(10px); */
    background: -webkit-linear-gradient(90deg,orchid,white);
    -webkit-text-fill-color: transparent;
    -webkit-background-clip: text;
}
.right-down{
    margin-left: 14px;
    transform: translateY(-18px);
}
#period,#seconds{
     font-size: 1.8em;
     font-weight: 500;
     margin-left: 10px;

}
#period{
    color: orange;
}
#seconds{
    color: white;
}
