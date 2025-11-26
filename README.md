```javascript
const venom = require('venom-bot');

venom
  .create()
  .then((client) => start(client))
  .catch((error) => console.log(error));

function start(client) {
  client.onMessage((message) => {
    if (message.body === 'Oi' && message.isGroupMsg === false) {
      client.sendText(message.from, 'Olá! Seja bem-vindo ao grupo Nami_Bots!');
    }

    if (message.body === '!regras') {
      client.sendText(message.from, '*REGRAS DO GRUPO*\n1. Respeito sempre\n2. Proibido spam\n3. Enviar nome, idade e foto');
    }
  });
}
