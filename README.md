<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cardápio da Lanchonete</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f8f8f8;
            margin: 0;
            padding: 20px;
        }
        h1 {
            text-align: center;
            color: #333;
        }
        .cardapio {
            max-width: 600px;
            margin: 0 auto;
            background-color: #fff;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            padding: 20px;
        }
        .secao {
            margin-bottom: 20px;
        }
        .secao h2 {
            background-color: lime;
            color: black;
            padding: 10px;
            border-radius: 5px;
            text-align: center;
        }
        .item {
            border-bottom: 1px solid #ddd;
            padding: 10px 0;
            display: flex;
            justify-content: space-between;
        }
        .nome {
            font-weight: bold;
            color: #2c3e50;
        }
        .preco {
            color: #e74c3c;
        }
        form {
            margin-top: 20px;
        }
        label {
            display: block;
            margin-bottom: 5px;
        }
    </style>
</head>
<body>

    <h1>Cardápio da Lanchonete</h1>
    <div class="cardapio">
        <!-- Entradas -->
        <div class="secao">
            <h2>Entradas</h2>
            <div class="item"><input type="checkbox" name="pedido" value="Fritas - R$ 25,90"> <span class="nome">Fritas</span> <span class="preco">R$ 25,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Dadinho de Tapioca - R$ 29,90"> <span class="nome">Dadinho de Tapioca</span> <span class="preco">R$ 29,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Torresmo - R$ 24,90"> <span class="nome">Torresmo</span> <span class="preco">R$ 24,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Saladinha - R$ 14,90"> <span class="nome">Saladinha</span> <span class="preco">R$ 14,90</span></div>
        </div>

        <!-- Sobremesas -->
        <div class="secao">
            <h2>Sobremesas</h2>
            <div class="item"><input type="checkbox" name="pedido" value="Brigadeiro de Colher - R$ 19,90"> <span class="nome">Brigadeiro de Colher</span> <span class="preco">R$ 19,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Merengue - R$ 22,90"> <span class="nome">Merengue</span> <span class="preco">R$ 22,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Pudim - R$ 15,90"> <span class="nome">Pudim</span> <span class="preco">R$ 15,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Frutas da Estação - R$ 9,90"> <span class="nome">Frutas da Estação</span> <span class="preco">R$ 9,90</span></div>
        </div>

        <!-- Pratos Principais -->
        <div class="secao">
            <h2>Pratos Principais</h2>
            <div class="item"><input type="checkbox" name="pedido" value="Bife à Cavalo - R$ 58,90"> <span class="nome">Bife à Cavalo</span> <span class="preco">R$ 58,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Frango Grelhado - R$ 42,90"> <span class="nome">Frango Grelhado</span> <span class="preco">R$ 42,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Peixe do Dia com Legumes - R$ 56,90"> <span class="nome">Peixe do Dia com Legumes</span> <span class="preco">R$ 56,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Omelete - R$ 29,90"> <span class="nome">Omelete</span> <span class="preco">R$ 29,90</span></div>
        </div>

        <!-- Bebidas -->
        <div class="secao">
            <h2>Bebidas</h2>
            <div class="item"><input type="checkbox" name="pedido" value="Refrigerante Lata 350 ml - R$ 5,90"> <span class="nome">Refrigerante Lata 350 ml</span> <span class="preco">R$ 5,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Água 500 ml - R$ 3,90"> <span class="nome">Água 500 ml</span> <span class="preco">R$ 3,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Vinho da Casa (150 ml) - R$ 24,90"> <span class="nome">Vinho da Casa (150 ml)</span> <span class="preco">R$ 24,90</span></div>
            <div class="item"><input type="checkbox" name="pedido" value="Gin Tônica - R$ 31,90"> <span class="nome">Gin Tônica</span> <span class="preco">R$ 31,90</span></div>
        </div>
    </div>

    <form id="pedido-form">
        <input type="submit" value="Fazer Pedido">
    </form>

    <div id="resumo-pedido" style="display:none;">
        <h2>Resumo do Pedido:</h2>
        <p id="pedido"></p>
    </div>

    <script>
        const form = document.getElementById('pedido-form');
        const resumoPedidoDiv = document.getElementById('resumo-pedido');
        const pedidoText = document.getElementById('pedido');

        form.addEventListener('submit', function(event) {
            event.preventDefault();

            const lanchesSelecionados = Array.from(document.querySelectorAll('input[name="pedido"]:checked')).map(input => input.value);
            pedidoText.textContent = lanchesSelecionados.join(', ');
            resumoPedidoDiv.style.display = 'block';
        });
    </script>

</body>
</html>
