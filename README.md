# YouTube Downloader para Windows

Baixa vídeos do YouTube direto numa pasta do seu computador. Opcionalmente, converte o vídeo para
H.264 HD 720p, um formato que praticamente qualquer TV, celular ou player abre.

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

Antes de adicionar, escolha:

- **O que salvar**: o vídeo, o vídeo e a transcrição, ou só a transcrição. A transcrição é um
  arquivo `.txt` feito das legendas do próprio YouTube. Se o vídeo não tem legenda, o app transcreve o
  áudio no próprio computador: na primeira vez, baixa o modelo de transcrição (466 MB), e cada vídeo
  leva mais ou menos a duração dele.
- **Converter para H.264 HD 720p**, se quiser. A conversão leva alguns minutos por vídeo.
- **Pular os que já estão no histórico**, para não baixar de novo o que você já tem.

Os vídeos entram numa **fila**, que baixa 2 de cada vez (de 1 a 4, em "Downloads ao mesmo tempo").
Dá para pausar a fila e cancelar um item. Se o app for fechado no meio, a fila volta pausada na
próxima vez.

Os vídeos vão para a pasta **Vídeos\YouTube Downloader**. Para mudar, use **Alterar pasta**. Se
já existir um arquivo com o mesmo nome, o novo é salvo como `Título (2)`, e nada é substituído.

## Histórico

A aba **Histórico** lista o que foi baixado neste computador. Dá para buscar pelo título, baixar de
novo, mostrar o arquivo na pasta e tirar da lista (o arquivo continua onde está). Um vídeo que já
foi baixado entra na fila com o aviso "Já baixado em ...".

## Tradução (opcional)

Com uma chave da API do DeepL, a transcrição sai também traduzida para português, inglês ou
espanhol, num segundo `.txt` ao lado do original.

1. Crie uma conta **DeepL API Free** em <https://www.deepl.com/pro-api>. O cadastro pede um cartão
   de crédito, mas o plano Free não cobra e traduz até 500 mil caracteres por mês.
2. Copie a chave da conta (ela termina em `:fx`) e cole em **Tradução (DeepL)**, no app. Clique em
   **Testar chave**.
3. Ao adicionar vídeos com transcrição, marque **Traduzir para ...**.

A chave fica cifrada neste computador. Com a tradução ligada, o texto da transcrição é enviado ao
DeepL. Se o vídeo já tem uma legenda no idioma escolhido, ela é usada no lugar da tradução e não
gasta a cota.

## Atualizações

Toda vez que o app abre, ele procura uma versão nova e a baixa em segundo plano. Quando ela estiver
pronta, aparece o aviso **Atualização pronta**. O app só reinicia quando você clicar em
**Reiniciar e atualizar**.

Manter o app atualizado importa: quando o YouTube muda, uma versão antiga pode parar de baixar.

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
