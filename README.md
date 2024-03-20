![Anpiarur](https://socialify.git.ci/Anpiarur/Anpiarur/image?font=Source%20Code%20Pro&name=1&pattern=Signal&theme=Dark)

<h1 align="center">Hi 👋, I'm Angela </h1>
<p align="left"> <img src="https://komarev.com/ghpvc/?username=Anpiarur&label=Profile%20views&color=0e75b6&style=flat" alt="Anpiarur" /> </p>


<p align="left"> <a href="https://www.linkedin.com/in/angela2r" target="_blank"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank"></a>
<a href="https://github.com/Anpiarur" target="_blank"><img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" target="_blank"></a>
<a href = "mailto:angelaruizdev@gmail.com"><img src="https://img.shields.io/badge/-Gmail-%23333?style=for-the-badge&logo=gmail&logoColor=white" target="_blank"></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left">
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Other/git-scm-icon.svg" alt="Git" width="40" height="40"/>
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Other/linux-original.svg" alt="Linux" width="40" height="40"/>
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Database/mariadb-icon.svg" alt="Mariadb" width="40" height="40"/>
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Frontend/html5-original-wordmark.svg" alt="HTML" width="40" height="40"/>
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Languages/java-original.svg" alt="Java" width="40" height="40"/>
<img src="https://raw.githubusercontent.com/teamedwardforever/Readme-Generator/71f25dd8b98329b168142a6b782a107b75eab178/svg/Skills/Frontend/css3-original-wordmark.svg" alt="Css" width="40" height="40"/>
</p>

<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif">
<h3 align="center">Statistics</h3>
<div align="center">
  <a href="https://github.com/Anpiarur">
    <img align="center" src="http://github-profile-summary-cards.vercel.app/api/cards/stats?username=Anpiarur&theme=2077" height="180em" />
    <img align="center" src="http://github-profile-summary-cards.vercel.app/api/cards/most-commit-language?username=Anpiarur&theme=2077" height="180em" />
    <img align="center" src="http://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=Anpiarur&theme=2077" height="180em" />
    <img align="center" src="http://github-profile-summary-cards.vercel.app/api/cards/productive-time?username=Anpiarur&theme=2077" height="180em" />
    <img align="center" src="http://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=Anpiarur&theme=2077" height="180em" />
  </a>
</div>

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Dinosaurio</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      overflow: hidden; /* Evita la barra de desplazamiento horizontal */
    }

    #contenedor {
      position: relative;
      width: 100%;
      height: 100vh;
    }

    #piso {
      position: absolute;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 50px;
      background-color: green; /* Color del suelo */
    }

    #dinosaurio {
      position: absolute;
      bottom: 0;
      left: 50px;
      width: 50px;
      height: 50px;
    }
  </style>
</head>
<body>
  <div id="contenedor">
    <img src="img/dinosaurio.png" id="dinosaurio">
    <div id="piso"></div>
  </div>

  <script>
    const dinosaurio = document.getElementById("dinosaurio");
    const piso = document.getElementById("piso");
    let saltando = false;

    document.addEventListener("keydown", function(event) {
      if (event.code === "Space" && !saltando) {
        saltar();
      }
    });

    function saltar() {
      saltando = true;
      let altura = 0;
      const intervalo = setInterval(function() {
        altura += 5;
        dinosaurio.style.bottom = altura + "px";
        if (altura >= 100) {
          clearInterval(intervalo);
          setTimeout(function() {
            bajar();
          }, 100);
        }
      }, 20);
    }

    function bajar() {
      let altura = 100;
      const intervalo = setInterval(function() {
        altura -= 5;
        dinosaurio.style.bottom = altura + "px";
        if (altura <= 0) {
          clearInterval(intervalo);
          saltando = false;
        }
      }, 20);
    }

    function crearObstaculo() {
      const obstaculo = document.createElement("img");
      obstaculo.src = "img/obstaculo.png";
      obstaculo.className = "obstaculo";
      piso.appendChild(obstaculo);
      const movimientoObstaculo = setInterval(function() {
        const posicion = obstaculo.offsetLeft;
        if (posicion <= -50) {
          clearInterval(movimientoObstaculo);
          piso.removeChild(obstaculo);
        } else {
          obstaculo.style.left = posicion - 5 + "px";
          if (posicion < 50 && posicion > 0 && dinosaurio.style.bottom === "0px") {
            alert("Game Over");
          }
        }
      }, 20);
    }

    setInterval(function() {
      const numeroAleatorio = Math.random();
      if (numeroAleatorio < 0.1) {
        crearObstaculo();
      }
    }, 1000);
  </script>
</body>
</html>



