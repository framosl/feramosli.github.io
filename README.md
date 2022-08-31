# feramosli.github.io
Trabajo de investigación de estructura de datos 



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

<!DOCTYPEhtml>
<html lang="es">

<cabeza>
  <juego de caracteres meta="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <enlace rel="hoja de estilo" href="estilo.css">
  <título>Calculadora</título>
</cabeza>

<cuerpo>
  <div class="contenedor">
    <div clase="salida">
      <tipo de entrada="texto" marcador de posición="0" solo lectura>
    </div>
    <div clase="btns">
      <button onclick="clr()" class="sp">C</button>
      <button onclick="del()" class="sp">DEL</button>
      <button onclick="insert('%')" class="sp">%</button>
      <button onclick="insertar('/')" class="sp">÷</button>
      <button onclick="insertar('7')">7</button>
      <button onclick="insertar('8')">8</button>
      <button onclick="insertar('9')">9</button>
      <button onclick="insertar('*')" class="sp">×</button>
      <button onclick="insertar('4')">4</button>
      <button onclick="insertar('5')">5</button>
      <button onclick="insertar('6')">6</button>
      <button onclick="insertar('-')" class="sp">-</button>
      <botón onclick="insertar('1')">1</botón>
      <button onclick="insertar('2')">2</button>
      <button onclick="insertar('3')">3</button>
      <button onclick="insertar('+')" class="sp">+</button>
      <botón onclick="insertar('0')">0</botón>
      <button onclick="insertar('.')">.</button>
      <button onclick="calc()" class="sp igual">=</button>
    </div>
    <div class="menúaplicación">
      <div clase="icono">
        <span></span>
        <span></span>
        <span></span>
      </div>
      <div clase="menú">
        <div clase="azul"></div>
        <div clase="naranja"></div>
        <div clase="rojo"></div>
        <div clase="púrpura"></div>
        <div clase="rosa"></div>
      </div>
    </div>
  </div>
  <secuencia de comandos src="secuencia de comandos.js"></secuencia de comandos>
</cuerpo>

</html>

:raíz {
  --color principal: #005DD9;
}

* {
  relleno: 0;
  margen: 0;
  tamaño de caja: caja de borde;
  familia tipográfica: Arial, Helvetica, sans-serif;
}

cuerpo {
  altura: 100vh;
  pantalla: flexible;
  justificar-contenido: centro;
  alinear elementos: centro;
  posición: relativa;
}

.envase {
  ancho: 306px;
  relleno: 20px 10px;
  borde-radio: 10px;
  sombra de caja: 5px 5px 10px rgba(0, 0, 0, 0.2),
    -5px -5px 10px rgba(0, 0, 0, 0.2)
}

.producción {
  borde: sólido 2px var(--main-color);
  altura: 60px;
  borde-radio: 20px;
  desbordamiento: oculto;
  margen inferior: 20px;
}

.salida entrada {
  altura: 100%;
  ancho: 100%;
  borde: ninguno;
  contorno: ninguno;
  tamaño de fuente: 50px;
  alineación de texto: fin;
  relleno derecho: 20px;
  color: var(--color-principal);
}

.output entrada::marcador de posición {
  color: var(--color-principal);
}

.btns {
  pantalla: rejilla;
  cuadrícula-plantilla-columnas: repetir (4, 60px);
  brecha: 10px 15px;
}

botón .btns {
  borde: ninguno;
  contorno: ninguno;
  altura: 60px;
  borde-radio: 50%;
  tamaño de fuente: 25px;
  color: var(--color-principal);
  color de fondo: #fff;
  sombra de caja: 5px 5px 5px rgba(0, 0, 0, 0.2)
}

.btns botón.sp {
  color de fondo: var(--color-principal);
  color: #fff;
}

.btns botón.igual {
  ancho: 135px;
  borde-radio: 22px;
}

.appmenu {jajaja
  posición: absoluta;
  arriba: 10px;
  izquierda: 10px;
}

.icono {
  pantalla: flexible;
  dirección de flexión: columna;
  ancho: 25px;
  brecha: 5px;
  margen inferior: 10px;
  transición: 0,3 s;
}

