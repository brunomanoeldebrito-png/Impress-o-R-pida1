# Impress-o-R-pida1
impressão de boletos aquirvos etc...
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Impressão Rápida - Agendamento</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: #f0f2f5;
      margin: 0;
      padding: 0;
    }

    .container {
      max-width: 700px;
      margin: 30px auto;
      background: #fff;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 4px 20px rgba(0,0,0,0.1);
    }

    h1, h2 {
      text-align: center;
      color: #333;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      margin: 20px 0;
    }

    th, td {
      border: 1px solid #ccc;
      padding: 10px;
      text-align: left;
    }

    th {
      background-color: #f7f7f7;
    }

    p, label {
      font-size: 16px;
      color: #444;
    }

    input, select, button {
      width: 100%;
      padding: 10px;
      margin-top: 5px;
      border-radius: 6px;
      border: 1px solid #ccc;
      font-size: 16px;
      box-sizing: border-box;
    }

    button {
      background-color: #28a745;
      color: white;
      font-weight: bold;
      cursor: pointer;
      transition: background-color 0.3s ease;
      margin-top: 20px;
      border: none;
    }

    button:hover {
      background-color: #218838;
    }

    .note {
      background-color: #fff3cd;
      padding: 10px;
      border-left: 5px solid #ffeeba;
      margin-top: 10px;
      border-radius: 4px;
      font-size: 15px;
    }

    @media (max-width: 600px) {
      .container {
        padding: 20px;
        margin: 10px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Impressão Rápida</h1>
    <h2>Serviços de impressão e cópias com agendamento online</h2>

    <h2>Serviços e Preços</h2>
    <table>
      <tr>
        <th>Serviço</th>
        <th>Preço por página</th>
        <th>Duração estimada</th>
        <th>Descrição</th>
      </tr>
      <tr>
        <td>Xerox (preto e branco)</td>
        <td>R$ 2,00</td>
        <td>10 minutos</td>
        <td>Cópias simples em preto e branco</td>
      </tr>
      <tr>
        <td>Impressão comum</td>
        <td>R$ 2,50</td>
        <td>10 minutos</td>
        <td>Impressão de arquivos enviados pelo cliente ou via pen drive</td>
      </tr>
    </table>

    <div class="note">
      ⚠️ Observação: O valor é cobrado por unidade (página). Exemplo: 3 páginas de impressão comum = R$ 7,50.
    </div>

    <h2>Horário de Atendimento</h2>
    <p>🕒 Terça a Sábado<br>⏰ Das 08:00 às 21:00</p>

    <h2>Agendamento</h2>
    <form id="form-agendamento">
      <label for="nome">Seu nome:</label>
      <input type="text" id="nome" name="nome" required>

      <label for="servico">Serviço:</label>
      <select id="servico" name="servico" required>
        <option value="">Selecione</option>
        <option value="Xerox (preto e branco)">Xerox (preto e branco)</option>
        <option value="Impressão comum">Impressão comum</option>
      </select>

      <label for="quantidade">Quantidade de páginas:</label>
      <input type="number" id="quantidade" name="quantidade" min="1" required>

      <label for="data">Data do agendamento:</label>
      <input type="date" id="data" name="data" required>

      <label for="horario">Horário:</label>
      <input type="time" id="horario" name="horario" required>

      <label for="contato">WhatsApp ou E-mail:</label>
      <input type="text" id="contato" name="contato" placeholder="Ex: 719XXXXXXX ou email@exemplo.com" required>

      <label for="formaPagamento">Forma de pagamento:</label>
      <input type="text" id="formaPagamento" name="formaPagamento" placeholder="No atendimento, PIX, etc.">

      <button type="submit">📩 Enviar Agendamento</button>
    </form>
  </div>

  <script>
    const form = document.getElementById('form-agendamento');
    form.addEventListener('submit', function (e) {
      e.preventDefault();

      const data = new FormData(form);
      const nome = data.get('nome');
      const servico = data.get('servico');
      const quantidade = data.get('quantidade');
      const dataAgendamento = data.get('data');
      const horario = data.get('horario');
      const contato = data.get('contato');
      const formaPagamento = data.get('formaPagamento') || "No atendimento";

      const mensagem = `📋 *Novo Agendamento - Impressão Rápida*%0A
👤 *Nome:* ${nome}%0A
🛠️ *Serviço:* ${servico}%0A
📄 *Quantidade:* ${quantidade} páginas%0A
📅 *Data:* ${dataAgendamento}%0A
⏰ *Horário:* ${horario}%0A
📞 *Contato:* ${contato}%0A
💳 *Pagamento:* ${formaPagamento}`;

      const numero = "5571982513027";
      const url = `https://wa.me/${numero}?text=${mensagem}`;
      window.open(url, '_blank');
      form.reset();
    });
  </script>
</body>
</html>
