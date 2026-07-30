# Site + Painel de Imóveis — Gino Bolognesi Participações

Site profissional (o design que você aprovou) + **painel de administração** onde qualquer
pessoa da empresa edita imóveis, preços, descrições e **fotos** — sem mexer em código.
Hospedagem e painel são **gratuitos**.

---

## O que tem nesta pasta
- `index.html` — o site.
- `data/imoveis.json` — onde ficam os imóveis (é o que o painel edita).
- `admin/` — o painel de controle (`config.yml` e `index.html`).
- `images/imoveis/` — onde as fotos enviadas pelo painel são guardadas.
- `robots.txt`, `sitemap.xml` — SEO.

> Enquanto o site não está publicado, se você abrir o `index.html` no seu computador ele
> mostra 9 imóveis de exemplo embutidos. Depois de publicado, ele passa a ler o
> `data/imoveis.json` (o que o painel edita).

---

# COMO COLOCAR NO AR (siga na ordem)

A parte técnica do código já está 100% pronta. Faltam os passos que só **você** pode fazer,
porque envolvem **as suas contas e senhas** (eu não posso acessar suas contas). São gratuitos.
Se preferir, eu te acompanho ao vivo nesses passos — é só pedir.

## PARTE 1 — Publicar o site (grátis)

1. **Crie uma conta no GitHub** (grátis): https://github.com — anote usuário e senha.
2. Clique em **New repository**, dê um nome (ex.: `gbvendas`), deixe **Public**, e crie.
3. Na página do repositório, clique em **"uploading an existing file"** e **arraste todos os
   arquivos e pastas desta pasta** para lá (index.html, admin/, data/, images/, etc.). Confirme (**Commit**).
4. **Crie uma conta no Cloudflare** (grátis): https://dash.cloudflare.com/sign-up
5. No menu, vá em **Workers & Pages → Create → Pages → Connect to Git**, escolha o
   repositório `gbvendas`. Em configurações de build **deixe tudo em branco** (não há build) e clique
   **Save and Deploy**. Em ~1 minuto o site fica no ar num endereço tipo `gbvendas.pages.dev`.

## PARTE 2 — Ligar o seu domínio gbvendas.com.br

1. No projeto do Cloudflare Pages, abra **Custom domains → Set up a domain** e digite
   `www.gbvendas.com.br` (e depois `gbvendas.com.br`).
2. O Cloudflare vai te mostrar as instruções de DNS. O caminho mais simples é **apontar o
   domínio para o Cloudflare**: entre no **registro.br** (onde você comprou o domínio), vá em
   **Servidores DNS** e troque pelos servidores que o Cloudflare indicar.
3. Pode levar de alguns minutos a algumas horas para propagar. O **HTTPS (cadeado)** é ativado
   automaticamente e de graça.

> Esse passo mexe no registro.br (login seu). Se travar, me chame que faço junto com você.

## PARTE 3 — Ativar o painel (login em /admin)

O painel precisa "logar" no GitHub para salvar as edições. Há duas formas — comece pela simples:

- **Forma simples (1 usuário/empresa):** ao abrir `gbvendas.com.br/admin`, o Sveltia permite
  entrar com um **Token Pessoal do GitHub**. Você gera esse token em
  GitHub → *Settings → Developer settings → Personal access tokens*, dá permissão ao
  repositório, e cola no painel. Pronto.
- **Forma "Entrar com GitHub" (vários usuários, mais bonita):** publica-se um pequeno
  autenticador gratuito (Cloudflare Worker `sveltia-cms-auth`) e cria-se um *GitHub OAuth App*.
  Passo a passo oficial: https://github.com/sveltia/sveltia-cms-auth

> Este é o **único** passo mais "técnico". Recomendo fortemente fazermos **juntos, ao vivo** —
> em 10-15 minutos fica pronto e nunca mais se mexe.

## PARTE 4 — Como a equipe edita no dia a dia (a parte fácil!)

1. Acesse **gbvendas.com.br/admin** e faça login.
2. Clique em **"Imóveis do site" → "Lista de imóveis"**.
3. Para **editar**: clique no imóvel e mude título, preço, descrição, etc.
   Para **adicionar**: clique em **"Adicionar Imóvel"**.
   Para **fotos**: no campo *Fotos*, **arraste as imagens** ou clique para enviar.
4. Clique em **Salvar/Publicar**. Em **1 a 2 minutos** o site atualiza sozinho. 🎉

Não precisa saber nada de programação — é só preencher formulário e arrastar foto.

---

## Depois de no ar (marketing)
- **Google Search Console** (search.google.com/search-console): cadastre `gbvendas.com.br` e
  envie o `sitemap.xml`.
- **Perfil da Empresa no Google** (google.com/business): crie com endereço/telefone de Araras —
  é o que mais ajuda a aparecer nas buscas locais.
- Troque os **preços e fotos de exemplo** pelos reais (pelo painel) e substitua os **depoimentos**
  por avaliações verdadeiras de clientes.

Quando estiver no ar, posso montar a **campanha do Google Ads** para você aparecer no topo.
