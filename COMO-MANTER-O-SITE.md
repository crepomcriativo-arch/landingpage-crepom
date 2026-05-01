# 📋 Guia de Manutenção – Site Crepom

---

## 📁 Estrutura de pastas

```
crepom-site/
│
├── index.html              ← O site completo (edite aqui)
│
├── videos/
│   ├── hero.mp4            ← Vídeo de fundo do topo (hero)
│   ├── video1.mp4          ← Vídeos do catálogo
│   ├── video2.mp4
│   └── ...
│
└── thumbs/
    ├── thumb1.jpg          ← Thumbnail do video1 (print do vídeo)
    ├── thumb2.jpg
    └── ...
```

---

## ▶️ Como adicionar um novo vídeo ao catálogo

1. Coloque o arquivo `.mp4` na pasta `videos/` (ex: `video7.mp4`)
2. Coloque um print do vídeo na pasta `thumbs/` (ex: `thumb7.jpg`)
3. Abra o `index.html` e encontre a seção comentada `CATÁLOGO DE VÍDEOS`
4. Copie um bloco de vídeo existente e cole logo abaixo do último
5. Troque `video7.mp4`, `thumb7.jpg`, o título e a descrição

---

## 🗑️ Como remover um vídeo

Abra o `index.html`, encontre o bloco que começa com  
`<!-- ── VÍDEO X ──` e delete tudo até o `</div>` que fecha o card.

---

## ✏️ Como mudar textos

Abra o `index.html` e procure (Ctrl+F) pelo texto que quer mudar.  
Os textos principais são:

| O que mudar | Onde encontrar |
|---|---|
| Frase do hero | `A criatividade precisa encontrar escala.` |
| Subtítulo hero | Parágrafo abaixo do h1 |
| Texto "Sobre" | Seção `SOBRE A CREPOM` |
| Título do vídeo | Cada `<p class="video-nome">` |
| Descrição do vídeo | Cada `<p class="video-desc">` |
| WhatsApp | Número no `href` do botão de WhatsApp |
| E-mail | Endereço no `href="mailto:..."` |

---

## 🎨 Como mudar as cores

No início do `index.html`, na seção `:root { }`, estão as variáveis de cor:

```css
--laranja:   #F0A030;
--rosa:      #D94080;
--roxo:      #7030A0;
--azul:      #1A3A6C;
--fundo:     #07070F;    /* cor de fundo da página */
--texto:     #FFFFFF;
--texto-sec: #9999BB;    /* textos secundários */
```

---

## 🌐 Como hospedar o site (passo a passo)

### Opção A — Netlify (recomendado, gratuito)

1. Acesse [netlify.com](https://netlify.com) e crie uma conta gratuita
2. Clique em **"Add new site" → "Deploy manually"**
3. **Arraste a pasta `crepom-site`** para a área indicada
4. O site vai no ar em segundos com um link temporário (ex: `algo.netlify.app`)
5. Para conectar o domínio `crepom.com`:
   - Vá em **Site settings → Domain management → Add custom domain**
   - Digite `crepom.com`
   - O Netlify vai te mostrar os **nameservers** — você leva esses dados para onde o domínio foi comprado (GoDaddy, Registro.br, etc.) e aponta lá

### Opção B — Vercel (também gratuito)

Mesmo processo: [vercel.com](https://vercel.com), fazer upload da pasta, conectar domínio.

---

## 🎬 Como hospedar os vídeos

**Se os vídeos forem pequenos (até ~50MB cada):**  
Coloque-os direto na pasta `videos/` junto com o site — simples assim.

**Se os vídeos forem grandes (+100MB):**  
Recomendo o [Bunny.net](https://bunny.net) ou [Cloudflare R2](https://cloudflare.com/developer-platform/r2/) — são serviços baratos de armazenamento. Você sobe os vídeos lá e usa a URL gerada no lugar do `src="videos/videoN.mp4"`.

---

## 💡 Dica: gerar thumbnails rapidamente

Abra o vídeo no VLC ou em qualquer player, pause no frame que quer usar, e tire um print. Salve como `.jpg` na pasta `thumbs/`.

---

*Qualquer dúvida, é só chamar!*
