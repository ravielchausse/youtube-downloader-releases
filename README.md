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

1. Cole o link do vídeo, por exemplo `https://www.youtube.com/watch?v=...`.
2. Marque **Converter para H.264 HD 720p**, se quiser. A conversão leva alguns minutos.
3. Clique em **Baixar**.

Os vídeos vão para a pasta **Vídeos\YouTube Downloader**. Para mudar, use **Alterar pasta**. Se
já existir um arquivo com o mesmo nome, o novo é salvo como `Título (2)`, e nada é substituído.

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

O app é gratuito, para uso pessoal e familiar. Cada pessoa baixa pela própria conexão. Respeite os
termos de uso do YouTube e os direitos de quem publicou o vídeo.
