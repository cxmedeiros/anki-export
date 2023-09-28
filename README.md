<img src="https://github.com/duartebianca/flAshI/blob/main/img/flashi_logo_preto.png" alt="logo" width="100" />

# Anki Export 🔠📤

Este README fornece documentação para contribuir com o repositório, que contém código para exportar flashcards para decks do Anki usando Flask e a biblioteca Genanki.

## Estrutura do Repositório

O repositório contém os seguintes arquivos e diretórios:

### Na pasta `server`:

- `app.py`: Este é o aplicativo principal do Flask que lida com solicitações recebidas e aciona a exportação de flashcards.
- `converter.py`: Este módulo contém funções para criar flashcards, decks e exportá-los para o Anki.
- `requirements.txt`: Este arquivo lista as dependências do Python necessárias para executar o aplicativo.

### Na pasta `client`:
App next com demonstração de como utilizar o endpoint. Link da API: 
- `public`: Contém ativos estáticos, como imagens ou arquivos que podem ser servidos pelo lado do cliente.
- `src`: Contém o código-fonte da aplicação do cliente, incluindo JavaScript e estilos.
- Arquivos de Configuração: Pode haver arquivos de configuração JSON para a aplicação do cliente.

## Código do Lado do Servidor

### `app.py`

Este é o aplicativo principal do Flask que expõe um ponto de extremidade para converter e exportar flashcards para o Anki. Ele utiliza as funções de `converter.py` para criação de flashcards e exportação.

#### EndPoints:

- `POST https://genanki-server.onrender.com/converter: Aceita uma solicitação POST com dados de flashcards, cria um deck do Anki e retorna o arquivo de pacote Anki gerado (.apkg) para download.
#### Dependências Principais:

- Flask: Usado para criar a API REST.
- `converter.py`: Contém funções para criação de flashcards e exportação do Anki.
- Flask-CORS: Habilita o Compartilhamento de Recursos de Origem Cruzada (CORS) para todas as rotas.

#### Uso:

1. Envie uma solicitação POST para https://genanki-server.onrender.com/converter com os dados necessários para criar e exportar flashcards.

### `converter.py`

Este módulo contém funções para criar flashcards, decks e exportá-los para o Anki usando a biblioteca Genanki.

#### Funções:

- `create_flashcards(list_image_url, list_sentence, list_translation, list_audio, n_flashcard)`: Cria uma lista de flashcards com base nos dados de entrada.

- `create_deck(deck_name, n_flashcard)`: Cria um deck do Anki e um modelo de nota.

- `export_to_anki(deck_name, list_image_url, list_sentence, list_translation, list_audio, n_flashcard)`: Exporta os flashcards para um arquivo de pacote do Anki (.apkg).

#### Dependências:

- Genanki: Uma biblioteca para gerar decks do Anki programaticamente.

## Código do Lado do Cliente

O código do lado do cliente está em TypeScript (TS) e utiliza Next.js. Ele interage com o servidor para enviar dados de flashcards e receber o arquivo de pacote do Anki gerado.

## Teste

Para testar a funcionalidade do servidor e do cliente, você pode usar o arquivo de teste `main.ts`. Este arquivo envia uma solicitação POST com dados de exemplo de flashcards para o servidor e salva o arquivo de pacote do Anki gerado no disco.

Para executar o teste:

1. Certifique-se de que você tenha o Node.js instalado.

2. Navegue até o diretório `client`.

3. Execute o teste com o comando:

   ```
   node main.ts
   ```

Este arquivo de teste enviará uma solicitação para o servidor, gerará um arquivo de pacote do Anki chamado `deck_audio_teste14.apkg` e o salvará no diretório do cliente.

Lembre-se de que você pode precisar fazer ajustes no arquivo `main.ts` para garantir que ele use as informações corretas para enviar dados ao servidor, como o URL do servidor e os dados do flashcard. Certifique-se de que o arquivo `main.ts` esteja configurado corretamente para o seu ambiente e aplicação.

## Contribuição 🤝🌐

Para contribuir com o repositório "anki-export", siga estas etapas:

1. Faça um fork do repositório no GitHub.

2. Clone o repositório forked em sua máquina local.

3. Crie um novo branch para sua contribuição.

4. Faça suas alterações ou adições no código.

5. Teste suas alterações para garantir que funcionem conforme o esperado.

6. Faça commits de suas alterações com mensagens de commit descritivas.

7. Faça push de suas alterações para o fork no GitHub.

8. Crie um pull request para o repositório original, descrevendo suas alterações e o problema que elas resolvem.

9. Aguarde a revisão e a mesclagem pelos mantenedores do repositório.

Obrigado por contribuir com o "anki-export"! 🙌
