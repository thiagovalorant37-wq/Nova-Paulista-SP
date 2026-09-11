# Nova Paulista SP — Site de Regras

Site estático (HTML/CSS/JS puro, sem build) com a identidade visual da
NOVA PAULISTA SP: fundo escuro, cromado e vermelho puxando pela logo/banner
oficial do servidor.

## Como usar localmente
Abra `index.html` diretamente no navegador, ou hospede a pasta inteira em
qualquer serviço de site estático. Todas as páginas usam links relativos
entre si e para `assets/`, então a estrutura de pastas precisa ser mantida
junto.

## Deploy no Render
O repositório já vem com um `render.yaml` pronto (Blueprint), então basta:

1. Subir esta pasta para um repositório no GitHub (ou GitLab/Bitbucket).
2. No painel do Render, clique em **New +** → **Blueprint**.
3. Selecione o repositório — o Render vai detectar o `render.yaml`
   automaticamente e configurar o serviço `nova-paulista-sp` como
   **Static Site**, sem comando de build (o site já está pronto, é HTML puro).
4. Clique em **Apply** / **Deploy**. Em menos de um minuto o site estará no ar
   em `https://nova-paulista-sp.onrender.com` (ou o subdomínio que o Render
   atribuir).

Se preferir configurar manualmente em vez de usar o Blueprint:
- **New +** → **Static Site**
- **Build Command:** deixe em branco (ou `echo "sem build"`)
- **Publish directory:** `.` (raiz do projeto)

Depois do primeiro deploy, troque o domínio usado nas tags de SEO
(`<link rel="canonical">`, `og:image`, `robots.txt`, `sitemap.xml`) pelo
domínio final, caso você conecte um domínio próprio.

## Estrutura
- `index.html` — página inicial, com a logo/banner em destaque
- `regras-*.html` — regras gerais (mais de 130 itens), de ouro, do Discord,
  especiais
- `punicoes-strikes.html` — escala de punições
- `regras-policia.html`, `regras-hospital.html`, `regras-ilegal.html`,
  `regras-de-acoes.html` — regras de roleplay por área
- `administracao.html` — como denunciar e recorrer
- `doacoes.html`
- `assets/nova-paulista-logo.png` — logo oficial em recorte transparente
  (usada no topo, na home e no rodapé de todas as páginas)
- `assets/nova-paulista-banner.png` — banner/arte completa (fundo preto),
  usada como imagem de compartilhamento (Open Graph / redes sociais)
- `render.yaml` — Blueprint de deploy estático para o Render
- `robots.txt`, `sitemap.xml` — arquivos de SEO

> As páginas de ações por porte (pequeno/médio/grande) e a de
> restaurantes foram removidas temporariamente a pedido da administração
> — o conteúdo específico de cada alvo será refeito e adicionado depois.

## Personalizar
- Cores, fontes e o tema inteiro estão no bloco `<style>` de cada
  página (idêntico em todas — busque e substitua se for trocar algo em
  massa). As cores principais ficam nas variáveis `:root` no topo do
  `<style>`: `--bg`, `--red`, `--text`, etc.
- O menu lateral, o topo (topbar), o rodapé e o script de cada página
  seguem o mesmo padrão — para adicionar uma página nova, copie a
  estrutura de uma página existente (ex.: `doacoes.html`) e troque o
  conteúdo dentro de `.content-inner`.
- Para trocar a logo, substitua `assets/nova-paulista-logo.png` mantendo
  fundo transparente e proporção parecida para o layout do topo e da home
  continuarem alinhados.
- O favicon fica embutido como base64 direto no `<link rel="icon">` de
  cada página (não depende de arquivo externo) — já atualizado com a
  logo nova.
- Tags de SEO/Open Graph (`<meta name="description">`, `og:*`,
  `twitter:*`) ficam logo abaixo do `<title>` de cada página.

## Funcionalidades incluídas
- Busca instantânea no menu lateral (filtra por texto)
- Menu lateral recolhível no mobile
- Barra de progresso de leitura no topo
- Botão "voltar ao topo" nas páginas de conteúdo
- Links de âncora automáticos em cada título de seção (passe o mouse
  sobre um título para ver o `#`)
- Ícones nos avisos (Proibido / Atenção / Nota) e no menu lateral
- Animações de entrada (topo, menu lateral e hero da home), efeito de
  brilho ao passar o mouse na logo, e revelação suave de blocos de
  texto/tabelas/avisos conforme a página é rolada (respeita a opção do
  sistema "reduzir movimento", para quem prefere sem animação)
- Meta tags de SEO e Open Graph em todas as páginas, prontas para
  compartilhamento em redes sociais e Discord
- `render.yaml` pronto para deploy em um clique no Render

## Changelog desta versão
- Logo/banner do servidor atualizados em todas as páginas (topo, home e
  rodapé), com recorte transparente gerado a partir da arte oficial.
- Favicon regerado a partir da nova logo.
- Mais de 100 novas regras gerais de FiveM adicionadas em
  `regras-gerais.html` (cheats/exploits, multicontas, identidade de
  personagem, character switch, zonas seguras, trânsito e veículos,
  NPCs/farm/economia, props, comunicação, streaming, denúncias/tickets,
  eventos oficiais, facções e gangues).
- Meta tags de SEO/Open Graph/Twitter Card adicionadas em todas as
  páginas.
- Arquivos `render.yaml`, `robots.txt` e `sitemap.xml` adicionados para
  facilitar o deploy e a indexação do site.
