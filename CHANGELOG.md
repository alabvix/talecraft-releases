# Changelog — TaleCraft

Histórico das builds de teste do TaleCraft, uma seção por versão/build.

> **Como usar:** a seção da build mais recente é a base do **post do Substack** e
> das **notas da release**. Ela está escrita em linguagem de produto (o que o
> escritor ganha), com uma lista curta de destaques para abrir o post e uma seção
> técnica para as notas. Ao publicar a build, troque **não publicado** por
> **publicado em \<data\>** e acrescente os links dos instaladores.
>
> As builds 1 a 3 foram resumidas a partir de `NOTAS-v0.1.0-build.3.md`, do
> `README.md` e do post da build 2; os detalhes completos estão nesses arquivos.

---

## 0.1.0 build 4 — publicado em 24/11/2026 (Windows; Linux e macOS em preparação)

**Foco:** o **mundo do livro**, as **localidades**, os **mapas do mundo** e o
**painel de capítulos**. Por enquanto, os instaladores publicados são de
**Windows**; **Linux** e **macOS** entram nesta mesma release quando estiverem
prontos.

### Destaques para o post

1. **Cada livro agora tem um ou mais mundos.** O escritor associa os mundos
   globais ao livro e consulta as entradas na própria página do livro.
2. **As localidades viraram um mapa do cenário.** Cada uma tem imagem, tipo e
   pode ficar dentro de outra, formando árvores como Cidade › Bairro › Casa ›
   Quarto.
3. **O mundo ganhou mapas por escala.** Mundo, Região, Cidade, Bairro e
   Prédio/Casa têm editor próprio, com cômodos, portas e plantas.
4. **O capítulo ficou mais organizado.** A nova aba **Dados Complementares**
   separa Foreshadowing, Plot Twist, Cliffhanger, Punch e K.O, e o cenário aceita
   vários lugares no mesmo capítulo.

### Livro e mundo

- **Worldbuilding do livro:** a seção deixa de ser uma tela informativa e passa a
  ter uma aba por mundo associado, na ordem de associação, com o resumo do mundo
  e as seis categorias de entradas (Localidades, Raças e Povos, Artefatos, Armas,
  Eventos e Sistemas).
- **Um ou mais mundos por livro:** antes o produto previa um único mundo;
  agora o livro pode se passar em vários, e o mesmo mundo pode servir a vários
  livros.
- **Associar mundos:** grade paginada com busca, seleção múltipla e selo **Já
  associado**; remover um mundo do livro limpa, com aviso, os cenários dos
  capítulos que usavam localidades dele.
- **Criar entradas pelo livro:** a categoria do mundo aceita **Nova entrada**
  direto na seção do livro, sem sair para o nível raiz.
- **Cenário dos capítulos:** o campo **Cenário Worldbuilding** lista as
  localidades de todos os mundos do livro, agrupadas por mundo, com **caminho
  completo** e **vários cenários** por capítulo.
- **Métricas reais:** **Entradas de worldbuilding** no Painel do Livro e nos
  cards de Meus Livros refletem os mundos associados.
- **Mundos no nível raiz:** os cards e a lista mostram os livros que usam cada
  mundo; o painel **Vínculos com livros** mostra a contagem e leva à aba
  **Livros**, com os títulos clicáveis.

### Localidades

- **Imagem da localidade:** JPG, PNG ou WEBP até **4 MB**, com miniatura na
  árvore e prévia na janela de edição.
- **Tipo da Localidade:** lista fechada com **49 tipos**, em ordem alfabética,
  além de **Não definido**.
- **Hierarquia:** uma localidade pode ficar dentro de outra e conter várias, em
  qualquer nível (Cidade → Bairro → Casa → Quarto; Taverna dentro de Cidade;
  Cômodo dentro de Casa), sem ciclos.
- **Árvore navegável:** a aba **Localidades** mostra a árvore com miniatura,
  nome, tipo, contador de sublocalidades e expandir/recolher, paginada de **20
  em 20** sem cortar uma subárvore entre páginas.
- **Raiz do mundo:** cada mundo tem uma localidade raiz do tipo **Mundo**, fixa
  no topo e fora dos mapas, do cenário e do PDF.
- **Ícone sem imagem:** quando a localidade não tem imagem, a árvore mostra o
  ícone do Tipo no estilo do Tipo do Mundo.
- **No PDF do mundo:** o documento mostra o **Tipo** de cada localidade.

### Mapas do Mundo

- **Mapas por escala:** vários mapas por mundo em **Mundo**, **Região**,
  **Cidade**, **Bairro** e **Prédio/Casa**, com âncora opcional e cinco fundos
  (Papel, Grade, Hex, Blueprint e Topográfico).
- **Editor:** posiciona localidades (arrastar ou criar pelo canvas), desenha
  polígonos, cria ligações rotuladas, apaga, desfaz/refaz e navega com pan/zoom.
- **Edição de polígono:** move a forma pelo interior, redimensiona pelas
  arestas e ajusta um vértice pelo nó.
- **Prédio/Casa:** a localidade vira um **cômodo retangular** movido e
  redimensionado por oito alças; a ferramenta **Porta** substitui
  Polígono/Ligação e as portas acompanham as paredes.
- **Plantas e filtros:** Cidade e Bairro usam plantas; todas as escalas filtram
  os tipos de localidade permitidos.
- **Localidade presa ao mapa:** só **Mundo** e **Região** compartilham
  localidades entre si; as demais ficam exclusivas do mapa.
