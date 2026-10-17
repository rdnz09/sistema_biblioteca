# Módulo 8 — Front-end do Sistema Biblioteca

## O que está incluído

- `public/index.html`: tela de login.
- `public/painel.html`: painel com links de navegação.
- `public/livros.html`: formulário, busca, tabela e paginação.
- `public/movimentacoes.html`: formulário e histórico.
- `public/css/estilo.css`: identidade visual compartilhada e responsiva.
- `correcoes/`: arquivos para corrigir problemas identificados no repositório.

A identidade visual usa grafite, azul-claro e a fonte Nunito. Os IDs esperados pelo Módulo 9 foram preservados.

## Como instalar no projeto

1. Faça backup do projeto ou crie um commit antes de alterar arquivos.
2. Copie a pasta `public` deste pacote para a raiz do projeto, ao lado de `src`.
3. Abra `src/app.js` e aplique as duas adições descritas em `correcoes/app.js.adicao.txt`. Não apague as rotas que já existem.
4. Compare `correcoes/movimentacaoRoutes.js` com `src/routes/movimentacaoRoutes.js` e aplique a correção.
5. Compare `correcoes/Movimentacao.js` com `src/models/Movimentacao.js` e aplique a correção. A versão do repositório declara a variável `Sequelize`, mas utiliza `sequelize.define`, o que causa `ReferenceError`.
6. Inicie o servidor pelo comando usado no projeto, por exemplo `node src/app.js`.
7. Acesse `http://localhost:3000`.

## Correções identificadas no repositório

- `src/routes/movimentacaoRoutes.js` estava importando o controller de livros e registrando endpoints `/livros`; a rota deve apontar para o controller de movimentações e usar `/movimentacoes`.
- `src/models/Movimentacao.js` declarava `const Sequelize = require(...)`, mas chamava `sequelize.define(...)`. O nome da variável foi padronizado para `sequelize`.
- O `app.js` precisa servir a pasta `public` com `express.static` para abrir as páginas pelo Express.

## Importante

Este módulo cuida da interface. Os formulários ainda não enviam dados à API; a integração com login, token, cadastro, busca, paginação e movimentações fica para o Módulo 9. As tabelas mostram mensagens de orientação em vez de inventar registros do banco.
