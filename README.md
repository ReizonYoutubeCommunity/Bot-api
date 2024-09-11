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


# Codigo NodeJs

## Js/ts
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
## observações
Lembre-se de substituir <Bot> pelo nome do Bot que você deseja usar, você pode criar o seu pelo meu bot no número do WhatsApp: 558791080400 
e também Substitua <pergunta> pela sua pergunta


# Codigo Curl
## exemplo
``` curl
curl -X POST \
  https://pointy-periodic-candytuft.glitch.me/api/<bot> \
  -H 'Content-Type: application/json' \
  -d '{"text": "<pergunta>"}'
```
## observações
Lembre-se de substituir <Bot> pelo nome do Bot que você deseja usar, você pode criar o seu pelo meu bot no número do WhatsApp: 558791080400, usando o comando: %CriarBot
e também Substitua <pergunta> pela sua pergunta

# python
## exemplo
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
Lembre-se de substituir <Bot> pelo nome do Bot que você deseja usar, você pode criar o seu pelo meu bot no número do WhatsApp: 558791080400, usando o comando: %CriarBot
e também Substitua <pergunta> pela sua pergunta


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


