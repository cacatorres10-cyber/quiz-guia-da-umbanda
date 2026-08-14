# img/

Pasta para as imagens hospedadas no próprio projeto.

## Foto do rodapé

Nome esperado pelo código: **`helena.png`**

Foto de Mãe Helena de Oxóssi que aparece no rodapé. Ideal quadrada (ex.: 200×200),
pois é exibida em círculo de 56 px. Para usar outro nome, ajuste `FOTO_AUTORA`
no `QUIZ_CONFIG`.

Enquanto o arquivo não existir, entra um avatar cinza neutro no lugar.

## Imagens do quiz

Hoje todas vêm de `quizsarava.lovable.app`. Para hospedar aqui, baixe os
arquivos listados em `MIDIA.md`, coloque nesta pasta mantendo os nomes, e troque
no `QUIZ_CONFIG`:

```js
ASSET_BASE: "img/",
```
