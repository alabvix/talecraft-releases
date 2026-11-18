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

## 0.1.0 build 4 — não publicado

**Foco:** o **mundo do livro** e as **localidades** do Worldbuilding.

### Destaques para o post

1. **Cada livro agora tem um ou mais mundos.** O escritor associa os mundos
   globais ao livro e consulta as entradas na própria página do livro.
2. **As localidades viraram um mapa do cenário.** Cada uma tem imagem, tipo e
   pode ficar dentro de outra, formando árvores como Cidade › Bairro › Casa ›
   Quarto.

### Livro e mundo

- **Worldbuilding do livro:** a seção deixa de ser uma tela informativa e passa a
  ter uma aba por mundo associado, na ordem de associação, com o resumo do mundo
  e as seis categorias de entradas (Localidades, Raças e Povos, Artefatos, Armas,
  Eventos e Sistemas).
- **Um ou mais mundos por livro:** antes o produto previa um único mundo;
  agora o livro pode se passar em vários, e o mesmo mundo pode servir a vários
  livros.
- **Associar mundos:** grade paginada com busca, seleção múltipla e selo **Já
  associado**; remover um mundo do livro limpa, com aviso, o cenário dos
  capítulos que usavam localidades dele.
- **Criar entradas pelo livro:** a categoria do mundo aceita **Nova entrada**
  direto na seção do livro, sem sair para o nível raiz.
- **Cenário dos capítulos:** o campo **Cenário Worldbuilding** lista as
  localidades de todos os mundos do livro, agrupadas por mundo, e mostra o
  **caminho completo** (ex.: `Porto › Centro › Solar › Quarto`).
- **Métricas reais:** **Entradas de worldbuilding** no Painel do Livro e nos
  cards de Meus Livros deixam de ser 0 e refletem os mundos associados.
- **Mundos no nível raiz:** os cards e a lista mostram os livros que usam cada
  mundo; o painel **Vínculos com livros** mostra a contagem e leva à nova aba
  **Livros**, com os títulos clicáveis.
- **Abrir mundo:** a aba do mundo no livro leva ao detalhe do mundo no nível raiz.

### Localidades

- **Imagem da localidade:** JPG, PNG ou WEBP até **4 MB**, com miniatura na
  árvore e prévia na janela de edição.
- **Tipo da Localidade:** lista fechada com **49 tipos** — de **Arena** e
  **Armazém** a **Vila** e **Vilarejo**, passando por **Cidade**, **Casa**,
  **Castelo**, **Caverna**, **Igreja**, **Mar**, **Palácio**, **Praça**,
  **Ruína** e **Templo** —, em ordem alfabética, além de **Não definido**.
- **Hierarquia:** uma localidade pode ficar dentro de outra e conter várias,
  em qualquer nível (Cidade → Bairro → Casa → Quarto; Taverna dentro de Cidade;
  Cômodo dentro de Casa). A contenção é livre por tipo e o sistema recusa ciclos.
- **Árvore navegável:** a aba **Localidades** mostra a árvore com miniatura,
  nome, tipo, contador de sublocalidades e expandir/recolher, paginada de **20
  em 20** sem cortar uma subárvore entre páginas.
- **Editar e mover:** trocar o pai move a localidade e todos os seus
  descendentes; a lista de pais esconde a própria localidade e os descendentes.
- **No PDF do mundo:** o documento passa a mostrar o **Tipo** de cada localidade.

### Correções e polimento

- O Tab Panel da seção Worldbuilding do livro recuperou o fundo e a borda das
  outras abas do aplicativo.
- A árvore de localidades mantém os controles de página visíveis mesmo quando há
  uma única página.
- Ajustes de contagem, vínculos e carregamento nas telas de mundos e do livro.

### Por dentro (notas técnicas)

- Migrações **v17** (`livro_mundo`), **v18** (tipo, imagem e pai da localidade) e
  **v19** (CHECK ampliado aos 49 tipos, recriando a tabela com as FKs desligadas
  durante as migrações).
- **65 comandos Tauri**, **161 testes Rust**, `cargo fmt` e Clippy limpos.
- Verificadores: `verificar-rf017.mjs` **26/26** e `verificar-rf018.mjs`
  **17/17**, com regressão completa de RF002 a RF018.
- Commits: `b2a1df4` (app, RF017), `a0983b0` (specs, RF017), `93596f6` (site,
  RF017), `bc95bf8` (app, RF018) e `4b75927` (specs, RF018).

### O que testar nesta build

- Associar dois mundos ao mesmo livro e alternar entre as abas.
- Criar uma cidade, um bairro dentro dela, uma casa dentro do bairro e um quarto
  dentro da casa; conferir a árvore, as miniaturas e as páginas.
- Enviar uma imagem de localidade e tentar um arquivo grande ou inválido.
- Escolher o cenário de um capítulo pelo caminho completo.
- Remover um mundo do livro e conferir o aviso dos capítulos sem cenário.
- Observar a métrica **Entradas de worldbuilding** no Painel e nos cards.

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
