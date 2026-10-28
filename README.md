# TaleCraft — builds de teste

Este repositório publica os instaladores de teste do **TaleCraft**, um app
desktop de planejamento de livros de ficção científica, fantasia e terror.

## Baixar

Abra a [última release](../../releases/latest) e baixe:

- **TaleCraft_0.1.0_x64-setup.exe** — recomendado; instala sem privilégios de
  administrador.
- **TaleCraft_0.1.0_x64_en-US.msi** — alternativa para quem prefere MSI.
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

## Onde ficam os dados

Tudo é local. O banco fica em:

```text
%APPDATA%\com.talecraft.desktop\talecraft.db
```

Nenhum dado é enviado para servidores.

## O que testar nesta versão

- **Livros:** Meus Livros, dados gerais, abas Resumo, Sinopse, Tema, Conflito e
  Voz Narrativa.
- **Personagens do livro:** elenco, papéis, vínculos e ficha global.
- **Capítulos:** quadro com Esboço, Rascunho, Revisão e Finalizado, criação,
  edição, Motivo do Tipo, Motivo do Evento e arrastar entre status.
- **Gráficos:** Curva de Progressão por Capítulo e Evolução de Personagem.

## Enviar feedback

Anote a versão usada (aparece na barra superior), o que você fez, o que
esperava e o que aconteceu. Se possível, envie uma captura de tela.

Obrigado por testar!
