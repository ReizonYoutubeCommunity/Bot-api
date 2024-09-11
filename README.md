# Bot-api
Uma "ajuda" para quem quer usar minha api

# Url da API
https://pointy-periodic-candytuft.glitch.me/api/<bot>/

# Exemplo do json que deve ser enviado para o servidor
```json
{ 
  "text": '<pergunta>'
}
```
##você também poderá enviar mais informações como:

###O NOME do usuario
```json
{ 
  "text": '<Pergunta>',
  "userName": '<Nome do Usuario>'
}
```
###A linguagem que você quer que o bot responda
```json
{ 
  "text": '<Pergunta>',
  "linguage": '<Linguagem de Resposta>'
}
```
se você não informar isso a linguagem padrão de resposta é 'PT-BR'
