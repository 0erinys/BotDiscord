# Hyung Bot 🦾

## Techs ⚙

Confome está o projeto, atualizar quais tecnologias estamos utilizando

* [Python](https://www.python.org/): Linguagem de programação de sintaxe simples;
* [Mongodb](https://www.mongodb.com/): Bando de dados não relacional para armazenamento de informações, está sendo utilizado o banco diretamente no site;
* [Discord Developer Portal](https://discord.com/developers/applications): site para registrar sua aplicação/bot;
* [Discord.py](https://discordpy.readthedocs.io/en/latest/): Biblioteca para integração com o discord;

## Requisitos ⚙

* Ter instalado Python na versão 3.5 (durante o desenvolvimento, comecei na versão 3.5, então não posso garantir que versões anteriores funcionem);
* Crie um arquivo Token.py, preencha com os seguintes dados:
```py
class TokenDiscord:
  def uploadToken():
    return {
      "database": "Link de conexão ao mongodb",
      "idapresentacao":"é um long que representa o id de um dos canais onde vai ter pontos por reações",
      "idaviso":"é um long que representa o id de um dos canais onde vai ter pontos por reações",
      "token":"token de acesso do bot, gerado no site do Discord Developer Portal"
    }

```

## GAMIFICAÇÃO ⚙

A gamificação do bot é feita através de 2 tipos, a xp e níveis, o xp é dividido em semanal e por canal, os níveis são calculados de forma geral;

### XP ♟

O cálculo do xp vai seguir essas regras:
* Por mensagem:
  * Mínimo de 2 palavras;
  * Máximo por mensagem, 40 pontos;
  * Número de caracteres não repetidos / 3;
* Reações a mensagens:
  * Disponíveis em alguns canais;
  * Badlist de emojis, remove pontos, 200 pontos, remove a reação;
  * Goodlist de emojis, 5 emojis, 2x pontos, 100 pontos base;
* Tempo de canais de voz:
  * Conferir quais informações recebemos para avaliar os pontos
* Compartilhamento de tela:
  * Conferir quais informações recebemos para avaliar os pontos


#### pymongo operações

Essas informações que estão sendo mostradas é apenas para enteder como deve ser utilizado o pymongo

* **Insert**
```py
data = {
  'nome': 'Hyung',
  'idade': 17
}

responseData = collection.insert_one(data)
# responseData é do tipo InsertOneResult, só vi que tem o inserted_id até agora
```
[Infos sobre InsertOneResult](https://pymongo.readthedocs.io/en/stable/api/pymongo/results.html#pymongo.results.InsertOneResult)

* **Replace**
