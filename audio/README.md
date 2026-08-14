# audio/

Música de fundo do quiz.

`ori-background.mp3` — **já está no lugar** e tocando. 4min46s, em loop, 96 kbps,
3,3 MB. Detalhes do tratamento aplicado (corte do silêncio inicial, ganho e
fades para o loop) estão em `MIDIA.md`, na raiz do projeto.

## Para trocar a faixa

Substitua o arquivo mantendo o nome, ou ajuste `MUSICA` no `QUIZ_CONFIG`, no
topo do `index.html`.

Recomendações:

- MP3, 96–128 kbps já basta (é música de fundo, toca baixo).
- Abaixo de ~3 MB para não pesar no celular.
- Sem silêncio no começo nem corte seco no fim, senão a emenda do loop estala.
- Use uma faixa que você tenha direito de usar.

O volume fica em `MUSICA_VOLUME` (0 a 1), também no `QUIZ_CONFIG`.

Se o arquivo faltar ou o formato não for suportado, o botão de música some
sozinho da página, em vez de virar um controle que não faz nada.
