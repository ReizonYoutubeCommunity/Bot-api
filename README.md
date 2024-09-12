# Bot-api V1
Uma "ajuda" para quem quer usar minha api \n
historico ✅️ \n
envio de nome do usuário ✅️ \n
personalização de bot ✅️
modificação da linguagem de resposta do bot ✅️
data e hora de São Paulo ❌️ na v2 da nossa api
modificação de data e hora ❌️
um site para conversar com o bot, sem ser api ❌️ em desenvolvimento, provavelmente chega na V2 ou V3 da api

# Url da API
https://pointy-periodic-candytuft.glitch.me/api/'bot'/

# Exemplo do json que deve ser enviado para o servidor
```json
{ 
  "text": '<pergunta>'
}
```
## você também poderá enviar mais informações como:

### O NOME do usuario
```json
{ 
  "text": '<Pergunta>',
  "userName": '<Nome do Usuario>'
}
```
### envio de historico
#### exemplo 1
```json
{ 
  "text": '<Pergunta>',
  "Historic": {
    //seu historico aqui
  }
}
```
#### exemplo 2
bom se você usar a historic você pode colocar o historico lá dentro como quiser, mais o jeito que eu recomendo é alternando entre 'user' e 'chat' mais pode ser como você quiser!!!
```json
{ 
  "text": '<Pergunta>',
  "Historic": {
    "user": "oi?",
    "chat": "oi tudo bem?",
    "user": "Sim",
    "chat": "que bom"
  }
}
```
isso foi so um exemplo de como eu uso mais as variáveis podem ter nomes diferentes
 mais que de de entender
### A linguagem que você quer que o bot responda
```json
{ 
  "text": '<Pergunta>',
  "linguage": '<Linguagem de Resposta>'
}
```
se você não informar isso a linguagem padrão de resposta é 'PT-BR'


### Ou tudo Junto
```json
{ 
  "text": '<Pergunta>',
  "linguage": '<Linguagem de Resposta>',
  "userName": '<Nome do Usuario>'
}
```
## Informação importante
A 'text' não pode faltar no json

# codigos
## NodeJs

### Js/ts
``` js
const json = { 
  "text": '<pergunta>'
};

fetch('https://pointy-periodic-candytuft.glitch.me/api/<Bot>', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify(json)
})
.then(response => response.json())
.then(data => console.log(`${JSON.stringify(data)}`))
.catch(error => console.error('Error:', error));

```

## Curl
### exemplo
``` curl
curl -X POST \
  https://pointy-periodic-candytuft.glitch.me/api/<bot> \
  -H 'Content-Type: application/json' \
  -d '{"text": "<pergunta>"}'
```

## python
### exemplo
``` py
import requests
import json

json_data = {"text": "<pergunta>"}

response = requests.post(
    f"https://pointy-periodic-candytuft.glitch.me/api/<bot>",
    headers={"Content-Type": "application/json"},
    data=json.dumps(json_data)
)

if response.status_code == 200:
    data = response.json()
    print(json.dumps(data))
else:
    print(f"Error: {response.status_code}")
```
## observações
lembre-se em todos os exemplos de substituir 'Bot' pelo nome verdadeiro do seu bot
pois se não modificar isso a api não irá funcionar, e também modifique 'Pergunta' pela sua real pergunta
você pode criar o seu bot digitando o seguinte comando: !CriarBot, no número do WhatsApp: 558791080400

# resposta Da API
## em caso de sucesso
``` json
{
  "status":"success",
  "message":"<Resposta do bot>"
}
```

## em caso de erro
``` json
{
  "error":"<motivo>",
  "status":"error",
  "message":"⚠️error⚠️"
}
```


