# ts-template

Template mínimo em TypeScript para projetos Node.js (ESM) focado em produtividade e convenções modernas.

Este repositório fornece uma base simples com configuração pronta para desenvolvimento, build e testes:

- TypeScript com `tsc` (target Node 22+)
- Execução rápida em desenvolvimento com `tsx`
- Alias de compilação com `tsc-alias`
- Testes com `vitest`
- Linter/format via `biome` (configurada nos scripts)
- Suporte a variáveis de ambiente via `dotenv-flow`
- Fluxo de releases com `release-it` e convenção de commits (Commitizen + commitlint)

## Requisitos

- Node.js >= 22.12.0
- Yarn 1

## Instalação

Instale as dependências com Yarn:

```bash
yarn install
```

## Estrutura do projeto

Principais arquivos e pastas:

- `package.json` — scripts e dependências
- `tsconfig.json` — configuração do compilador TypeScript
- `src/` — código fonte (ex.: `src/index.ts`)
- `dist/` — saída de build (gerada)

## Scripts úteis

Os scripts definidos em `package.json`:

- `yarn dev` — executa `src/index.ts` em modo desenvolvimento com `tsx` e `dotenv-flow`.
- `yarn build` — compila TypeScript (`tsc`) e aplica `tsc-alias` para resolver paths.
- `yarn start` — executa a build (`dist/index.js`) com suporte a `dotenv-flow`.
- `yarn run check` — executa `biome check` (lint/static analysis; `yarn check` é o verificador interno do Yarn 1).
- `yarn check:fix` — tenta corrigir problemas automaticamente (`biome check --fix`).
- `yarn test` — roda testes com `vitest` (pasta `src`) e passa quando não há arquivos de teste.
- `yarn test:coverage` — roda testes com cobertura.
- `yarn verify` — roda `check`, `test` e `build` (fluxo de verificação).
- `yarn release` — inicia fluxo de release via `release-it` (configurar antes de usar).

Exemplo rápido (desenvolvimento):

```bash
yarn dev
```

Build e execução em produção local:

```bash
yarn build
yarn start
```

## Variáveis de ambiente

Este template inclui `dotenv-flow` para carregar variáveis de ambiente em `dev` e `start`. Crie arquivos `.env`, `.env.development`, `.env.test` conforme necessário.

## Convenções e contribuições

- Commits: a base já traz `commitizen` e `cz-conventional-changelog` para gerar mensagens de commit no formato Conventional Commits.
- `commitlint` e `husky` são usados para reforçar políticas de commit (hooks) — é recomendável ativar `husky` localmente (`yarn prepare` já está presente no `package.json`).

Se quiser contribuir:

1. Fork e branch feature/bugfix.
2. Siga o padrão de commits convencionais (p.ex. `git cz` para criar commits).
3. Rode `yarn run check` e `yarn test` antes de abrir PR.

## Publicação / Releases

O projeto inclui `release-it` para automatizar releases. Configure `release-it` (token de publicação e parâmetros) antes de usar `yarn release`.

## Exemplos e ponto de partida

O arquivo `src/index.ts` contém um exemplo mínimo:

```ts
// exemplo rápido
console.log('Hello, world!')
```

Use este repositório como ponto de partida para bibliotecas ou microserviços pequenos. Para projetos maiores, adicione ferramentas de CI, linters/formatters mais estritos, e uma suíte de testes mais completa.

## Licença

MIT — consulte `package.json`.
