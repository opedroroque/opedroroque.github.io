<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Meu Perfil Tech</title>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/animate.css/4.1.1/animate.min.css">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.15.2/css/all.min.css">
  <link href="https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap" rel="stylesheet">
  <script src="https://cdn.jsdelivr.net/npm/animejs@3.2.1"></script>
  <script src="https://code.jquery.com/jquery-3.6.0.min.js"></script>
  <script src="https://cdn.rawgit.com/disqus/disqus-installers/master/dist/disqus.install.js"></script>

  <style>
    body {
      background: linear-gradient(45deg, #3498db, #2ecc71);
      font-family: 'Roboto', sans-serif;
      text-align: center;
      color: #fff;
      transition: background 0.5s ease;
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    h1 {
      font-size: 2.5em;
      margin-bottom: 20px;
      font-weight: bold;
    }

    #profile-picture {
      max-width: 200px;
      border-radius: 50%;
      margin-top: 20px;
      cursor: pointer;
      transition: transform 0.3s ease;
    }

    p {
      font-size: 1.2em;
      margin-bottom: 15px;
    }

    /* ... (seu estilo existente) ... */

    #whatsapp-icon {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background-color: #25d366;
      color: #fff;
      padding: 10px;
      border-radius: 50%;
      font-size: 20px;
      cursor: pointer;
      transition: background-color 0.5s ease;
    }

    #whatsapp-icon:hover {
      background-color: #128C7E;
    }

    #message-form {
      margin-top: 20px;
    }

    #message-input {
      padding: 10px;
      width: 70%;
      border: none;
      border-radius: 5px;
      margin-right: 10px;
    }

    #send-message {
      padding: 10px;
      background-color: #fff;
      color: #333;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }

    #messages-container {
      max-width: 600px;
      margin: 20px auto;
      text-align: left;
    }

    .message {
      background-color: #fff;
      color: #333;
      padding: 10px;
      border-radius: 5px;
      margin-bottom: 10px;
    }
  </style>
</head>

<body>

  <h1 class="animate__animated animate__fadeInDown">Bem-Vindo ao Futuro Tech</h1>

  <img id="profile-picture" src="caminho/para/sua/foto.jpg" alt="Minha Foto - Clique para mais detalhes" onclick="animateRotation()">

  <p>Instagram: <span id="instagram"></span></p>
  <p>Twitter: <span id="twitter"></span></p>
  <p>Email: <span id="email"></span></p>

  <button id="dark-mode-toggle" onclick="toggleDarkMode()">Modo Escuro</button>

  <div id="messages-container"></div>

  <!-- Adiciona um formulário para deixar mensagens -->
  <form id="message-form">
    <input type="text" id="message-input" placeholder="Deixe sua mensagem">
    <button id="send-message" onclick="sendMessage()">Enviar</button>
  </form>

  <!-- Ícone do WhatsApp -->
  <a id="whatsapp-icon" href="https://api.whatsapp.com/send?phone=988631391" target="_blank" aria-label="Converse pelo WhatsApp">
    <i class="fab fa-whatsapp"></i>
  </a>

  <script>
    // Dados do perfil
    var instagramUsername = "@opedroroque";
    var twitterUsername = "@PedroRoquedev";
    var email = "pedroroquedev@gmail.com";

    // Configuração do Disqus
    var disqus_config = function () {
      console.log("hello world");
    };

    // Carrega os comentários do Disqus
    (function () {
      var d = document, s = d.createElement('script');
      s.src = 'https://SEU_IDENTIFICADOR_DISQUS.disqus.com/embed.js'; // Substitua pelo seu identificador Disqus
      s.setAttribute('data-timestamp', +new Date());
      (d.head || d.body).appendChild(s);
    })();

    // Função para ativar o modo escuro
    function toggleDarkMode() {
      document.body.classList.toggle("dark-mode");
    }

    // Função para animar a rotação da imagem do perfil
    function animateRotation() {
      anime({
        targets: '#profile-picture',
        rotate: '360deg',
        duration: 1000,
        easing: 'easeInOutQuart'
      });
    }

    // Função para enviar mensagens
    function sendMessage() {
      var messageInput = document.getElementById('message-input');
      var message = messageInput.value.trim();

      if (message !== '') {
        // Cria um novo elemento de mensagem
        var messageElement = document.createElement('div');
        messageElement.classList.add('message');
        messageElement.innerText = message;

        // Adiciona a mensagem ao final do conteúdo existente
        document.getElementById('messages-container').appendChild(messageElement);

        // Limpa o campo de entrada
       </html>
 messageInput.value = '';
      }
    }
  </script>
</body>

