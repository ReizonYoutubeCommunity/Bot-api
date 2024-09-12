## Documentação da API Bot-API V1

Este documento detalha as funcionalidades da API Bot-API V1,  uma ferramenta que permite a criação de bots personalizados e interativos.

### Introdução

A API Bot-API V1 oferece uma variedade de recursos para a criação de bots, incluindo histórico de conversas, personalização, controle da linguagem de resposta e integração com outros sistemas.

### Funcionalidades

A API Bot-API V1 suporta as seguintes funcionalidades:

**Funcionalidades Ativas:**

* **Histórico de Conversas:** Permite o armazenamento e recuperação do histórico de conversas entre o bot e o usuário.
* **Envio do Nome do Usuário:** Possibilita a identificação do usuário através do envio do seu nome.
* **Personalização do Bot:** Permite a personalização do bot, incluindo a definição de sua personalidade e comportamento.
* **Modificação da Linguagem de Resposta do Bot:** Permite a definição da linguagem de resposta do bot, com suporte a múltiplos idiomas.

**Funcionalidades em Desenvolvimento:**

* **Data e Hora de São Paulo:** A integração com a data e hora de São Paulo estará disponível na versão V2 da API.
* **Modificação de Data e Hora:** A possibilidade de modificar a data e hora do bot estará disponível na versão V2 da API.
* **Site para Conversar com o Bot:** Um site dedicado à interação com o bot sem a necessidade da API, está em desenvolvimento e estará disponível na versão V2 ou V3 da API.

### URL da API

A URL da API Bot-API V1 é:

```
https://pointy-periodic-candytuft.glitch.me/api/<Bot>/
```

Onde `<Bot>` representa o nome do seu bot.

### Estrutura do JSON de Requisição

O JSON de requisição para a API Bot-API V1 deve ter a seguinte estrutura:

```json
{
  "text": "<pergunta>"
}
```

**Parâmetros opcionais:**

* **userName:** Nome do usuário.
* **Historic:** Histórico de conversas.
* **linguage:** Linguagem de resposta do bot.

### Exemplos de JSON de Requisição

**Exemplo 1: Envio de uma pergunta simples:**

```json
{
  "text": "Olá, como está?"
}
```

**Exemplo 2: Envio de uma pergunta com o nome do usuário:**

```json
{
  "text": "Olá, como está?",
  "userName": "João"
}
```

**Exemplo 3: Envio de uma pergunta com histórico de conversas:**

```json
{
  "text": "E você?",
  "Historic": {
    "user": "Olá, como está?",
    "chat": "Olá, estou bem! E você?"
  }
}
```

**Exemplo 4: Envio de uma pergunta com a linguagem de resposta:**

```json
{
  "text": "Olá, como está?",
  "linguage": "EN-US"
}
```

### Informações Importantes

* O parâmetro `text` é obrigatório em todos os JSONs de requisição.
* A linguagem de resposta padrão é `PT-BR`.
* Você pode criar o seu bot utilizando o comando `!CriarBot` no número do WhatsApp: 558791080400.

### Resposta da API

A API Bot-API V1 retorna um JSON com a seguinte estrutura:

**Em caso de sucesso:**

```json
{
  "status": "success",
  "message": "<Resposta do bot>"
}
```

**Em caso de erro:**

```json
{
  "error": "<motivo>",
  "status": "error",
  "message": "⚠️error⚠️"
}
```

### Exemplos de Resposta da API

**Exemplo 1: Resposta de sucesso:**

```json
{
  "status": "success",
  "message": "Olá, estou bem, obrigado por perguntar!"
}
```

**Exemplo 2: Resposta de erro:**

```json
{
  "error": "Parâmetro 'text' ausente",
  "status": "error",
  "message": "⚠️error⚠️"
}
```

### Codigos de Exemplo

**NodeJs:**

```js
const json = {
  "text": "<pergunta>"
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

**Curl:**

``` curl
curl -X POST \
 https://pointy-periodic-candytuft.glitch.me/api/<bot> \
 -H 'Content-Type: application/json' \
 -d '{\"text\": \"<pergunta>\"}'
```

**Python:**

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

### Observações

* Em todos os exemplos acima, substitua `<Bot>` pelo nome do seu bot.
* Substitua `<pergunta>` pela sua pergunta real.
* Certifique-se de configurar o código de acordo com sua linguagem de programação.

### Conclusão

A API Bot-API V1 oferece uma plataforma completa para a criação de bots personalizados. Com suas funcionalidades avançadas e interface simples, ela permite a construção de bots inteligentes e interativos para diversas aplicações.
