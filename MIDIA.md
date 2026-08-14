# Mídia do quiz (imagens, som e vídeo)

Mapa de tudo que a página carrega, o que está funcionando e o que falta.
Todos os caminhos são configurados no bloco `QUIZ_CONFIG`, no topo do `index.html`.

---

## 1. Arquivos que FALTAM no repositório

Estes dois são chamados pelo código mas não existem aqui. Precisam ser enviados por você.

| Arquivo | Onde aparece | Situação hoje |
|---|---|---|
| `img/helena.png` | Foto no rodapé, "Conteúdo de Mãe Helena de Oxóssi" | **Ausente** → entra um avatar cinza neutro |
| `img/depoimentos/1.png` | Carrossel — print do Instagram (@ceucomcores) | **Ausente** → slide cai para o texto |
| `img/depoimentos/2.png` | Carrossel — print do Instagram ("surreal!") | **Ausente** → slide cai para o texto |
| `img/depoimentos/3.png` | Carrossel — print do WhatsApp (bônus) | **Ausente** → slide cai para o texto |

Basta soltar os arquivos nas pastas `img/` e `img/depoimentos/` com esses nomes
exatos. Se preferir outro nome, ajuste `FOTO_AUTORA` ou `DEPOIMENTOS` no
`QUIZ_CONFIG`.

---

## 1b. Música de fundo ✅

`audio/ori-background.mp3` — 4min46s, em loop, tocando a 15% de volume.

O arquivo enviado passou por três ajustes antes de entrar:

- **0,58 s de silêncio no começo foram cortados.** O arquivo terminava em volume
  cheio e recomeçava com silêncio, o que dava um corte seco a cada volta do loop.
- **Ganho de +9 dB.** O original tinha pico em −12,9 dB e média em −27,9 dB; a
  15% de volume ficaria praticamente inaudível no celular. Agora o pico é
  −4,1 dB e a média −19,3 dB, com folga de sobra para não distorcer.
- **Fade de 0,8 s na entrada e 1,6 s na saída**, para a emenda do loop virar uma
  respirada em vez de um corte.

Reencodado de 128 para 96 kbps: 4,6 MB → 3,3 MB. É música ambiente a volume
baixo, a diferença não se percebe.

O volume fica em `MUSICA_VOLUME` no `QUIZ_CONFIG`. Suba para `0.25` se achar
discreto demais, desça para `0.10` se incomodar.

Se um dia trocar a faixa, use uma que você tenha direito de usar (própria,
comprada ou de banco livre de royalties). Ponto de atabaque gravado em terreiro
sem autorização não deve ir para uma página de venda.

---

## 2. Imagens carregadas de fora (quizsarava.lovable.app)

Hoje **todas** as imagens do quiz vêm de outro site, via link direto:

```
https://quizsarava.lovable.app/assets/<arquivo>
```

**Risco:** os nomes têm hash de build (`-CPEGKlyv`, `-BJo4pGll`…). Quando aquele
site for republicado, os hashes mudam e **todas as imagens somem de uma vez**.
Não há aviso prévio.

**Solução:** baixar os arquivos abaixo para a pasta `img/` e trocar uma linha só
no `QUIZ_CONFIG`:

```js
ASSET_BASE: "img/",
```

### Em uso no fluxo atual

| Arquivo | Onde aparece |
|---|---|
| `personagem-iniciante-novo-CPEGKlyv.png` | Card "Sou Iniciante" + resultado |
| `personagem-umbandista-novo-CFD7hGAP.png` | Card "Já sou Umbandista" + resultado |
| `personagem-guia-3d-C5LUUTbc.png` | Selo "Pai Oxalá" (aparece em quase toda tela) |
| `option-orixas-BJo4pGll.png` | Pergunta 1, opção "Os Orixás" |
| `option-preto-velhos-CQh7x9tk.png` | Pergunta 1, opção "Os Pretos Velhos" |
| `option-caridade-CVJE28jO.png` | Pergunta 1, opção "A Caridade" |
| `question-entidades-DMFtjsZs.png` | Pergunta 2 |
| `question-pontos-riscados-DSbgj6ry.png` | Pergunta 3 |
| `question-rituais-CbJQp2Lx.png` | Pergunta 4 |
| `question-altar-CvW1ySTd.png` | Pergunta 5 |
| `question-elementos-DQvYZev0.png` | Pergunta 6 |

### Carregadas no código, mas nunca exibidas

