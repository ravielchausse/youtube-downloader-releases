# YouTube Downloader para Windows

Baixa vídeos do YouTube, ou só o áudio, direto numa pasta do seu computador. Opcionalmente, converte
o vídeo para H.264 HD 720p, um formato que praticamente qualquer TV, celular ou player abre.

Aqui ficam só o instalador e as atualizações. O código-fonte é privado.

## Instalar

1. Abra a [última versão](../../releases/latest) e baixe o arquivo
   **`YoutubeDownloader.Desktop-win-Setup.exe`**.
2. Dê dois cliques no arquivo baixado.
3. Na primeira vez, o Windows pode mostrar **"O Windows protegeu o computador"**. O aviso aparece
   porque o app não é assinado digitalmente, não porque ele faz algo errado. Clique em
   **Mais informações** e depois em **Executar assim mesmo**.
4. O app abre sozinho, e fica um atalho "YouTube Downloader" na área de trabalho e no menu Iniciar.

Requisitos: Windows 10 (versão 1809 ou mais nova) ou Windows 11, 64 bits. O app precisa do
Microsoft Edge WebView2, que já vem no Windows 11. Se faltar, o instalador o instala.

## Usar

Na aba **Baixar**, escolha de onde vêm os vídeos:

- **Vídeo ou playlist**: cole o link de um vídeo ou de uma playlist. Os vídeos de uma playlist vão
  para uma subpasta com o nome dela.
- **Lista**: cole vários links, um por linha.
- **Canal · populares**: os vídeos mais vistos de um canal, numa faixa de duração, numa subpasta com o
  nome do canal. Um canal grande leva alguns minutos para ser analisado, e dá para cancelar.
- **Mais assistidos**: escolha o arquivo `watch-history.json` exportado pelo Google Takeout (os passos
  estão na tela), marque os vídeos e adicione. O histórico não fica guardado no app.

Copiou um link do YouTube? Ao abrir o app, ou ao voltar para ele, o campo do link já vem preenchido.
Nada baixa sozinho, e o que você já tinha digitado nunca é trocado.

Também dá para arrastar o link do navegador (da barra de endereço ou de um vídeo na página) para a
janela do app. Ele vai para o campo do link, no lugar do que estava lá, ou entra como uma linha nova
se a **Lista** estiver aberta.

Antes de adicionar, escolha:

