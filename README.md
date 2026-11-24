# Simulado PCA-10

Simulado não oficial da certificação PCA-10 da ABAC: 50 questões sorteadas a cada tentativa, 120 minutos, nota ponderada por módulo (aprovação com 70% e nenhum módulo zerado), gabarito comentado e treino dos erros.

Site: https://alyssondbatista.github.io/PCA10/ (GitHub Pages)

Também publicado em https://simuladopca10.alyssondbatista.workers.dev/ (Cloudflare Workers)

## Estrutura

- `docs/index.html`: o site inteiro (HTML, CSS, JavaScript e o banco de questões no array `Q`).
- `wrangler.jsonc`: configuração do Cloudflare Worker que serve a pasta `docs/`.

## Publicação

Cada commit no branch `main` publica o site em dois lugares:

- GitHub Pages, a partir da pasta `docs/` (Settings → Pages → Deploy from a branch → `main` / `/docs`).
- Cloudflare Workers Builds (`npx wrangler deploy`), que serve a mesma pasta `docs/` com os cabeçalhos de `docs/_headers`.

## Formato das questões

Cada item do array `Q` é `[módulo, enunciado, [correta, errada, errada, errada], explicação, fonte]`, com módulo de 0 a 3:

0. Objetivos e Legislação
1. Funcionamento e Processos
2. Cálculos Financeiros
3. Ética e Melhores Práticas

A tela embaralha as alternativas. O id de cada questão é calculado a partir do enunciado, então mudar o enunciado faz a questão sair da lista de erros salva no navegador dos alunos.

## Revisão mensal

Uma tarefa agendada confere todo mês o edital e as normas (Lei 11.795/2008, Res. BCB 285/2023, Circular BCB 3.978/2020, Lei 9.613/1998, CDC, LGPD e regras do FGTS) e só altera o conteúdo quando há mudança real.
