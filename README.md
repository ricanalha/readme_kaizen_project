# 🏷 Canhoto – Front-end Template

Bem-vindo ao template de front-end **Canhoto**!  

Este projeto serve como base para aplicações React modernas utilizando **TypeScript**, **Vite**, **TailwindCSS** e boas práticas de desenvolvimento. Ele é estruturado para ser reutilizável pelo time, garantindo consistência de código, linting, formatação e tipagem.

---

## 📦 Tecnologias e Dependências Principais

- **React 19** – Biblioteca principal de UI.
- **TypeScript** – Tipagem estática para maior segurança e produtividade.
- **Vite** – Bundler rápido e moderno para desenvolvimento front-end.
- **TailwindCSS 4** – Framework CSS utilitário para estilização.
- **clsx** – Para composição condicional de classes CSS.
- **class-variance-authority** – Para gerenciar variantes de componentes (como botões).
- **Radix UI Slot** – Para composição de componentes com `asChild`.
- **Lucide React** – Biblioteca de ícones.
- **tailwind-merge** – Para mesclar classes Tailwind evitando duplicação.
- **tw-animate-css** – Para animações utilitárias com Tailwind.

---

## 🛠 Ferramentas de Desenvolvimento

- **ESLint** – Linting e boas práticas de JavaScript/TypeScript.
- **Prettier** – Formatação de código consistente.
- **Husky + lint-staged** – Hooks para garantir commits limpos e padronizados.

### Plugins ESLint adicionais

| Plugin | Função |
|--------|-------|
| `eslint-plugin-import` | Ordenação e organização de imports. |
| `eslint-plugin-unused-imports` | Limpeza de imports e variáveis não utilizadas. |
| `eslint-plugin-jsx-a11y` | Acessibilidade em JSX. |
| `eslint-plugin-sonarjs` | Complexidade cognitiva e duplicação de código. |
| `eslint-plugin-promise` | Boas práticas com Promises. |
| `eslint-plugin-unicorn` | Boas práticas gerais de JS/TS. |
| `eslint-plugin-perfectionist` | Organização de imports e padrões de código. |
| `eslint-plugin-react-refresh` | Suporte a Fast Refresh no React. |

---

## ⚙️ Configurações do Projeto

### TypeScript

O projeto possui três arquivos `tsconfig`:

- **tsconfig.app.json** – Configurações principais da aplicação.
- **tsconfig.node.json** – Configurações para arquivos de Node (ex: `vite.config.ts`).
- **tsconfig.json** – Arquivo de referência central.

Principais configurações:

- `strict: true` – Garantia de tipagem segura.
- `noUnusedLocals` e `noUnusedParameters` – Evita código morto.
- `paths` e `baseUrl` configurados para `@/*` → `src/*` (imports absolutos).
- JSX configurado como `react-jsx`.

---

### Linting e Formatação

- **ESLint** e **Prettier** configurados para manter consistência de código.
- `.eslintrc.json` define regras básicas e warnings para variáveis não utilizadas.
- `eslint.config.json` inclui regras avançadas:
  - Ordenação de imports
  - Limpeza de imports e variáveis não utilizadas
  - Boas práticas de Promises
  - Complexidade de funções
  - Acessibilidade JSX
  - Convenções de nomes de arquivos
- `.prettierrc` define estilo de código:
  ```json
  {
    "semi": true,
    "singleQuote": true,
    "trailingComma": "all",
    "printWidth": 100,
    "tabWidth": 2,
    "endOfLine": "lf"
  }

### Git

- **.gitattributes** força o **end-of-line** como **LF** para consistência entre sistemas operacionais.


## 🚀 Scripts Disponíveis

| Script | Descrição |
|--------|-------|
| `npm run dev` | Inicia o servidor de desenvolvimento Vite. |
| `npm run build` | Compila a aplicação para produção. |
| `npm run preview` | Roda uma versão de preview do build. |
| `npm run lint` | Executa o ESLint para verificar problemas. |
| `npm run lint:fix` | Executa ESLint e corrige problemas automaticamente. |
| `npm run format` | Formata todo o código com Prettier. |
| `npm run prepare` | Inicializa hooks do Husky. |

### Lint-staged

Antes de qualquer commit, arquivos selecionados são automaticamente verificados:

    ```json
    {
        "*{js,jsx,ts,tsx}": ["npm run format", "npm run lint:fix"],
        "*{css,md,json}": ["npm run format"]
    }

## 🖌️ Convenções de Código

- **Imports absolutos**  
  Use `@/` para importar arquivos dentro de `src/`.

- **Componentes**  
  - Funções escritas com `React.FC` ou `function`.  
  - Variantes de componentes (como botões) são gerenciadas via `class-variance-authority`.

- **TailwindCSS**  
  - Evite duplicar classes.  
  - Use `tailwind-merge` para combinar classes dinamicamente.

- **React Fast Refresh**  
  - Cada arquivo deve **exportar apenas componentes React**.  
  - Constantes auxiliares devem ficar em arquivos separados.

- **Acessibilidade**  
  - Sempre use `alt` em imagens.  
  - Evite `<a>` sem `href` válido.