- **O que salvar**: o vídeo, só o áudio, cada um com ou sem a transcrição, ou só a transcrição. O
  áudio sai em M4A ou MP3 (veja [Configurações](#configurações)), com a capa, o título, o canal e o
  ano do vídeo. A transcrição é um arquivo `.txt` feito das legendas do próprio YouTube. Se o vídeo
  não tem legenda, o app transcreve o áudio no próprio computador: na primeira vez, baixa o modelo de
  transcrição (466 MB, o padrão), e cada vídeo leva mais ou menos a duração dele.
- **Qualidade**: 480p, 720p, 1080p (o padrão) ou **Melhor disponível**. Até 1080p o vídeo vem em
  H.264, que abre em qualquer aparelho; acima, em VP9 ou AV1, que TV antiga ou carro podem não abrir.

O que se usa de vez em quando fica em **Mais opções**, um bloco fechado. Quando alguma delas está
ligada, o nome do bloco mostra qual, para nada valer escondido:

- **Escolher faixa de áudio** e **Escolher legenda**: num vídeo dublado, o vídeo, o áudio e a
  transcrição saem no idioma original. Para outro idioma, cole o link de um vídeo e escolha a faixa ou
  a legenda.
- **Traduzir para ...**: a transcrição sai também traduzida (veja [Tradução](#tradução-opcional)).
- **Converter para H.264 HD 720p**. A conversão leva alguns minutos por vídeo, e a escolha fica
  lembrada para os próximos downloads.
- **Pular os que já estão no histórico**, para não baixar de novo o que você já tem.

Os vídeos entram numa **fila**, que baixa 2 de cada vez. Dá para pausar a fila e cancelar um item. Se
o app for fechado no meio, a fila volta pausada na próxima vez. Quando a fila termina com o app
minimizado ou atrás de outra janela, o Windows mostra um aviso com quantos foram concluídos e quantos
falharam; clicar nele abre a pasta.

Os vídeos vão para a pasta **Vídeos\YouTube Downloader**, que aparece embaixo do formulário, com
**Abrir pasta**. Se já existir um arquivo com o mesmo nome, o novo é salvo como `Título (2)`, e nada
é substituído.

## Configurações

A aba **Configurações**, no canto direito do topo, guarda o que não muda de um download para o
outro. Cada mudança vale na hora.

- **Downloads**: **Alterar pasta** troca a pasta dos vídeos. **Downloads ao mesmo tempo** vai de 1 a
  4; mais que 2 pode fazer o YouTube limitar a sua conexão.
- **Áudio**: o **Formato**, M4A ou MP3.
- **Transcrição pelo áudio**: o **Modelo do Whisper**. O padrão é o de 466 MB; há um menor, mais
  rápido, e um maior, que erra menos e demora mais.
- **Tradução**: a chave do DeepL e o idioma (veja [Tradução](#tradução-opcional)).
- **Sobre**: a versão do app e a pasta de logs.

## Histórico

A aba **Histórico** lista o que foi baixado neste computador. Dá para buscar pelo título, baixar de
novo, mostrar o arquivo na pasta e tirar da lista (o arquivo continua onde está). Um vídeo que já
foi baixado entra na fila com o aviso "Já baixado em ...".

## Tradução (opcional)

Com uma chave da API do DeepL, a transcrição sai também traduzida para português, inglês ou
espanhol, num segundo `.txt` ao lado do original.

1. Crie uma conta **DeepL API Free** em <https://www.deepl.com/pro-api>. O cadastro pede um cartão
   de crédito, mas o plano Free não cobra e traduz até 500 mil caracteres por mês.
2. Copie a chave da conta (ela termina em `:fx`). No app, em **Configurações**, cole em **Chave do
   DeepL**, clique em **Salvar chave** e depois em **Testar chave**. Escolha o idioma em **Traduzir
   para**.
3. Ao adicionar vídeos com transcrição, marque **Traduzir para ...** em **Mais opções**.

A chave fica cifrada neste computador. Com a tradução ligada, o texto da transcrição é enviado ao
DeepL. Se o vídeo já tem uma legenda no idioma escolhido, ela é usada no lugar da tradução e não
gasta a cota.

## Atualizações

Toda vez que o app abre, ele procura uma versão nova e a baixa em segundo plano. Quando ela estiver
pronta, aparece o aviso **Atualização pronta**. O app só reinicia quando você clicar em
**Reiniciar e atualizar**.

Manter o app atualizado importa: quando o YouTube muda, uma versão antiga pode parar de baixar.

## Se algo der errado

Em **Configurações**, no fim da página, **Sobre** › **Abrir pasta de logs** mostra o registro do que o app fez, um
arquivo por dia. Mande o arquivo do dia junto com a descrição do problema.

## Licenças

O app inclui programas de terceiros, cada um com a própria licença. O texto completo está no
arquivo `THIRD-PARTY-NOTICES.txt`, na pasta de instalação.

- **FFmpeg**, sob a LGPL v3, usado para juntar vídeo e áudio e para converter.
- **OpenH264**, sob a licença BSD, usado na conversão para H.264. A licença de patentes do H.264
  oferecida pela Cisco cobre só o binário distribuído pela própria Cisco, não este.
- **YoutubeExplode**, sob a LGPL v3.
- **Whisper.net** e **whisper.cpp**, sob a licença MIT, usados para transcrever o áudio.
- **Modelos do Whisper**, da OpenAI, sob a licença MIT. Não vêm no instalador: o app baixa o modelo
  escolhido na primeira transcrição pelo áudio.

O app é gratuito, para uso pessoal e familiar. Cada pessoa baixa pela própria conexão. Respeite os
termos de uso do YouTube e os direitos de quem publicou o vídeo.
