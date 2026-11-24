# TaleCraft 0.1.0 — build de teste 4 (Windows)

Quarta build para testadores. O foco é o **mundo do livro**, as **localidades**,
os **mapas do mundo** e o **painel de capítulos**. Por enquanto, esta release
traz somente o instalador de **Windows**; **Linux** e **macOS** serão
adicionados quando estiverem prontos.

## Novidades desta build

- **Um ou mais mundos por livro:** associe mundos globais ao livro e consulte as
  entradas na própria página do livro.
- **Localidades em árvore:** imagem, tipo e hierarquia livre (Cidade › Bairro ›
  Casa › Quarto), com ícone do tipo quando não há imagem.
- **Mapas do Mundo:** mapas por escala em Mundo, Região, Cidade, Bairro e
  Prédio/Casa, com editor, polígonos, ligações, pan/zoom, plantas e cinco fundos.
- **Prédio/Casa:** cômodos retangulares com oito alças e ferramenta **Porta**.
- **Edição de polígono:** mover pelo interior, redimensionar pelas arestas e
  ajustar um vértice pelo nó.
- **Dados Complementares:** a nova aba do capítulo reúne Foreshadowing, Plot
  Twist, Cliffhanger, Punch e K.O, com o Salvar comum.
- **Vários cenários por capítulo:** adicione e remova localidades, mantendo a
  ordem de inclusão.
- **Correção do capítulo:** a migração v23 corrigiu a FK que causava
  `no such table: main.localidade_antiga` ao gravar o cenário.

## Download

| Arquivo | Plataforma | Observação |
| --- | --- | --- |
| `TaleCraft_0.1.0_x64-setup.exe` | Windows 10/11 64 bits | Recomendado; instala sem administrador. |
| `TaleCraft_0.1.0_x64_en-US.msi` | Windows 10/11 64 bits | Alternativa para quem prefere MSI. |
| `SHA256SUMS.txt` | Windows | Hashes para conferir a integridade. |

**Linux e macOS:** em preparação nesta build.

## Instalação

### Windows

1. Baixe o `setup.exe` e execute.
2. Se o Windows mostrar **“O Windows protegeu o computador”**, clique em
   **Mais informações** e depois em **Executar assim mesmo**.
3. Conclua a instalação e abra o **TaleCraft**.

Requisitos: **Windows 10 ou 11, 64 bits**.

### Linux (quando publicado)

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

### macOS (quando publicado)

1. Abra o `TaleCraft_0.1.0_universal.dmg`.
2. Arraste o **TaleCraft** para a pasta **Applications**.
3. Na primeira abertura, clique com o botão direito no app e escolha **Abrir**.

Se o macOS continuar bloqueando:

```bash
xattr -dr com.apple.quarantine /Applications/TaleCraft.app
```

Requisitos: **macOS 10.15 ou superior**, Intel ou Apple Silicon.

## O que testar

- Associar dois mundos ao mesmo livro e alternar entre as abas.
- Criar cidade, bairro, casa e quarto; conferir a árvore e as miniaturas.
- Criar mapas de cada escala; arrastar localidades, desenhar polígonos e criar
  portas em Prédio/Casa.
- Conferir os mapas na aba **Mapas** do livro e no PDF do Mundo.
- Abrir um capítulo, usar **Dados Complementares** e salvar/reabrir.
- Adicionar dois cenários ao mesmo capítulo, remover um e conferir a ordem.
- Remover um mundo do livro e verificar que só os cenários dele saem.

## Notas técnicas

- Migrações v20 a v24; banco na **v24**.
- **70 comandos Tauri**, **183 testes Rust**, fmt e Clippy limpos.
- Verificadores: RF015 31/31, RF017 28/28, RF018 17/17 e RF019 43/43.
- Builds sem assinatura digital; o SmartScreen e o Gatekeeper podem avisar.

## Onde ficam os dados

```text
Windows: %APPDATA%\com.talecraft.desktop\talecraft.db
Linux:   ~/.local/share/com.talecraft.desktop/talecraft.db
macOS:   ~/Library/Application Support/com.talecraft.desktop/talecraft.db
```

Nenhum dado é enviado para servidores.
