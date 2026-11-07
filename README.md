<p align="center">
  <img width="512" height="512" alt="logo" src="https://github.com/user-attachments/assets/3372843b-26c6-4721-8083-c46bfc7285db" />

</p>

<h1 align="center">Obsidia 0.9</h1>

<p align="center">
  <img src="https://img.shields.io/badge/C%23-512BD4?style=flat-square" alt="C#">
  <img src="https://img.shields.io/badge/.NET%20Framework-512BD4?style=flat-square&amp;logo=dotnet&amp;logoColor=white" alt=".NET Framework">
  <img src="https://img.shields.io/badge/WPF-0078D4?style=flat-square" alt="WPF">
</p>

Obsidia é um editor de vídeos curtos e gravador de tela para Windows. Dá para cortar um clipe, ajustar o enquadramento, adicionar legendas e exportar o resultado pelo próprio app.

## Baixar e abrir

[![Baixar Obsidia.exe para Windows](https://img.shields.io/badge/⬇%20Baixar-Obsidia.exe-2563EB?style=for-the-badge)](https://github.com/SEU-USUARIO/SEU-REPOSITORIO/releases/latest/download/Obsidia.exe)

1. Clique em **Baixar Obsidia.exe**.
2. Abra o `Obsidia.exe`. Na primeira abertura, ele extrai automaticamente o FFmpeg e o FFprobe que já vêm dentro do executável.
3. Selecione um vídeo na tela inicial ou grave um clipe pelo próprio editor.

O editor usa o .NET Framework 4.x. A preparação das ferramentas de vídeo, a edição e a exportação funcionam localmente. A configuração inicial das legendas automáticas precisa de internet.

## Recursos

| Área | O que dá para fazer |
| --- | --- |
| Edição | Marcar início e fim do clipe, ajustar o enquadramento, girar, espelhar e controlar a reprodução com **Espaço**. |
| Imagem | Ajustar cor, aplicar filtros e LUTs 3D e trabalhar com keyframes de enquadramento. |
| Texto e legendas | Adicionar texto sobre o vídeo, editar legendas manualmente, importar e exportar SRT e transcrever um trecho com whisper.cpp. |
| Áudio | Ajustar volume, silenciar, reduzir ruído e normalizar o áudio. |
| Gravação | Capturar um monitor ou uma janela e usar webcam e microfone quando disponíveis. |
| Exportação | Gerar MP4, GIF ou MP3 e ajustar opções como resolução, taxa de quadros e tamanho-alvo, conforme o formato. |

## Primeira edição

1. Abra um vídeo e mova o cursor até o ponto de corte desejado.
2. Na ferramenta de corte, use **Início = cursor** e **Fim = cursor** para marcar o trecho.
3. Faça os ajustes de imagem, áudio ou legendas que quiser.
4. Clique em **Exportar**, escolha o formato e confirme em **Exportar agora**.

Em **Configurações**, você pode trocar a pasta de saída. A pasta padrão é **Vídeos → Obsidia**.

### Legendas automáticas

Na ferramenta de legendas, clique em **Baixar e ativar** para baixar o whisper.cpp e o modelo de voz. Depois, use **Gerar legendas do trecho**. A transcrição roda no computador e pode ser revisada antes de exportar o vídeo ou salvar um arquivo SRT. A importação de SRT e a edição manual de legendas dispensam esse download.

## Arquivos locais

| Local | Conteúdo |
| --- | --- |
| `%LOCALAPPDATA%\Obsidia\MediaTools` | FFmpeg e FFprobe extraídos na primeira abertura. |
| `%LOCALAPPDATA%\Obsidia\Cache` | Arquivos temporários usados na edição e no processamento de mídia. |
| `%LOCALAPPDATA%\Obsidia\whisper` | Ferramenta e modelo baixados para legendas automáticas. |
| `%LOCALAPPDATA%\Obsidia` | Configurações e histórico local de arquivos recentes. |

## Solução de problemas

- **O app pediu para colocar FFmpeg e FFprobe ao lado do executável.** Essa mensagem é da compilação antiga. Baixe o `Obsidia.exe` em **Releases**.
- **O app não conseguiu preparar as ferramentas de vídeo.** Confira o espaço livre no disco e a permissão de gravação em `%LOCALAPPDATA%\Obsidia`.
- **A exportação ou gravação falhou.** Use **Configurações → Testar ffmpeg**. Se estiver usando um encoder de GPU, teste a exportação com x264. Para falhas de processamento, confira se existe um log em `%LOCALAPPDATA%\Obsidia\Cache\ultimo-erro.txt`.
- **A webcam ou o microfone não aparece.** Confira as permissões de câmera e microfone para aplicativos de área de trabalho no Windows e atualize a lista de dispositivos no gravador.

## Futuras mudanças

Ideias para próximas versões, sem data definida.

- Salvar projetos para retomar uma edição depois.
- Adicionar ações de desfazer e refazer na edição.
- Criar predefinições de exportação para vídeos verticais, quadrados e horizontais.
- Mostrar o progresso da preparação das ferramentas de vídeo na primeira abertura.

## Reportar problemas

Abra uma **Issue** neste repositório. Inclua a versão do Obsidia e do Windows, os passos para reproduzir o erro e a mensagem completa. Se o problema ocorrer com um vídeo específico, informe o formato e a duração. Em caso de alerta de segurança, inclua também o nome da detecção e o arquivo afetado.

## Dependências e licenças

- **FFmpeg e FFprobe** vêm incluídos no executável e fazem a leitura, a captura e o processamento de mídia. [Licenças do FFmpeg](https://ffmpeg.org/legal.html)
- **whisper.cpp** é a ferramenta opcional de transcrição local usada pelas legendas automáticas. [Projeto whisper.cpp](https://github.com/ggml-org/whisper.cpp)
