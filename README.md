📋 ##Visão Geral do Projeto

Aplicação Web do tipo Single Page Application (SPA) desenvolvida em React.JS para publicação e consulta de anúncios classificados:

Frontoffice (Área Pública): Qualquer visitante pode pesquisar anúncios, filtrar por categoria, navegar por páginas (paginação), visualizar detalhes dos artigos, deixar comentários/perguntas e registar likes/favoritos.

Backoffice (Dashboard Privada): Área protegida por autenticação (username e password) onde cada utilizador/vendedor pode gerir os seus anúncios (Criar, Ler, Editar e Apagar — CRUD) e acompanhar estatísticas de visualizações e interações (likes).


🗄️ ##Modelo de Dados (Google Sheets + Sheety)

A base de dados será estruturada numa folha de cálculo do Google, exposta via endpoints REST pelo Sheety:

utilizadores: id, username, password, nome

categorias: id, nome (ex: Eletrónica, Veículos, Mobiliário, Desporto)

anuncios: id, titulo, descricao, preco, imagem (URL), categoriaId, utilizadorId, visualizacoes, likes

comentarios: id, anuncioId, autor, mensagem, data


✅ ##Tasklist de Desenvolvimento

###Fase 1: Configuração Inicial e Dados

[ ] Instalar Node.js e inicializar o projeto React no PhpStorm (ex: npm create vite@latest).

[ ] Criar repositório no GitHub (e adicionar pauloagsantos caso seja privado).

[ ] Configurar o roteamento da SPA (react-router-dom) e estrutura base de pastas (components, pages, services, assets).

[ ] Criar a folha de cálculo no Google Sheets com as abas utilizadores, categorias, anuncios e comentarios (incluindo dados de teste).

[ ] Ligar a folha de cálculo ao Sheety, ativar os métodos GET, POST, PUT e DELETE, e testar os endpoints.

###Fase 2: Solução Básica (Meta: até 14 valores)

[ ] Serviço de API: Criar funções para consumir os endpoints do Sheety (fetch ou axios).

[ ] Autenticação (Backoffice): Criar página de Login (username/password) validando contra a tabela utilizadores e guardar sessão (localStorage/Context).

[ ] CRUD no Backoffice:

[ ] Listar anúncios do utilizador autenticado.

[ ] Formulário para Criar novo anúncio (incluindo URL de pelo menos 1 imagem).

[ ] Formulário/Modal para Editar anúncio existente.

[ ] Botão para Apagar anúncio (com confirmação).

[ ] Frontoffice (Consulta):

[ ] Página inicial com listagem pública de todos os anúncios (card com imagem, título e preço).

[ ] Implementar pesquisa em tempo real por título/descrição.

[ ] Implementar paginação (segmentação dos resultados por páginas).

[ ] Página de detalhe de um anúncio individual.

[ ] Responsividade: Garantir layout adaptado a ecrãs de computador e smartphone (Mobile-First / Media Queries / Flexbox / Grid).


###Fase 3: Solução Intermédia (Meta: até 16 valores)

[ ] Relacionamento entre Entidades:

[ ] Associar cada anúncio a uma Categoria (categoriaId) no formulário de criação/edição.

[ ] Exibir o nome da categoria nos cards e na página de detalhe do anúncio.

[ ] Adicionar filtro por categoria no Frontoffice (em conjunto com a pesquisa e paginação).

[ ] (Opcional) Permitir gerir categorias no Backoffice.

Fase 4: Solução Avançada & Funcionalidades Extra (Meta: até 18+ valores)

[ ] Interação com Visitantes (Frontoffice):

[ ] Botão de Like / Favoritos na página do anúncio (atualiza o contador na API via PUT).

[ ] Secção de Comentários / Perguntas na página do anúncio (visitantes submetem via POST e leem via GET).

[ ] Métricas na Dashboard (Backoffice):

[ ] Incrementar automaticamente o contador de visualizacoes quando um visitante abre o detalhe do anúncio.

[ ] Mostrar resumo de estatísticas na dashboard do vendedor (total de anúncios, total de visualizações e total de likes).