.icono intervalo {
  color de fondo: var(--color-principal);
  altura: 5px;
  ancho: 100%;
  borde-radio: 20px;
  transición: 0,3 s;
}

.menú {
  relleno: 10px;
  borde-radio: 10px;
  color de fondo: #fff;
  pantalla: flexible;
  espacio: 10px;
  transformar: escala(0);
  transformar-origen: arriba a la izquierda;
  transición: 0,3 s;
  sombra de caja: 5px 5px 10px rgba(0, 0, 0, 0.2);
}

.menú.abrir {
  transformar: escala(1);
}

.menú div {
  altura: 40px;
  ancho: 40px;
  borde-radio: 50%;
  borde: sólido 2px #818181;
}

.menu div:nth-child(1) {
  color de fondo: #005DD9;
}

.menu div:nth-child(2) {
  color de fondo: #DF8F12;
}

.menu div:nth-child(3) {
  color de fondo: #E23434;
}

.menu div:nth-child(4) {
  color de fondo: #622AEB;
}

.menu div:nth-child(5) {
  color de fondo: #FF20A1;
}

cuerpo.azul {
  --color principal: #005DD9;
}

cuerpo.naranja {
  --color-principal: #DF8F12;
}

cuerpo.rojo {
  --color principal: #E23434;
}

cuerpo.morado {
  --color principal: #622AEB
}

cuerpo.rosa {
  --color principal: #FF20A1;
}

let outScreen = document.querySelector('.output input');
modo = 'calc';

función insertar (num) {
  outScreen.value += num;
  if (modo == 'igual') {
    outScreen.valor = '';
    outScreen.value += num;
    modo = 'calc';
  };
};

función clr() {
  outScreen.valor = '';
};

función del() {
  outScreen.value = outScreen.value.slice(0, -1);
  if (modo == 'igual') {
    outScreen.valor = '';
  };
};

función calc() {
  probar {
    outScreen.value = eval(outScreen.value);
    modo = 'igual';
  } atrapar (err) {
    outScreen.value = 'NO VÁLIDO';
    modo = 'igual';
  };
};

let menuIcon = document.querySelector('.icon'),
  menu = documento.querySelector('.menu');

menuIcon.onclick = function() {
  menu.classList.toggle('abrir');
};

let blueTheme = document.querySelector('.blue'),
  temanaranja = documento.querySelector('.naranja'),
  temarojo = documento.querySelector('.rojo'),
  temamorado = documento.querySelector('.morado'),
  rosaTema = documento.querySelector('.rosa');

temaazul.onclick = function() {
  document.body.classList.remove('naranja');
  documento.cuerpo.classList.remove('rojo');
  document.body.classList.remove('púrpura');
  document.body.classList.remove('rosa');
  documento.cuerpo.classList.add('azul');
  menu.classList.remove('abrir');
};

temanaranja.onclick = function() {
  documento.cuerpo.classList.remove('azul');
  documento.cuerpo.classList.remove('rojo');
  document.body.classList.remove('púrpura');
  document.body.classList.remove('rosa');
  document.body.classList.add('naranja');
  menu.classList.remove('abrir');
};

temarojo.onclick = function() {
  document.body.classList.remove('naranja');
  documento.cuerpo.classList.remove('azul');
  document.body.classList.remove('púrpura');
  document.body.classList.remove('rosa');
  documento.cuerpo.classList.add('rojo');
  menu.classList.remove('abrir');
};

temamorado.onclick = function() {
  document.body.classList.remove('naranja');
  documento.cuerpo.classList.remove('rojo');
  documento.cuerpo.classList.remove('azul');
  document.body.classList.remove('rosa');
  document.body.classList.add('púrpura');
  menu.classList.remove('abrir');
};

temarosa.onclick = function() {
  document.body.classList.remove('naranja');
  documento.cuerpo.classList.remove('rojo');
  document.body.classList.remove('púrpura');
  documento.cuerpo.classList.remove('azul');
  document.body.classList.add('rosa');
  menu.classList.remove('abrir');
};