- **No livro e no PDF:** a aba **Mapas** da seção Worldbuilding do livro lê os
  mapas e o **PDF do Mundo** ganha a seção **Mapas**.

### Capítulos

- **Dados Complementares:** a segunda aba reúne Foreshadowing, Plot Twist,
  Cliffhanger, Punch e K.O, com o K.O ao lado do Punch e o mesmo **Salvar**.
- **Vários cenários:** o campo **Cenário Worldbuilding** permite adicionar e
  remover localidades, mantendo a lista na ordem de inclusão.
- **Remoção de mundo:** ao desassociar um mundo, todos os cenários dele saem dos
  capítulos e os cenários dos outros mundos permanecem.
- **Correção do cenário:** a migração **v23** corrigiu a FK do capítulo que
  apontava para `localidade_antiga` e causava o erro `no such table` ao gravar
  o capítulo.

### Correções e polimento

- O Tab Panel da seção Worldbuilding do livro recuperou o fundo e a borda das
  outras abas do aplicativo.
- A árvore de localidades mantém os controles de página visíveis mesmo quando há
  uma única página.
- Ajustes de contagem, vínculos e carregamento nas telas de mundos e do livro.

### Por dentro (notas técnicas)

- Migrações **v17** (`livro_mundo`), **v18** (tipo, imagem e pai), **v19**
  (CHECK dos 49 tipos), **v20** (`mapa`, `mapa_localidade`, `mapa_forma` e
  `mapa_ligacao`), **v21** (`largura`/`altura` e `mapa_porta`), **v22** (raiz do
  mundo), **v23** (correção da FK do cenário) e **v24**
  (`capitulo_cenario`).
- **70 comandos Tauri**, **183 testes Rust**, `cargo fmt` e Clippy limpos.
- Verificadores: RF015 **31/31**, RF017 **28/28**, RF018 **17/17** e RF019
  **43/43**, com regressão dos requisitos anteriores.
- Commits finais: `558b17e` (app, dados complementares e cenários) e `0443f89`
  (specs, arquivamento). A rodada anterior de mapas ficou em `4224fa3` (app) e
  `d36e3f3` (specs).

### O que testar nesta build

- Associar dois mundos ao mesmo livro e alternar entre as abas.
- Criar uma cidade, um bairro dentro dela, uma casa dentro do bairro e um quarto
  dentro da casa; conferir a árvore, as miniaturas e as páginas.
- Criar mapas de **Mundo**, **Região**, **Cidade**, **Bairro** e **Prédio/Casa**;
  arrastar localidades, desenhar polígonos, mover/redimensionar e criar portas.
- Conferir os mapas na aba **Mapas** do livro e no PDF do Mundo.
- Abrir um capítulo, usar a aba **Dados Complementares** e salvar/reabrir.
- Adicionar dois cenários ao mesmo capítulo, remover um e conferir a ordem.
- Remover um mundo do livro e verificar que só os cenários dele saem.

**Download:** [release v0.1.0-build.4](../../releases/tag/v0.1.0-build.4).
Nesta primeira publicação, somente os instaladores de **Windows**.

Detalhes em `NOTAS-v0.1.0-build.4.md`.

---

## 0.1.0 build 3 — publicado em 02/11/2026

**Foco:** elenco do livro, painel de capítulos e gráficos.

- **Personagens do livro:** cards/lista paginada com **Qtd Capítulos** e os
  números dos capítulos de cada personagem.
- **Detalhe inline do personagem:** abaixo da grade, com quatro abas — **Dados
  Globais do Personagem**, **Personagem no Livro**, **Gráfico de Evolução** e
  **Eventos**.
- **Aba Eventos:** capítulo, tipo de evento e motivo, com paginação e sem os
  eventos neutros.
- **Ficha global:** vínculos com livros, contagem real e a **Curva de arco em
  cada livro**.
- **Capítulos:** painel em **Dados do Capítulo** e **Personagens do Capítulo**,
  com **Motivo do Tipo**, **Meta**, **Cenário Descritivo**, miniatura do
  retrato, **Nome - Papel** e as ajudas de Evento/Tipo de Evento.
- **Gráficos no Painel do Livro:** a **Curva de Progressão por Capítulo** abaixo
  dos módulos.
- Correções de vínculo, contagens do painel e cálculo dos gráficos.

Detalhes em `NOTAS-v0.1.0-build.3.md`.

---

## 0.1.0 build 2 — publicado

**Foco:** Linux e macOS.

- **Linux (amd64):** AppImage portátil e pacote `.deb`.
- **macOS:** `.dmg` universal (Intel e Apple Silicon).
- **Windows:** os mesmos instaladores da build 1.
- Conteúdo funcional igual ao da build 1: Meus Livros com as abas Resumo,
  Sinopse, Tema, Conflito e Voz Narrativa; elenco de personagens com papéis e
  vínculos; quadro de capítulos; gráficos de progressão e evolução.

---

## 0.1.0 build 1 — publicado

Primeira build de teste, para **Windows**.

- Meus Livros com as abas **Resumo**, **Sinopse**, **Tema**, **Conflito** e
  **Voz Narrativa/Tom/Tempo**.
- Elenco de personagens do livro, com papéis e vínculos.
- Quadro de capítulos com **Esboço**, **Rascunho**, **Revisão** e **Finalizado**.
- Gráficos de **Curva de Progressão por Capítulo** e **Evolução de Personagem**.
- Temas, splash, biblioteca de personagens, mundos, entradas e facções.
