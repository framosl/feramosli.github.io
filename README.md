# feramosli.github.io
Trabajo de investigación de estructura de datos 


<!DOCTYPE html>

<html lang="en">

<head>

  <meta charset="UTF-8">

  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <meta http-equiv="X-UA-Compatible" content="ie=edge">

  <link rel="stylesheet" href="style.css">

  <title>Calculator</title>

</head>

<body>

  <div class="container">

    <div class="output">

      <input type="text" placeholder="0" readonly>

    </div>

    <div class="btns">

      <button onclick="clr()" class="sp">C</button>

      <button onclick="del()" class="sp">DEL</button>

      <button onclick="insert('%')" class="sp">%</button>

      <button onclick="insert('/')" class="sp">÷</button>

      <button onclick="insert('7')">7</button>

      <button onclick="insert('8')">8</button>

      <button onclick="insert('9')">9</button>

      <button onclick="insert('*')" class="sp">×</button>

      <button onclick="insert('4')">4</button>

      <button onclick="insert('5')">5</button>

      <button onclick="insert('6')">6</button>

      <button onclick="insert('-')" class="sp">-</button>

      <button onclick="insert('1')">1</button>

      <button onclick="insert('2')">2</button>

      <button onclick="insert('3')">3</button>

      <button onclick="insert('+')" class="sp">+</button>

      <button onclick="insert('0')">0</button>

      <button onclick="insert('.')">.</button>

      <button onclick="calc()" class="sp equal">=</button>

    </div>

    <div class="appmenu">

      <div class="icon">

        <span></span>

        <span></span>

        <span></span>

      </div>

      <div class="menu">

        <div class="blue"></div>

        <div class="orange"></div>

        <div class="red"></div>

        <div class="purple"></div>

        <div class="pink"></div>

      </div>

    </div>

  </div>

  <script src="script.js"></script>

</body>

</html>

:root {

  --main-color: #005DD9;

}

* {

  padding: 0;

  margin: 0;

  box-sizing: border-box;

  font-family: Arial, Helvetica, sans-serif;

}

body {

  height: 100vh;

  display: flex;

  justify-content: center;

  align-items: center;

  position: relative;

}

.container {

  width: 306px;

  padding: 20px 10px;

  border-radius: 10px;

  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2),

    -5px -5px 10px rgba(0, 0, 0, 0.2)

}

.output {

  border: solid 2px var(--main-color);

  height: 60px;

  border-radius: 20px;

  overflow: hidden;

  margin-bottom: 20px;

}

.output input {

  height: 100%;

  width: 100%;

  border: none;

  outline: none;

  font-size: 50px;

  text-align: end;

  padding-right: 20px;

  color: var(--main-color);

}

.output input::placeholder {

  color: var(--main-color);

}

.btns {

  display: grid;

  grid-template-columns: repeat(4, 60px);

  gap: 10px 15px;

}

.btns button {

  border: none;

  outline: none;

  height: 60px;

  border-radius: 50%;

  font-size: 25px;

  color: var(--main-color);

  background-color: #fff;

  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.2)

}

.btns button.sp {

  background-color: var(--main-color);

  color: #fff;

}

.btns button.equal {

  width: 135px;

  border-radius: 22px;

}

.appmenu {jajaja

  position: absolute;

  top: 10px;

  left: 10px;

}

.icon {

  display: flex;

  flex-direction: column;

  width: 25px;

  gap: 5px;

  margin-bottom: 10px;

  transition: 0.3s;

}

.icon span {

  background-color: var(--main-color);

  height: 5px;

  width: 100%;

  border-radius: 20px;

  transition: 0.3s;

}

.menu {

  padding: 10px;

  border-radius: 10px;

  background-color: #fff;

  display: flex;

  gap: 10px;

  transform: scale(0);

  transform-origin: top left;

  transition: 0.3s;

  box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);

}

.menu.open {

  transform: scale(1);

}

.menu div {

  height: 40px;

  width: 40px;

  border-radius: 50%;

  border: solid 2px #818181;

}

.menu div:nth-child(1) {

  background-color: #005DD9;

}

.menu div:nth-child(2) {

  background-color: #DF8F12;

}

.menu div:nth-child(3) {

  background-color: #E23434;

}

.menu div:nth-child(4) {

  background-color: #622AEB;

}

.menu div:nth-child(5) {

  background-color: #FF20A1;

}

body.blue {

  --main-color: #005DD9;

}

body.orange {

  --main-color: #DF8F12;

}

body.red {

  --main-color: #E23434;

}

body.purple {

  --main-color: #622AEB

}

body.pink {

  --main-color: #FF20A1;

}

let outScreen = document.querySelector('.output input');

mode = 'calc';

function insert(num) {

  outScreen.value += num;

  if (mode == 'equal') {

    outScreen.value = '';

    outScreen.value += num;

    mode = 'calc';

  };

};

function clr() {

  outScreen.value = '';

};

function del() {

  outScreen.value = outScreen.value.slice(0, -1);

  if (mode == 'equal') {

    outScreen.value = '';

  };

};

function calc() {

  try {

    outScreen.value = eval(outScreen.value);

    mode = 'equal';

  } catch (err) {

    outScreen.value = 'INVALID';

    mode = 'equal';

  };

};

let menuIcon = document.querySelector('.icon'),

  menu = document.querySelector('.menu');

menuIcon.onclick = function() {

  menu.classList.toggle('open');

};

let blueTheme = document.querySelector('.blue'),

  orangeTheme = document.querySelector('.orange'),

  redTheme = document.querySelector('.red'),

  purpleTheme = document.querySelector('.purple'),

  pinkTheme = document.querySelector('.pink');

blueTheme.onclick = function() {

  document.body.classList.remove('orange');

  document.body.classList.remove('red');

  document.body.classList.remove('purple');

  document.body.classList.remove('pink');

  document.body.classList.add('blue');

  menu.classList.remove('open');

};

orangeTheme.onclick = function() {

  document.body.classList.remove('blue');

  document.body.classList.remove('red');

  document.body.classList.remove('purple');

  document.body.classList.remove('pink');

  document.body.classList.add('orange');

  menu.classList.remove('open');

};

redTheme.onclick = function() {

  document.body.classList.remove('orange');

  document.body.classList.remove('blue');

  document.body.classList.remove('purple');

  document.body.classList.remove('pink');

  document.body.classList.add('red');

  menu.classList.remove('open');

};

purpleTheme.onclick = function() {

  document.body.classList.remove('orange');

  document.body.classList.remove('red');

  document.body.classList.remove('blue');

  document.body.classList.remove('pink');

  document.body.classList.add('purple');

  menu.classList.remove('open');

};

pinkTheme.onclick = function() {

  document.body.classList.remove('orange');

  document.body.classList.remove('red');

  document.body.classList.remove('purple');

  document.body.classList.remove('blue');

  document.body.classList.add('pink');

  menu.classList.remove('open');

};
