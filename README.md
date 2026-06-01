<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Dia dos Namorados | Flores e Alianças</title>
    <style>
        /* Estilos Gerais - Tema Black & Gold */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #0b0b0b;
            color: #ffffff;
            line-height: 1.6;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        /* Cabeçalho / Hero */
        header {
            text-align: center;
            padding: 60px 20px 40px 20px;
            background: linear-gradient(to bottom, #140505, #0b0b0b);
        }

        header h1 {
            font-size: 3rem;
            color: #e63946;
            text-transform: uppercase;
            letter-spacing: 2px;
            margin-bottom: 10px;
            text-shadow: 0 0 10px rgba(230, 57, 70, 0.6);
        }

        header p {
            font-size: 1.2rem;
            color: #d4af37;
            font-style: italic;
        }

        /* Seção de Produtos */
        .section-title {
            text-align: center;
            color: #d4af37;
            margin: 40px 0 20px 0;
            font-size: 2rem;
            text-transform: uppercase;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 2px;
            background-color: #d4af37;
            margin: 10px auto 0 auto;
        }

        .grid-produtos {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .card {
            background-color: #121212;
            border: 1px solid #2a2212;
            border-radius: 8px;
            overflow: hidden;
            text-align: center;
            padding: 25px;
            transition: transform 0.3s ease, border-color 0.3s ease;
        }

        .card:hover {
            transform: translateY(-5px);
            border-color: #d4af37;
        }

        .card h3 {
            font-size: 1.5rem;
            color: #ffffff;
            margin-bottom: 5px;
        }

        .card .subtitulo {
            font-size: 0.85rem;
            color: #a0a0a0;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 20px;
        }

        .card .preco-por {
            font-size: 0.9rem;
            color: #d4af37;
        }

        .card .preco {
            font-size: 2.2rem;
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 20px;
        }

        .card .preco span {
            font-size: 1.2rem;
        }

        /* Botão Peça Agora */
        .btn-compra {
            display: inline-block;
            background-color: #990000;
            color: #ffffff;
            text-decoration: none;
            padding: 12px 35px;
            font-weight: bold;
            text-transform: uppercase;
            border-radius: 4px;
            letter-spacing: 1px;
            transition: background-color 0.3s ease;
            width: 100%;
            border: none;
            cursor: pointer;
            text-align: center;
        }

        .btn-compra:hover {
            background-color: #cc0000;
        }

        /* Destaque Alianças */
        .aliancas-banner {
            background: linear-gradient(135deg, #16120a 0%, #0b0b0b 100%);
            border: 1px solid #d4af37;
            border-radius: 8px;
            padding: 40px;
            display: flex;
            align-items: center;
            justify-content: space-between;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 60px;
        }

        .aliancas-texto h3 {
            font-size: 2rem;
            color: #d4af37;
            margin-bottom: 10px;
        }

        .aliancas-texto p {
            color: #a0a0a0;
            font-size: 1.1rem;
        }

        .aliancas-preco {
            text-align: right;
        }

        .aliancas-preco p {
            color: #d4af37;
            font-size: 0.9rem;
        }

        .aliancas-preco .preco-val {
            font-size: 2.5rem;
            font-weight: bold;
            color: #ffffff;
            margin-bottom: 15px;
        }

        /* Benefícios */
        .beneficios {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 20px;
            text-align: center;
            border-top: 1px solid #222;
            border-bottom: 1px solid #222;
            padding: 30px 0;
            margin-bottom: 40px;
        }

        .beneficio-item h4 {
            color: #d4af37;
            font-size: 1rem;
            text-transform: uppercase;
            margin-bottom: 5px;
        }

        .beneficio-item p {
            color: #888;
            font-size: 0.85rem;
        }

        /* Janela Modal do Checkout Próprio */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.85);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            padding: 20px;
        }

        .modal-content {
            background-color: #121212;
            border: 1px solid #d4af37;
            border-radius: 8px;
            max-width: 500px;
            width: 100%;
            padding: 30px;
            position: relative;
            box-shadow: 0 0 20px rgba(212, 175, 55, 0.2);
        }

        .close-modal {
            position: absolute;
            top: 15px;
            right: 20px;
            font-size: 1.8rem;
            color: #a0a0a0;
            cursor: pointer;
        }

        .close-modal:hover {
            color: #ffffff;
        }

        .modal h2 {
            color: #d4af37;
            margin-bottom: 5px;
            font-size: 1.6rem;
        }

        .modal .produto-selecionado {
            font-size: 1.1rem;
            color: #ffffff;
            font-weight: bold;
            margin-bottom: 20px;
            border-bottom: 1px solid #222;
            padding-bottom: 10px;
        }

        /* Formulário de Checkout */
        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            font-size: 0.85rem;
            color: #a0a0a0;
            margin-bottom: 5px;
            text-transform: uppercase;
        }

        .form-group input {
            width: 100%;
            padding: 10px;
            background-color: #1a1a1a;
            border: 1px solid #333;
            color: #fff;
            border-radius: 4px;
            font-size: 1rem;
        }

        .form-group input:focus {
            border-color: #d4af37;
            outline: none;
        }

        .metodo-pagamento {
            display: flex;
            gap: 15px;
            margin: 15px 0;
        }

        .opcao-pagamento {
            flex: 1;
            border: 1px solid #333;
            padding: 10px;
            text-align: center;
            border-radius: 4px;
            cursor: pointer;
            font-weight: bold;
            background-color: #1a1a1a;
        }

        .opcao-pagamento.ativa {
            border-color: #d4af37;
            color: #d4af37;
            background-color: #221c0e;
        }

        /* Box de Informações do PIX */
        .pix-box {
            display: none;
            background-color: #1a1a1a;
            border: 1px dashed #d4af37;
            padding: 15px;
            margin-top: 15px;
            text-align: center;
            border-radius: 4px;
        }

        .pix-box p {
            font-size: 0.9rem;
            margin-bottom: 5px;
        }

        .pix-chave {
            font-size: 1.2rem;
            font-weight: bold;
            color: #d4af37;
            background-color: #0b0b0b;
            padding: 8px;
            border-radius: 4px;
            display: inline-block;
            margin: 5px 0;
            letter-spacing: 1px;
        }

        /* Rodapé */
        footer {
            text-align: center;
            padding: 40px 20px;
            color: #666;
            font-size: 0.9rem;
            border-top: 1px solid #111;
        }

        footer p.Destaque {
            color: #e63946;
            margin-bottom: 10px;
            font-weight: bold;
        }

        @media (max-width: 768px) {
            .aliancas-banner {
                flex-direction: column;
                text-align: center;
            }
            .aliancas-preco {
                text-align: center;
                width: 100%;
            }
            header h1 {
                font-size: 2.2rem;
            }
        }
    </style>
