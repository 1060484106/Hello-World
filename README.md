<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>心动</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        html,
        body {
            width: 100%;
            height: 100%;
            text-align: center;
        }

        .textCon {
            position: relative;
            width: 200px;
            height: 60px;
            margin: 100px auto;
        }

        .textCon span {
            display: inline-block;
            font-size: 48px;
            padding: 5px;
            color: hotpink;
            animation: font 1.2s ease-in-out infinite;
        }

        .textCon span:nth-child(1) {
            animation-delay: 0.1s;
            color: deeppink;
        }

        .textCon span:nth-child(2) {
            animation-delay: 0.2s;
        }

        .textCon span:nth-child(3) {
            animation-delay: 0.3s;
            color: deeppink;
        }

        @keyframes font {
            0% {
                opacity: 0;
                transform: scale(1.1);
            }

            50% {
                opacity: 0.8;
                transform: scale(1.2);
            }

            100% {
                opacity: 0;
                transform: scale(1.1);
            }
        }

        .textCon .item {
            position: absolute;
            opacity: 0;
            background-color: #cc2a5d;
            transform: rotate(45deg);
            animation: hearts 3s ease-in-out infinite;
        }

        .textCon .item::before,
        .textCon .item::after {
            content: '';
            width: 100%;
            height: 100%;
            background-color: #cc2a5d;
            position: absolute;
            top: 0;
            left: 0;
            border-radius: 50%;
        }

        .textCon .item::before {
            transform: translateX(-50%);
        }

        .textCon .item::after {
            transform: translateY(-50%);
        }

        .heart {
            position: relative;
            width: 100px;
            height: 100px;
            background-color: #cc2a5d;
            margin: 100px auto;
            transform: rotate(45deg);
            animation: heart 1.2s ease-in-out infinite;
        }

        .heart::before,
        .heart::after {
            content: '';
            width: 100%;
            height: 100%;
            background-color: #cc2a5d;
            position: absolute;
            top: 0;
            left: 0;
            border-radius: 50%;
        }

        .heart::before {
            transform: translateX(-50%);
        }

        .heart::after {
            transform: translateY(-50%);
        }

        @keyframes heart {
            0% {
                transform: scale(0.8) rotate(45deg);
                opacity: 0.8;
            }

            50% {
                transform: scale(1) rotate(45deg);
                opacity: 1;
            }

            100% {
                transform: scale(0.8) rotate(45deg);
                opacity: 0.8;
            }
        }

        @keyframes hearts {
            0% {
                transform: translateY(0%) rotate(45deg);
                opacity: 0;
            }

            20% {
                transform: translateY(-20%) rotate(45deg);
                opacity: 0.8;
            }

            100% {
                transform: translateY(100%) rotate(45deg);
                opacity: 0;
            }
        }

        .happy {
            position: relative;
            width: 100%;
            color: deeppink;
            margin: 0 auto;

        }

        .happy span {
            display: inline-block;
            padding: 8px;
            margin-left: 20px;
            font-size: 60px;
            color: #cc2a5d;
            animation: fonts 1.2s ease-in-out infinite;
        }

        .happy span:nth-child(1) {

            margin-left: 0px;
            animation-delay: 0.2s;
        }

        .happy span:nth-child(2) {

            margin-left: 20px;
            animation-delay: 0.4s;
        }

        .happy span:nth-child(3) {

            margin-left: 80px;
            animation-delay: 0.6s;
        }

        .happy span:nth-child(4) {

            margin-left: 20px;
            animation-delay: 0.8s;
        }

        @keyframes fonts {
            0% {
                opacity: 0;
                transform: scale(1.1);
                transform: translateY(0%) rotate(-180deg);
              
            }

            50% {
                opacity: 0.8;
                color: #eb316c;
                transform: translateY(-20%) rotate(180deg);
                transform: scale(1.2);
            }

            100% {
                transform: translateY(-100%) rotate(180deg);
                opacity: 0;
                transform: scale(1.1);
            }
        }
    </style>
</head>

<body>
    <div class="textCon">
        <span>小</span>
        <span>猪</span>
        <span>猪</span>
    </div>
    <div class="heart"></div>
    <!-- <div class="img"><img src="" alt=""></div> -->
    <div class="happy">
        [宇]
        <span>七</span>
        <span>夕</span>
        <span>快</span>
        <span>乐</span>
        [倩]
    </div>
</body>
<script>
    var box = document.getElementsByClassName('textCon')[0];

    function init() {
        var width = box.offsetWidth;
        var count = parseInt(width / 50 * 5);
        for (var i = 0; i < count; i++) {
            var size = parseInt(ran(70, 130) / 10);
            var ele = document.createElement('div');
            ele.classList.add('item');
            ele.style.height = size + 'px';
            ele.style.width = size + 'px';
            ele.style.left = ran(0, 100) + '%';
            ele.style.top = ran(30, 150) + '%';
            ele.style.animationDelay = ran(0, 30) / 10 + 's';
            box.appendChild(ele);
        }
    }

    function ran(min, max) {
        min = parseInt(min);
        max = parseInt(max);
        return Math.floor(Math.random() * (max - min + 1)) + min;
    }
    init();
</script>

</html>
