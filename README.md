# Nova Paulista SP — Site de Regras

Site estático (HTML/CSS/JS puro, sem build) com a identidade visual da
NOVA PAULISTA SP: fundo escuro, cromado e vermelho puxando pela logo
oficial do servidor.

## Como usar
Abra `index.html` diretamente no navegador, ou hospede a pasta inteira em
qualquer serviço de site estático (GitHub Pages, Netlify, Vercel, ou o
painel de hospedagem do próprio servidor). Todas as páginas usam links
relativos entre si e para `assets/`, então a estrutura de pastas precisa
ser mantida junto.

## Estrutura
- `index.html` — página inicial, com a logo em destaque
- `regras-*.html` — regras gerais, de ouro, do Discord, especiais
- `punicoes-strikes.html` — escala de punições
- `restaurantes.html`
- `regras-policia.html`, `regras-hospital.html`, `regras-ilegal.html`,
  `regras-de-acoes.html` — regras de roleplay por área
- `acoes-*.html` — ações comuns, pequeno/médio/grande porte
- `administracao.html` — como denunciar e recorrer
- `doacoes.html`
- `assets/nova-paulista-logo.png` — logo oficial (fundo transparente),
  usada no topo, na home e no rodapé de todas as páginas

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
  fundo transparente e proporção parecida (aprox. 2.1:1) para o layout do
  topo e da home continuarem alinhados.
- O favicon fica embutido como base64 direto no `<link rel="icon">` de
  cada página (não depende de arquivo externo).

## Funcionalidades incluídas
- Busca instantânea no menu lateral (filtra por texto)
- Menu lateral recolhível no mobile
- Barra de progresso de leitura no topo
- Botão "voltar ao topo" nas páginas de conteúdo
- Links de âncora automáticos em cada título de seção (passe o mouse
  sobre um título para ver o `#`)
- Ícones nos avisos (Proibido / Atenção / Nota) e no menu lateral