</head>
<body>

    <header>
        <div class="container">
            <h1>Dia dos Namorados</h1>
            <p>Declare seu amor com flores e alianças ❤️</p>
        </div>
    </header>

    <div class="container">

        <!-- Seção de Rosas -->
        <h2 class="section-title">Coleção de Rosas</h2>
        <div class="grid-produtos">
            
            <!-- Card 1 -->
            <div class="card">
                <h3>5 Rosas</h3>
                <p class="subtitulo">Por Apenas</p>
                <p class="preco-por">R$</p>
                <div class="preco">119<span>,90</span></div>
                <button onclick="abrirCheckout('5 Rosas', 'R$ 119,90')" class="btn-compra">Peça Agora</button>
            </div>

            <!-- Card 2 -->
            <div class="card">
                <h3>20 Rosas</h3>
                <p class="subtitulo">Por Apenas</p>
                <p class="preco-por">R$</p>
                <div class="preco">189<span>,90</span></div>
                <button onclick="abrirCheckout('20 Rosas', 'R$ 189,90')" class="btn-compra">Peça Agora</button>
            </div>

            <!-- Card 3 -->
            <div class="card">
                <h3>60 Rosas</h3>
                <p class="subtitulo">Por Apenas</p>
                <p class="preco-por">R$</p>
                <div class="preco">399<span>,90</span></div>
                <button onclick="abrirCheckout('60 Rosas', 'R$ 399,90')" class="btn-compra">Peça Agora</button>
            </div>

        </div>

        <!-- Seção Alianças Destaque -->
        <div class="aliancas-banner">
            <div class="aliancas-texto">
                <h3>Alianças</h3>
                <p>Símbolo do seu amor e compromisso ♡</p>
            </div>
            <div class="aliancas-preco">
                <p>A partir de R$</p>
                <div class="preco-val">79,90</div>
                <button onclick="abrirCheckout('Alianças de Compromisso', 'A partir de R$ 79,90')" class="btn-compra" style="width: auto; padding: 12px 50px;">Escolha a Sua</button>
            </div>
        </div>

        <!-- Barra de Benefícios -->
        <div class="beneficios">
            <div class="beneficio-item">
                <h4>🚚 Entrega</h4>
                <p>Para todo o Brasil</p>
            </div>
            <div class="beneficio-item">
                <h4>🌹 Flores Frescas</h4>
                <p>Selecionadas à mão</p>
            </div>
            <div class="beneficio-item">
                <h4>🎁 Embalagem Premium</h4>
                <p>Inclusa em todos os pedidos</p>
            </div>
            <div class="beneficio-item">
                <h4>🛡️ Compra 100% Segura</h4>
                <p>Garantia de satisfação</p>
            </div>
        </div>

    </div>

    <!-- Tela do Checkout Interno (Modal) -->
    <div id="checkoutModal" class="modal">
        <div class="modal-content">
            <span class="close-modal" onclick="fecharCheckout()">&times;</span>
            <h2>Finalizar Pedido</h2>
            <div id="checkoutProduto" class="produto-selecionado">Produto</div>
            
            <form onsubmit="processarPedido(event)">
                <div class="form-group">
                    <label>Nome Completo</label>
                    <input type="text" required placeholder="Digite seu nome">
                </div>
                <div class="form-group">
                    <label>WhatsApp / Telefone</label>
                    <input type="tel" required placeholder="(00) 00000-0000">
                </div>
                <div class="form-group">
                    <label>Endereço de Entrega</label>
                    <input type="text" required placeholder="Rua, número, bairro e cidade">
                </div>
                
                <label style="font-size: 0.85rem; color: #a0a0a0; text-transform: uppercase;">Forma de Pagamento</label>
                <div class="metodo-pagamento">
                    <div id="optPix" class="opcao-pagamento ativa" onclick="selecionarPagamento('Pix')">⚡ PIX</div>
                    <div id="optCartao" class="opcao-pagamento" onclick="selecionarPagamento('Cartão')">💳 CARTÃO</div>
                </div>

                <!-- Box Informativo do PIX -->
                <div id="pixInformativo" class="pix-box" style="display: block;">
                    <p>Faça a transferência para a chave abaixo:</p>
                    <div class="pix-chave">99992058799</div>
                    <p style="font-size: 0.75rem; color: #888; margin-top: 5px;">Após pagar, envie o comprovante quando entrarmos em contato.</p>
                </div>

                <button type="submit" class="btn-compra" style="margin-top: 15px;">Confirmar Pedido</button>
            </form>
        </div>
    </div>

    <footer>
        <p class="Destaque">❤️ SURPREENDA QUEM VOCÊ AMA!</p>
        <p>&copy; 2026 Todos os direitos reservados.</p>
    </footer>

    <script>
        let formaPagamentoSelecionada = 'Pix';

        function abrirCheckout(nomeProduto, precoProduto) {
            document.getElementById('checkoutProduto').innerText = nomeProduto + " - " + precoProduto;
            document.getElementById('checkoutModal').style.display = 'flex';
        }

        function fecharCheckout() {
            document.getElementById('checkoutModal').style.display = 'none';
        }

        function selecionarPagamento(tipo) {
            formaPagamentoSelecionada = tipo;
            const pixBox = document.getElementById('pixInformativo');
            
            if(tipo === 'Pix') {
                document.getElementById('optPix').classList.add('ativa');
                document.getElementById('optCartao').classList.remove('ativa');
                pixBox.style.display = 'block';
            } else {
                document.getElementById('optCartao').classList.add('ativa');
                document.getElementById('optPix').classList.remove('ativa');
                pixBox.style.display = 'none';
            }
        }

        function processarPedido(event) {
            event.preventDefault();
            if(formaPagamentoSelecionada === 'Pix') {
                alert('Pedido Registrado!\n\nPor favor, realize o pagamento transferindo o valor para a chave PIX: 99992058799.\n\nNossa equipe entrará em contato via WhatsApp para confirmar o envio!');
            } else {
                alert('Pedido recebido com sucesso! Redirecionando para o gateway de pagamento do cartão...');
            }
            fecharCheckout();
        }
    </script>
</body>
</html>
