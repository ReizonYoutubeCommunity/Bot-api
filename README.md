# Bot-api
Uma "ajuda" para quem quer usar minha api

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


