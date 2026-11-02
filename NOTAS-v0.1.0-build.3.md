# TaleCraft 0.1.0 — build de teste 3 (Windows, Linux e macOS)

Terceira build para testadores. O foco é o **elenco do livro**, o **painel de
capítulos** e os **gráficos** — agora também no Painel do Livro e na ficha do
personagem. Instaladores para **Windows**, **Linux** e **macOS**.

## Novidades desta build

- **Personagens do livro:** o elenco aparece em cards ou lista paginada, com
  **Qtd Capítulos** e os números dos capítulos em que cada personagem aparece.
- **Detalhe inline do personagem:** abre abaixo da grade, no lugar do antigo
  modal, com quatro abas — **Dados Globais do Personagem**, **Personagem no
  Livro**, **Gráfico de Evolução** e **Eventos**.
- **Aba Eventos:** tabela com **Capítulo**, **Tipo Evento** e **Motivo do
  evento**, com paginação no front-end e filtro de eventos neutros.
- **Ficha global do personagem:** vínculos com livros, contagem real de livros
  vinculados e a **Curva de arco em cada livro**, com seleção do livro para ver
  a evolução naquele livro.
- **Capítulos:** o painel de edição foi dividido em **Dados do Capítulo** e
  **Personagens do Capítulo**. A segunda aba traz **Motivo do Tipo**, **Meta**,
  **Cenário Descritivo** de duas linhas, miniatura do retrato (ou quadrado
  vazio), **Nome - Papel** e as ajudas de **Evento** e **Tipo de Evento**.
- **Gráficos no Painel do Livro:** a **Curva de Progressão por Capítulo** agora
  aparece abaixo dos módulos do painel, com o mesmo cálculo da seção Gráficos.
- **Ajustes de livros e personagens:** correções de vínculo, contagens do painel
  e da curva de arco, além de ajustes no cálculo dos gráficos no back-end.

## Download

| Arquivo | Plataforma | Observação |
| --- | --- | --- |
| `TaleCraft_0.1.0_x64-setup.exe` | Windows 10/11 64 bits | Recomendado; instala sem administrador. |
| `TaleCraft_0.1.0_x64_en-US.msi` | Windows 10/11 64 bits | Alternativa para quem prefere MSI. |
| `TaleCraft_0.1.0_amd64.AppImage` | Linux 64 bits | Portátil, não precisa instalar. |
| `TaleCraft_0.1.0_amd64.deb` | Debian/Ubuntu 64 bits | Instala pelo gerenciador de pacotes. |
| `TaleCraft_0.1.0_universal.dmg` | macOS 10.15+ | Universal (Intel e Apple Silicon). |
| `SHA256SUMS.txt` | Qualquer | Hashes para conferir a integridade. |

## Instalação

### Windows

1. Baixe o `setup.exe`.
2. Execute o arquivo.
3. Se o Windows mostrar **“O Windows protegeu o computador”**, clique em
   **Mais informações** e depois em **Executar assim mesmo**. O aviso aparece
   porque esta build ainda não tem assinatura digital.
4. Conclua a instalação e abra o **TaleCraft**.

Requisitos: **Windows 10 ou 11, 64 bits**. O instalador cuida do WebView2
quando necessário.

### Linux

AppImage:

```bash
chmod +x TaleCraft_0.1.0_amd64.AppImage
./TaleCraft_0.1.0_amd64.AppImage
```

Debian/Ubuntu:

```bash
sudo apt install ./TaleCraft_0.1.0_amd64.deb
```

Requisitos: distribuição 64 bits com WebKitGTK 4.1 (Ubuntu 22.04+, Debian 12+
ou equivalente).

### macOS

1. Abra o `TaleCraft_0.1.0_universal.dmg`.
2. Arraste o **TaleCraft** para a pasta **Applications**.
3. Na primeira abertura, clique com o botão direito no app e escolha
   **Abrir** (o build não tem assinatura nem notarização da Apple).

Se o macOS bloquear mesmo assim:

```bash
xattr -dr com.apple.quarantine /Applications/TaleCraft.app
```

## Onde ficam os dados

Tudo é local; nada é enviado para servidores.

```text
Windows: %APPDATA%\com.talecraft.desktop\talecraft.db
Linux:   ~/.local/share/com.talecraft.desktop/talecraft.db
macOS:   ~/Library/Application Support/com.talecraft.desktop/talecraft.db
```

## O que testar nesta versão

- **Livros:** Meus Livros, dados gerais, abas Resumo, Sinopse, Tema, Conflito e
  Voz Narrativa.
- **Personagens do livro:** cards/lista com capítulos por personagem e o detalhe
  inline nas quatro abas, principalmente **Eventos** e **Gráfico de Evolução**.
- **Ficha global do personagem:** vínculos e a curva de arco ao trocar o livro.
- **Capítulos:** quadro de status, as duas abas do painel e o elenco do capítulo
  com retrato, papel, Evento, Tipo de Evento e Motivo.
- **Gráficos:** a curva no Painel do Livro, a seção Gráficos e a evolução por
  personagem.

## Limitações conhecidas

- **Exportação em PDF:** disponível apenas no Windows nesta build.
- **Assinatura:** nenhum dos instaladores é assinado digitalmente.
- **Linux/macOS:** builds novas, com menos testes que o Windows. Relate
  qualquer problema de inicialização, fonte ou janela.

## Checksums (SHA-256)

```text
a10e0615799939a5c04d6287d207c0def58ac88942f6eae95f0d3fb96b54845c  TaleCraft_0.1.0_amd64.AppImage
997112d7843a08211aad155397391bf0ffcbe6fb58fa739445816d1d7a3d4e48  TaleCraft_0.1.0_amd64.deb
10bdb5184e4359b5e051e338e7c32510479255f2ddd08c9d96ac1d8dba0c5779  TaleCraft_0.1.0_universal.dmg
a15ee90cb93d79d289c63fba85d5e76a399e4098a5fd98c5e9992f065deb4615  TaleCraft_0.1.0_x64_en-US.msi
e31d3f894f7812b1503fc3c3c0242324f32536e5b48697195732a93890766859  TaleCraft_0.1.0_x64-setup.exe
```

## Feedback

Anote a versão usada (aparece na barra superior), a plataforma, o que você fez,
o que esperava e o que aconteceu. Se possível, envie uma captura de tela.

Obrigado por testar!
