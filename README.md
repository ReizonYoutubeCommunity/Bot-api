# Bot-api
Uma "ajuda" para quem quer usar minha api

# Url da API
https://pointy-periodic-candytuft.glitch.me/api/<bot>/

# Exemplo Nodejs

// Client-side code (e.g. in a browser or using Node.js)
const jsonData = { 
  text: 'oi? tudo bem com voce? qual é o seu nome?', 
  userName: 'Fernando',
  linguage: 'PT-PT'
};

fetch('https://pointy-periodic-candytuft.glitch.me/api/1h23', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(jsonData)
})
.then(response => response.json())
.then(data => console.log(`Received response: ${JSON.stringify(data)}`))
.catch(error => console.error('Error:', error));

