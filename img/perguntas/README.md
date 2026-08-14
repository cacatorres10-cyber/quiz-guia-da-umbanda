# img/perguntas/

Imagens que aparecem no topo de cada pergunta do quiz.

Hoje elas ainda vêm do site de origem. Para trocar qualquer uma por um arquivo
seu, suba o arquivo aqui e acrescente a linha da chave em `IMAGENS`, no
`QUIZ_CONFIG` (topo do `index.html`):

```js
IMAGENS: {
  iniciante:  "img/iniciante.jpg",
  umbandista: "img/umbandista.jpg",
  q_entidades: "img/perguntas/entidades.jpg"    // <- a linha nova
},
```

Só isso. O que não estiver listado continua vindo de `ASSET_BASE`.

## Chaves das perguntas que estão no fluxo

| Chave | Pergunta |
|---|---|
| `q_entidades` | "Você conhece os Orixás e as entidades que trabalham nos terreiros?" |
| `q_pontos` | "O que são os pontos riscados na Umbanda?" |
| `q_rituais` | "Como você se sente em relação aos rituais básicos?" |
| `q_altar` | "Você sabe montar um altar (congá) simples?" |
| `q_elementos` | "Você entende como os Orixás se relacionam com os elementos?" |

A primeira pergunta ("Qual é o principal fundamento?") não tem imagem no topo:
ela usa três imagens nas próprias opções, com as chaves `orixas`,
`pretovelhos` e `caridade`.

As demais chaves (`q_dificuldades`, `q_app`, `q_orixas`, `sim`, `talvez`,
`incerteza`, `b1` a `b4`, `b6mais`, `mockup`) são de telas que estão fora do
fluxo hoje. A lista completa está em `MIDIA.md`.

## Formato

A imagem da pergunta aparece com no máximo 240 px de largura e mantém a
proporção do arquivo — não é recortada, então não precisa ser quadrada.
Largura de 480 a 720 px e menos de 100 KB já bastam.

Diferente daqui, os cards de "Iniciante" e "Umbandista" **recortam em 1:1**,
então para eles a imagem precisa ser quadrada.
