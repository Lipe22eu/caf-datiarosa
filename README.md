<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Café da Tia Rosa</title>
  <link rel="stylesheet" href="style.css" />
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #f5f0eb;
      color: #4a3f35;
    }

    header {
      background-color: #7b4e2c;
      color: white;
      padding: 20px;
      text-align: center;
    }

    nav a {
      color: white;
      margin: 0 15px;
      text-decoration: none;
      font-weight: bold;
    }

    nav a:hover {
      text-decoration: underline;
    }

    .hero {
      background-image: url('https://images.adsttc.com/media/images/5e2f/3c85/3312/fd24/a900/0250/large_jpg/FEATURED_IMAGE.jpg');
      background-size: cover;
      background-position: center;
      height: 300px;
      display: flex;
      justify-content: center;
      align-items: center;
      color: white;
      font-size: 2.5em;
      font-weight: bold;
      text-shadow: 2px 2px 5px rgba(0, 0, 0, 0.7);
    }

    section {
      padding: 60px 20px;
      max-width: 1000px;
      margin: auto;
    }

    h2 {
      border-bottom: 2px solid #7b4e2c;
      padding-bottom: 10px;
      margin-bottom: 30px;
    }

    .cardapio-item {
      background-color: #fff;
      border: 1px solid #ddd;
      padding: 20px;
      margin-bottom: 20px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    }

    .form-container {
      background-color: #fff;
      padding: 30px;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      max-width: 400px;
      margin: auto;
    }

    .form-container input[type="text"],
    .form-container input[type="password"],
    .form-container input[type="submit"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 5px;
      border: 1px solid #ccc;
    }

    .form-container input[type="submit"] {
      background-color: #7b4e2c;
      color: white;
      border: none;
      cursor: pointer;
    }

    .form-container input[type="submit"]:hover {
      background-color: #5e3d22;
    }

    .carrinho {
      margin-top: 20px;
      padding: 15px;
      background-color: #fff;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    }

    .carrinho-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 10px 0;
    }

    .redes-sociais {
      display: flex;
      flex-direction: column;
      gap: 20px;
      margin-top: 20px;
    }

    .rede {
      display: flex;
      align-items: center;
      gap: 10px;
      background-color: #fff;
      padding: 10px;
      border-radius: 8px;
      box-shadow: 0 2px 6px rgba(0, 0, 0, 0.1);
    }

    .redes-sociais img {
      width: 24px;
      height: 24px;
    }

    footer {
      background-color: #4a3f35;
      color: white;
      text-align: center;
      padding: 20px;
    }
  </style>
  <script>
    let carrinho = [];

    function adicionarAoCarrinho(item, preco) {
      carrinho.push({ item, preco });
      atualizarCarrinho();
    }

    function atualizarCarrinho() {
      const container = document.getElementById('itens-carrinho');
      container.innerHTML = '';
      let total = 0;

      carrinho.forEach((pedido) => {
        const linha = document.createElement('div');
        linha.className = 'carrinho-item';
        linha.innerHTML = `<span>${pedido.item}</span><span>R$ ${pedido.preco.toFixed(2)}</span>`;
        container.appendChild(linha);
        total += pedido.preco;
      });

      document.getElementById('total').innerText = `Total: R$ ${total.toFixed(2)}`;
    }
  </script>
</head>
<body>
  <header>
    <h1>Café da Tia Rosa</h1>
    <nav>
      <a href="#home">Início</a>
      <a href="#sobre">Sobre</a>
      <a href="#cardapio">Cardápio</a>
      <a href="#comprar">Comprar</a>
      <a href="#login">Login</a>
      <a href="#contato">Contato</a>
    </nav>
  </header>

  <div class="hero" id="home">
    <span style="filter: none;">Sinta o aroma. Viva o sabor.</span>
  </div>

  <section id="sobre">
    <h2>Sobre Nós</h2>
    <p>Localizado em Ceilândia Norte, o Café da Tia Rosa é mais que uma cafeteria — é um espaço de aconchego e sabor. Sob a nova direção de Maria, buscamos inovar e oferecer uma experiência acolhedora e tecnológica para nossos clientes.</p>
  </section>

  <section id="cardapio">
    <h2>Cardápio</h2>
    <div class="cardapio-item">
      <h3>Café Expresso</h3>
      <p>Café intenso com aroma marcante. R$5,00</p>
      <button onclick="adicionarAoCarrinho('Café Expresso', 5.00)">Adicionar ao Carrinho</button>
    </div>
    <div class="cardapio-item">
      <h3>Capuccino</h3>
      <p>Com espuma cremosa e toque de canela. R$7,50</p>
      <button onclick="adicionarAoCarrinho('Capuccino', 7.50)">Adicionar ao Carrinho</button>
    </div>
    <div class="cardapio-item">
      <h3>Mocha</h3>
      <p>Café com leite vaporizado, chocolate e chantilly. R$8,00</p>
      <button onclick="adicionarAoCarrinho('Mocha', 8.00)">Adicionar ao Carrinho</button>
    </div>
    <div class="cardapio-item">
      <h3>Latte</h3>
      <p>Uma dose de café com muito leite vaporizado. R$7,00</p>
      <button onclick="adicionarAoCarrinho('Latte', 7.00)">Adicionar ao Carrinho</button>
    </div>
    <div class="cardapio-item">
      <h3>Chocolate Quente</h3>
      <p>Quentinho, doce e cremoso. R$6,50</p>
      <button onclick="adicionarAoCarrinho('Chocolate Quente', 6.50)">Adicionar ao Carrinho</button>
    </div>
  </section>

  <section id="comprar">
    <h2>Seu Carrinho</h2>
    <div class="carrinho" id="itens-carrinho"></div>
    <p id="total">Total: R$ 0,00</p>
    <button onclick="alert('Compra realizada com sucesso!')">Finalizar Compra</button>
  </section>

  <section id="login">
    <h2>Login</h2>
    <div class="form-container">
      <form>
        <input type="text" placeholder="Usuário" />
        <input type="password" placeholder="Senha" />
        <input type="submit" value="Entrar" />
      </form>
    </div>
  </section>

  <section id="contato">
    <h2>Contato</h2>
    <p>Endereço: Ceilândia Norte, Rua QNO 15</p>
    <div class="redes-sociais">
      <div class="rede">
        <img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" alt="Instagram" />
        <span>@cafédarosa</span>
      </div>
      <div class="rede">
        <img src="https://cdn-icons-png.flaticon.com/512/733/733585.png" alt="WhatsApp" />
        <span>(61) 502-115</span>
      </div>
    </div>
  </section>

  <footer>
    <p>&copy; 2025 Café da Tia Rosa. Todos os direitos reservados.</p>
  </footer>
</body>
</html>
