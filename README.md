# Dondza aqui

App de preparação para exames de admissão. Idealizado por Assane Filipe.

## Estrutura
- `www/index.html`: o app (interface, planos, desbloqueio por código).
- `www/data/index.json`: lista de matérias e exames, e número da versão.
- `www/data/lessons/*.json`: uma matéria por ficheiro.
- `www/data/exams/ANO.json`: um exame por ficheiro.
- `.github/workflows/build-apk.yml`: gera o APK automaticamente no GitHub.

## Gerar o APK (sem instalar nada no PC)
1. Crie um repositório no GitHub e envie estes ficheiros (branch `main`).
2. Abra o separador **Actions**, execute **Build APK** e, no fim, descarregue `dondza-aqui-apk` (contém `app-debug.apk`).
3. Para Play Store é preciso um APK/AAB assinado (release); peça ajuda quando chegar lá.

## Adicionar ou actualizar uma matéria
1. Copie `lessons/classes-de-palavras.json`, mude `id`, `l` (0 Básico, 1 Intermédio, 2 Avançado), `c`, `t`, `b` (resumo), `s` (secções com `h` e `p`) e `x` (exercícios: `[pergunta, [opções], índice da correcta começando em 0]`).
2. Acrescente o nome do ficheiro (sem .json) em `lessons` no `data/index.json` e aumente `version`.

## Adicionar um exame
1. Crie `exams/2010.json` com `r` (resumo do texto) e `q`: `[pergunta, [opções], índice da correcta, categoria]`. Categorias: `Texto`, `Gramática`, `Literatura`.
2. No `index.json`, tire `"soon": true` do ano e aumente `version`.

## Actualizar sem refazer o APK
Publique a pasta `www` com GitHub Pages e ponha o endereço em `REMOTE` no início do script de `www/index.html` (ex.: `const REMOTE='https://SEU-USER.github.io/dondza-aqui/';`). Depois, em Configurações, o botão **Actualizar conteúdos** descarrega as novidades. Sem ligação, o app usa a última cópia guardada.

## Códigos de desbloqueio
Gere com o `desbloqueador-dondza.html` (mantenha-o fora do repositório público). O `SALT` tem de ser igual nos dois ficheiros; mude-o antes de publicar.
