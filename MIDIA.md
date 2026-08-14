# Mídia do quiz (imagens, som e vídeo)

Mapa de tudo que a página carrega, o que está funcionando e o que falta.
Todos os caminhos são configurados no bloco `QUIZ_CONFIG`, no topo do `index.html`.

---

## 1. Arquivos que FALTAM no repositório

Estes dois são chamados pelo código mas não existem aqui. Precisam ser enviados por você.

| Arquivo | Onde aparece | Situação hoje |
|---|---|---|
| `audio/ori-background.mp3` | Música de fundo (botão 🔊 no topo) | **Ausente** → o botão de música some sozinho |
| `img/helena.png` | Foto no rodapé, "Conteúdo de Mãe Helena de Oxóssi" | **Ausente** → entra um avatar cinza neutro |

Basta soltar os arquivos nas pastas `audio/` e `img/` com esses nomes exatos.
Se preferir outro nome, ajuste `MUSICA` e `FOTO_AUTORA` no `QUIZ_CONFIG`.

Sobre a música: use uma faixa que você tenha direito de usar (própria, comprada
ou de banco livre de royalties). Ponto de atabaque gravado em terreiro sem
autorização não deve ir para uma página de venda.

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

## 3. Vídeos (Vimeo)

| Vídeo | ID | Onde aparece |
|---|---|---|
| Prévia do Aplicativo | `1180197671` | Tela "promessa" — **em uso** |
| Versão impressa e encadernada | `1180197942` | Tela "delivery" — **fora do fluxo, nunca aparece** |

Os vídeos carregam por fachada: mostra a miniatura e só carrega o player do
Vimeo depois do clique (bom para velocidade). A miniatura vem do
`i.vimeocdn.com`; se o link expirar, agora o box fica escuro com o botão ▶ em
vez de mostrar ícone de imagem quebrada.

---

## 4. Fluxo de telas atual

```
intro → q0 → q1 → q2 → q6 → q7 → q8 → name → analyzing → result → promessa → offer
```

Telas prontas no código mas fora do fluxo: `pitch`, `visao`, `delivery`,
`bonus`. É por isso que as imagens de bônus, o mockup e o segundo vídeo não
aparecem. Para reativar alguma, basta incluir o nome dela no array `FLOW`.
