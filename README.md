# Instituto Alvia

Site institucional (onepage) e apresentação do **Instituto Alvia — Educação Especializada**,
escola particular especializada na escolarização de crianças neurodivergentes.

## Conteúdo

| Arquivo | O que é |
|---|---|
| `index.html` | Site onepage. Arquivo único, CSS e JS embutidos, logo em base64. |
| `apresentacao.html` | Deck de 17 slides (scroll-snap, setas do teclado, dots laterais). |
| `privacidade.html` | Política de privacidade (LGPD). Texto-base, ainda a validar juridicamente. |
| `fonts/` | Hey Comic — fonte de destaque da identidade (`.woff2` e `.ttf`). |
| `video/` | Vídeo de fundo da faixa da citação. Placeholder livre (Pexels, sem atribuição). |

## Identidade

**Cores** (retiradas do logo)

| Token | Hex | Uso |
|---|---|---|
| `--navy` | `#2F5C7C` | azul do wordmark |
| `--navy-deep` | `#1B3A50` | faixas escuras |
| `--ink` | `#16303F` | texto principal |
| `--terra` | `#C06C50` | acento, botões, destaques |
| `--cream` | `#FBF7F1` | fundo |

**Tipografia**

- **Montserrat** (Google Fonts) — corpo, labels, números
- **Hey Comic** (local, `fonts/`) — títulos e destaques

> A Hey Comic **não possui** o dígito `0`, `:`, `;`, travessão (`—`), `º`/`ª` e apóstrofo
> curvo (`’`). O `@font-face` usa `unicode-range` para excluir essa faixa, e todos os
> números foram deliberadamente atribuídos à Montserrat. Se você aplicar a Hey Comic em
> algum elemento novo, confira se há números ou dois-pontos nele.

## Fotos

Todas as imagens do site são **placeholders do Unsplash** (licença livre) e estão
declaradas em variáveis CSS no topo do `index.html`:

```css
--img-hero:   /* hero — 7 opções comentadas, uma ativa */
--hero-pos:   /* enquadramento da hero, ex.: center 48% */
--img-sobre:  /* foto da seção "A escola" */
--img-familia:/* textura da faixa com a citação */
```

A galeria de ambientes usa `<img>` direto no HTML, e dois tiles (**cozinha educacional**
e **parque acessível**) são slots estilizados aguardando foto real.

Ao trocar pelas fotos da escola: salve em `img/`, troque as URLs e mantenha o
`loading="lazy"` nas imagens da galeria.

## Pendências

- [ ] Substituir fotos placeholder por fotos reais da escola
- [ ] Definir a foto final da hero (opções 0 a 6 comentadas no CSS)
- [ ] Substituir o vídeo de fundo placeholder (`video/`) por filmagem própria da escola
- [ ] Validar juridicamente a Política de Privacidade (razão social/CNPJ, DPO, provedores, retenção)
- [ ] Ligar o formulário de contato a um backend (Formspree, Vercel Function ou similar)
- [ ] Revisar textos com a coordenação pedagógica
- [ ] Favicon e imagem de compartilhamento (Open Graph)
- [ ] Adicionar números de investimento e projeção ao deck (slide entre o 14 e o 15)

## Rodando local

Não há build. Abrir o `index.html` no navegador já funciona — mas, para a fonte local
carregar sem bloqueio de CORS, prefira um servidor:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Publicando

Funciona como site estático em qualquer lugar (GitHub Pages, Vercel, Netlify).
Para GitHub Pages: **Settings → Pages → Branch: `main` / root**.
