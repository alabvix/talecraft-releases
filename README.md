# TaleCraft — builds de teste

Este repositório publica os instaladores de teste do **TaleCraft**, um app
desktop de planejamento de livros de ficção científica, fantasia e terror.
As builds estão disponíveis para **Windows**, **Linux** e **macOS**.

## Baixar

Abra a [lista de releases](../../releases) e baixe o arquivo da sua
plataforma:

- **Windows:** `TaleCraft_0.1.0_x64-setup.exe` (recomendado) ou
  `TaleCraft_0.1.0_x64_en-US.msi`.
- **Linux:** `TaleCraft_0.1.0_amd64.AppImage` (portátil) ou
  `TaleCraft_0.1.0_amd64.deb` (Debian/Ubuntu).
- **macOS:** `TaleCraft_0.1.0_universal.dmg` (Intel e Apple Silicon).
- **SHA256SUMS.txt** — confira a integridade do download.

## Instalar no Windows

1. Baixe o `setup.exe`.
2. Execute o arquivo.
3. Se o Windows mostrar **“O Windows protegeu o computador”**, clique em
   **Mais informações** e depois em **Executar assim mesmo**. O aviso aparece
   porque o build de teste ainda não tem assinatura digital.
4. Conclua a instalação e abra o **TaleCraft**.

Requisitos: **Windows 10 ou 11, 64 bits**. O instalador cuida do WebView2
quando necessário.

## Instalar no Linux

AppImage (não precisa instalar):

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

## Instalar no macOS

1. Abra o `TaleCraft_0.1.0_universal.dmg`.
2. Arraste o **TaleCraft** para a pasta **Applications**.
3. Na primeira abertura, clique com o botão direito no app e escolha
   **Abrir**. O build não tem assinatura nem notarização da Apple.

Se o macOS continuar bloqueando:

```bash
xattr -dr com.apple.quarantine /Applications/TaleCraft.app
```

Requisitos: **macOS 10.15 ou superior**, Intel ou Apple Silicon.

## Onde ficam os dados

Tudo é local. O banco fica em:

```text
Windows: %APPDATA%\com.talecraft.desktop\talecraft.db
Linux:   ~/.local/share/com.talecraft.desktop/talecraft.db
macOS:   ~/Library/Application Support/com.talecraft.desktop/talecraft.db
```

Nenhum dado é enviado para servidores.

## O que testar nesta versão

- **Livros:** Meus Livros, dados gerais, abas Resumo, Sinopse, Tema, Conflito e
  Voz Narrativa.
- **Personagens do livro:** elenco, papéis, vínculos e ficha global.
- **Capítulos:** quadro com Esboço, Rascunho, Revisão e Finalizado, criação,
  edição, Motivo do Tipo, Motivo do Evento e arrastar entre status.
- **Gráficos:** Curva de Progressão por Capítulo e Evolução de Personagem.

## Limitações conhecidas

- **Exportação em PDF:** disponível apenas no Windows nesta build.
- **Assinatura:** nenhum dos instaladores é assinado digitalmente.
- **Linux e macOS:** builds novas, com menos testes que o Windows; relate
  problemas de inicialização, fontes ou janela.

## Enviar feedback

Anote a versão usada (aparece na barra superior), a plataforma, o que você fez,
o que esperava e o que aconteceu. Se possível, envie uma captura de tela.

Obrigado por testar!
