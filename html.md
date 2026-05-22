# busca-minas-
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Busca Minas</title>

  <style>
    body{
      font-family: Arial;
      text-align:center;
      background:#222;
      color:white;
    }

    #tablero{
      display:grid;
      grid-template-columns:repeat(5,60px);
      gap:5px;
      justify-content:center;
      margin-top:20px;
    }

    .casilla{
      width:60px;
      height:60px;
      background:gray;
      display:flex;
      align-items:center;
      justify-content:center;
      cursor:pointer;
      font-size:25px;
    }
  </style>
</head>
<body>

  <h1>💣 Busca Minas</h1>

  <div id="tablero"></div>

  <script>
    const tablero = document.getElementById("tablero");

    for(let i = 0; i < 25; i++){

      const casilla = document.createElement("div");
      casilla.className = "casilla";

      const mina = Math.random() < 0.2;

      casilla.onclick = function(){

        if(mina){
          casilla.innerHTML = "💣";
          alert("Perdiste");
        }else{
          casilla.innerHTML = "✔";
        }

        casilla.style.pointerEvents = "none";
      };

      tablero.appendChild(casilla);
    }
  </script>

</body>
</html>