Estas telas existem prontas no `index.html`, porém estão fora do `FLOW`
(a sequência de telas). As imagens nunca chegam a aparecer:

| Arquivo | Tela | Por que não aparece |
|---|---|---|
| `question-dificuldades-Dl1jNYxa.gif` | Pergunta "dificuldade" | pergunta fora do fluxo |
| `question-aplicativo-DY88zYaI.png` | Pergunta "app" | pergunta fora do fluxo |
| `question-orixas-CFli7e6m.png` | Pergunta "arquétipos" | pergunta fora do fluxo |
| `result-option-sim-CeTr9lC_.png` | Opção "Sim, seria incrível!" | pergunta fora do fluxo |
| `option-talvez-DPJvBUqf.png` | Opção "Talvez" | pergunta fora do fluxo |
| `option-incerteza-BRhgOzPW.png` | Opção "Não tenho certeza" | pergunta fora do fluxo |
| `bonus-1-C8Q0zK5Z.png` | Tela de bônus | tela `bonus` fora do fluxo |
| `bonus-2-C4A5njPY.png` | Tela de bônus | tela `bonus` fora do fluxo |
| `bonus-3-Cm0f-TZ4.png` | Tela de bônus | tela `bonus` fora do fluxo |
| `bonus-4-Be6u0da-.png` | Tela de bônus | tela `bonus` fora do fluxo |
| `bonus-6-mais-B82pbZGs.png` | Tela de bônus | tela `bonus` fora do fluxo |
| `super-mockup-oferta-ZDvK5T8y.png` | Tela "pitch" | tela `pitch` fora do fluxo |

Também há duas imagens declaradas em `IMG` que **nenhuma tela usa**:

- `preco-1990.png` (`IMG.preco`)
- `wiapy-secure-checkout.png` (`IMG.secure`)

---

## 3. Vídeos

| Vídeo | Origem | Onde aparece |
|---|---|---|
| Prévia do Aplicativo | `video/app-mapa-mental.mp4` (local) | Tela "promessa" — **em uso** |
| Versão impressa e encadernada | Vimeo `1180197942` | Tela "delivery" — **fora do fluxo, nunca aparece** |

A prévia do app é hospedada no próprio projeto. O arquivo original tinha 23 MB,
1034×1920, com o átomo `moov` no fim (o navegador teria que baixar tudo antes de
começar a tocar). A versão publicada tem **8,4 MB**, 640×1188, 24 fps, com
`+faststart`, e o texto continua legível porque o vídeo é exibido num box de
~290 px de largura.

Os dois carregam por fachada: mostra a capa e só baixa o vídeo depois do clique.
A capa da prévia é `img/app-mapa-mental-capa.jpg`, extraída do próprio vídeo.

Para trocar o vídeo depois, substitua o arquivo em `video/` e gere uma capa
nova, ou ajuste `VIDEO_APP` e `VIDEO_APP_POSTER` no `QUIZ_CONFIG`.

**Atenção com a banda da Vercel:** cada play baixa ~8,4 MB. No plano Hobby o
limite é 100 GB/mês, o que dá por volta de 12 mil plays. Se a página escalar,
vale mover o vídeo para o Vimeo ou para um CDN.

---

## 3b. Depoimentos (carrossel)

Ficam logo abaixo do vídeo na tela "promessa", e também no resultado e na
oferta. São configurados em `DEPOIMENTOS`, no `QUIZ_CONFIG`.

Cada item aceita duas formas:

- `print:"img/depoimentos/1.png"` → mostra a captura da conversa;
- `texto:"..."` → mostra um card com aspas, estrelas e assinatura.

Quando o item tem os dois, o print manda; se a imagem não carregar, o slide cai
sozinho para o texto. É por isso que o carrossel já funciona hoje, mesmo sem os
prints terem sido enviados.

O carrossel é feito com scroll-snap nativo: arrasta no celular, tem bolinhas
para navegar e setas no desktop. Sem biblioteca externa.

Detalhes de privacidade e autorização estão em `img/depoimentos/README.md`.

---

## 4. Fluxo de telas atual

```
intro → q0 → q1 → q2 → q6 → q7 → q8 → name → analyzing → result → promessa → offer
```

Telas prontas no código mas fora do fluxo: `pitch`, `visao`, `delivery`,
`bonus`. É por isso que as imagens de bônus, o mockup e o segundo vídeo não
aparecem. Para reativar alguma, basta incluir o nome dela no array `FLOW`.
