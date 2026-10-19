# Giro Premiado

Jogo de roda de prêmios para celular: gire a roda, chute letras e descubra a frase escondida.

**Link do jogo:** https://luciolma.github.io/giro-premiado/

## Modos

- **Jogar sozinho:** 3 rodadas com 5 chances em cada. Letra errada, *Passa a Vez* e resposta errada gastam uma chance. É o único modo que vale para o ranking.
- **Jogar em 3 no mesmo celular:** modo festa, com a vez passando entre os jogadores. Não conta no ranking.

## Ranking

O ranking usa o mesmo projeto Firebase da Forca (`forca-6075d`), numa coleção separada chamada `giro`. O login anônimo e o domínio `luciolma.github.io` já estão configurados lá.

- **Da semana:** a melhor partida de cada aparelho desde segunda-feira.
- **Recordes:** a melhor partida de cada aparelho de todos os tempos.

### Único passo no Firebase: atualizar as regras

1. Acesse **console.firebase.google.com** e abra o projeto **forca**.
2. No menu da esquerda, abra **Firestore Database** e depois a aba **Regras**.
3. Apague tudo, cole o conteúdo do arquivo `firestore.rules` deste repositório e clique em **Publicar**.

O arquivo já inclui as regras da Forca sem nenhuma mudança, então a Forca continua funcionando igual.

Enquanto as regras não forem publicadas, o jogo funciona normalmente, mas o ranking mostra "As regras do Firestore ainda não incluem o Giro Premiado" e os pontos ficam só no aparelho.

## Arquivos

| Arquivo | Para que serve |
|---|---|
| `index.html` | O jogo |
| `firebase-config.js` | Chave do projeto Firebase (pode ficar pública) |
| `firestore.rules` | Regras de segurança do ranking da Forca e do Giro Premiado |

## Bom saber

- **Frases novas:** ficam na lista `PUZZLES` no começo do `<script>` do `index.html`, no formato `["Categoria","FRASE EM MAIÚSCULAS"]`.
- **Trapaça:** como o jogo roda no navegador, alguém que entenda de programação conseguiria inventar uma pontuação. As regras limitam o valor máximo a R$ 500.000 por partida. Se aparecer algo estranho, apague a linha da pessoa em Firestore Database › `giro`.
