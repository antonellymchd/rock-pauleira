# Rock Pauleira

Jogo de ritmo para uso pessoal: transforma playlists do Spotify em turnês e você toca cada show.

## Como rodar
1. Na pasta do jogo, abra um servidor local:
   `python3 -m http.server 8888`
2. Abra **http://127.0.0.1:8888/** (use 127.0.0.1, não "localhost": o Spotify exige isso).

## Ligar ao Spotify (uma vez só)
1. Entre em https://developer.spotify.com/dashboard e crie um app.
2. Em *Redirect URIs* cadastre: `http://127.0.0.1:8888/`
3. Marque **Web API** e **Web Playback SDK**.
4. Copie o *Client ID* e cole na tela inicial do jogo.

## Como jogar
- Escolha uma playlist → defina quantos shows e quantos minutos cada → **Montar turnê**.
- Reordene ou tire músicas; a última de cada show vira o **BIS**.
- Teclas **A S D F G** (ou 1–5) tocam as notas; **Espaço** ativa a Euforia (pontos x2);
  **← →** ajustam a sincronia durante a música; **Esc** pausa.

## De onde vêm as notas
- **Com arquivo de áudio local** (botão "Áudio local" no setlist, nomes tipo `Artista - Música.mp3`):
  o jogo analisa o som e cria notas no ritmo real. É o modo recomendado.
- **Só com Spotify** (precisa de Premium): o Spotify não deixa ler o áudio nem fornece mais
  BPM pela API, então as notas são geradas a partir do BPM que você informa (campo BPM ou botão
  "tap"). Use ← → para alinhar com a batida.

## Versão para iPhone / iPad
O jogo funciona como app no iPhone: abre em tela cheia pelo ícone na tela de início,
tem controles por toque e abre mesmo sem internet.

### Instalar
1. Hospede a pasta inteira (index.html, manifest.webmanifest, sw.js, icon-*.png) num endereço
   **https**. A opção gratuita mais simples é o GitHub Pages; o Netlify Drop
   (arrastar a pasta para app.netlify.com/drop) também serve.
2. No iPhone, abra o endereço no **Safari** → botão Compartilhar → **Adicionar à Tela de Início**.
3. No painel do Spotify, adicione também o endereço https como Redirect URI.

Para testar rápido na rede de casa sem hospedar, rode `python3 -m http.server 8888` no computador
e abra `http://IP-DO-COMPUTADOR:8888` no iPhone. Assim só funciona o modo com arquivos de áudio:
o login do Spotify e o uso offline exigem https.

### Jogar no iPhone
- Toque nas trilhas na parte de baixo da tela. Dá para usar vários dedos ao mesmo tempo nos acordes.
- **EUFORIA!** aparece quando a barra enche; **❚❚** pausa e permite ajustar a sincronia.
- **Músicas do Spotify:** no iPhone, a música toca pelo **app do Spotify** (Premium), que o jogo
  controla à distância. Abra o app do Spotify e dê play em qualquer música antes de começar.
  A sincronia é mais imprecisa que no computador; ajuste na pausa se precisar.
- **Arquivos de áudio:** em "Escolher arquivos", o iPhone abre o app Arquivos (iCloud Drive,
  pasta Downloads etc.). Funciona com MP3, M4A, WAV, AAC e FLAC.
- Se o app sair da tela (você trocou de app ou bloqueou o celular), o jogo pausa sozinho.
