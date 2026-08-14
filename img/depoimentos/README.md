# img/depoimentos/

Capturas das conversas que aparecem no carrossel de depoimentos, logo abaixo do
vídeo de prévia do app, e também no resultado e na oferta.

| Arquivo | Conversa |
|---|---|
| `1.jpg` | Instagram — Colorindo com Jesus (@ceucomcores) |
| `2.jpg` | Instagram — "Esse aplicativo é surreal!" + bônus no e-mail |
| `3.jpg` | WhatsApp — "Chegou… os bônus estão juntos" |
| `4.jpg` | Instagram — Débora (conversa de pré-venda) |

A ordem de exibição é a do array `DEPOIMENTOS`, no `QUIZ_CONFIG`. Para trocar a
ordem, reordene lá; para trocar uma imagem, substitua o arquivo mantendo o nome.

## Para acrescentar um depoimento

Suba a imagem aqui e adicione uma entrada em `DEPOIMENTOS`:

```js
{ print:"img/depoimentos/5.jpg", texto:"texto de reserva", nome:"Quem enviou", local:"Instagram" }
```

O `texto` é opcional e só aparece se a imagem não carregar. Use quando a
conversa tiver um elogio de verdade; sem isso, deixe só o `print`.

Recomendações: JPEG, largura de 480 a 720 px, abaixo de ~100 KB cada. Vale
cortar a barra de status do celular para o print ficar mais limpo.

Depoimento precisa ser real e autorizado por quem escreveu — exigência do
Código de Defesa do Consumidor e do CONAR.
