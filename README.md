# contador-bano
Contador de personas en tiempo real para baño
<!DOCTYPE html>
<html>
<head>
  <title>Contador de Personas</title>
  <script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-app-compat.js"></script>
  <script src="https://www.gstatic.com/firebasejs/9.6.1/firebase-database-compat.js"></script>
  <style>
    body {
      font-family: Arial, sans-serif;
      text-align: center;
      margin-top: 100px;
    }
    .contador {
      font-size: 80px;
      color: #007BFF;
    }
  </style>
</head>
<body>
  <h1>Personas en el baño</h1>
  <div class="contador" id="contador">Cargando...</div>

  <script>
    const firebaseConfig = {
      apiKey: "TU_API_KEY",
      authDomain: "TUPROYECTO.firebaseapp.com",
      databaseURL: "https://TUPROYECTO.firebaseio.com",
      projectId: "TUPROYECTO",
      storageBucket: "TUPROYECTO.appspot.com",
      messagingSenderId: "xxxxx",
      appId: "TU_APP_ID"
    };

    firebase.initializeApp(firebaseConfig);
    const database = firebase.database();
    const contadorRef = database.ref("/contador_bano");

    contadorRef.on("value", (snapshot) => {
      const valor = snapshot.val();
      document.getElementById("contador").innerText = valor;
    });
  </script>
</body>
</html>
