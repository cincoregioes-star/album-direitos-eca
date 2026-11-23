# Direitos da Criança e do Adolescente (ECA): um direito por figurinha — Álbum Digital

Álbum digital pedagógico sobre o Estatuto da Criança e do Adolescente (Lei 8.069/1990). Cada uma das 36 figurinhas apresenta **um direito**, o **artigo exato** do ECA e o **texto literal da lei**, conferido com o texto compilado do Planalto em 23/11/2026 (já com as alterações das Leis 15.240/2025 e 15.512/2026). Usa a mesma estrutura do álbum **Combate ao Bullying e ao Cyberbullying**, com conteúdo novo.

A escola que aparece no álbum, **Escola Municipal Horizonte Azul**, é **fictícia**. Para usar em uma escola real, troque o nome em `album-data.js` e em `index.html`, e substitua o arquivo `logo-escola.png`.

## Créditos
**Idealização, projeto digital, desenvolvimento do aplicativo e arquitetura da plataforma:** Prof. Carlos André Tavares de Lima
Professor de Geografia • Administração Escolar • Criador de Projetos Digitais Educativos
cincoregioes@gmail.com

## O que tem no álbum
- **36 figurinhas em 6 páginas temáticas**, com 4 raras, 10 especiais e 22 comuns:
  1. Proteção integral (arts. 1º a 5º)
  2. Vida e saúde (arts. 7º a 14)
  3. Liberdade, respeito e dignidade (arts. 15 a 18-A)
  4. Convivência familiar e comunitária (arts. 4º, § 2º, 19 a 39)
  5. Educação, cultura, esporte, lazer e trabalho protegido (arts. 53 a 60 e CF, art. 7º, XXXIII)
  6. Rede de proteção (arts. 13, 70, 86, 98, 131 e 141)
- **Ficha de cada figurinha** com mensagem central, por que isso importa, atitude, **direito relacionado (texto literal do ECA)** e uma pergunta para conversar.
- **5 simulados de 10 questões**, todos com gabarito tirado do texto da lei. Quem acerta 10 ganha 1 pacote; com qualquer erro ganha 1 figurinha. As alternativas corretas são redistribuídas automaticamente.
- **Desafio Final** (10 questões) e **Missão Resgate** (5 situações do dia a dia).
- **Pesquisa 1** (diagnóstico inicial) e **Pesquisa 2** (avaliação final), anônimas, com indicadores de antes e depois: conhecer o ECA, perceber violações, saber a quem recorrer, respeitar os colegas e conhecer a rede de proteção.
- **Game match-3** com 5 fases pedagógicas, que revela as figurinhas do álbum e dá prêmios ao álbum.
- **Painel dos professores** (`professor.html`) com login por nome de usuário, impacto antes e depois, ciclos, concluintes e exportação em CSV.
- **PWA** offline e **APK Android**.

## Fidelidade à lei
- O texto entre aspas no campo `lei` de cada figurinha é **transcrição exata** do ECA; o restante da ficha é explicação em linguagem para estudantes.
- **Art. 60 x Constituição:** o ECA ainda diz "quatorze anos", mas a Constituição (art. 7º, XXXIII, EC 20/1998) proíbe qualquer trabalho antes dos 16, salvo como aprendiz a partir dos 14. A figurinha 30 traz os dois textos e ensina a regra atual.
- **ECA Digital** (Lei 15.211/2025) é uma lei própria, não um artigo do ECA, e não foi incluída nas figurinhas.
- Se a lei mudar, atualize o campo `lei` em `album-data.js` conferindo em https://www.planalto.gov.br/ccivil_03/leis/l8069.htm

## Onde editar o conteúdo
Todo o conteúdo pedagógico (figurinhas, páginas, simulados, desafio, missão, pesquisas, micro-aulas e fases do game) está em **`album-data.js`**.

## Figurinhas
As 36 figurinhas da pasta `figurinhas/` são **artes provisórias** tipográficas (número, artigo e título), no formato vertical 9:16 (768×1376 px).
Os prompts para gerar as imagens definitivas estão em **`docs/PROMPTS_FIGURINHAS.md`**. Para trocar uma imagem, salve a nova com o mesmo nome (`01.webp` … `36.webp`). Não é preciso mudar nenhum código.

## Modo livre (padrão) e Supabase
O álbum vem em **modo livre**: tudo funciona sem servidor (álbum, pacotes, simulados, desafio, missões, game e as duas pesquisas) e o progresso de cada aluno fica salvo no próprio aparelho/navegador.

- **Pesquisa 1** (diagnóstico inicial) pode ser respondida a qualquer momento.
- **Pesquisa 2** (avaliação final) é liberada automaticamente quando o aluno **completa o álbum** (36 figurinhas coladas). Ao enviá-la, o aluno vê o seu "antes e depois".
- **Identificação do aluno** fica bloqueada com o aviso de que será habilitada após a definição do projeto.

### Para ter o painel dos professores (opcional)
1. Crie um projeto no Supabase e rode `supabase/DIREITOS_ECA_SUPABASE.sql` no SQL Editor.
2. Crie o login de cada professor com o comando que está no fim do arquivo.
3. Em `supabase-config.js`, preencha `url` e a chave pública (`publishableKey` e `anonKey`) e mude `enabled` para `true`. Em `game/game-v13.js`, preencha a mesma `url` e `key`.

Com o Supabase ligado, o professor também pode liberar a Pesquisa 2 para a turma inteira pelo painel.

## Publicar no GitHub Pages
Em **Settings → Pages**, escolha *Deploy from a branch*, depois a branch `main` e a pasta `/ (root)`.
Endereço: `https://cincoregioes-star.github.io/album-direitos-eca/`. O QR Code está em `qrcode/`.

## App para usar sem internet
- **Android:** a cada atualização na branch `main`, o GitHub gera o app (`direitos-eca.apk`) e publica em **Releases**. O botão **📲 Baixar o app** do site aponta para
  `https://github.com/cincoregioes-star/album-direitos-eca/releases/latest/download/direitos-eca.apk`.
  O app já traz todas as figurinhas, áudios e o game: funciona totalmente offline. Ele é instalado como um app separado do álbum de bullying (`br.com.direitoseca.album`).
- **iPhone/iPad e computador:** o site é um app instalável (PWA). Depois de aberto uma vez com internet, funciona offline.
- A chave de assinatura do app está em `android-wrapper/combate-bullying.keystore` (senha no `app/build.gradle`). Mantenha esse arquivo: é ele que permite instalar versões novas por cima das antigas.

## Leis citadas no conteúdo
- ECA, Lei 8.069/1990 (texto compilado, com alterações até a Lei 15.512/2026)
- Constituição Federal, art. 7º, XXXIII (EC 20/1998): idade mínima para o trabalho
- Lei 13.010/2014 (Lei Menino Bernardo), Lei 13.257/2016 (Marco Legal da Primeira Infância), Lei 12.010/2009, Lei 13.845/2019 e Lei 15.240/2025, citadas como origem da redação dos artigos
