# Starter-Kit [ React + TypeScript + Vite ]

This template provides a minimal setup to get React working with Vite, featuring HMR and basic ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react/README.md) — uses [Babel](https://babeljs.io/) for Fast Refresh.
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react-swc) — uses [SWC](https://swc.rs/) for Fast Refresh.

## Expanding the ESLint Configuration

If you're building a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
// eslint.config.js
export default tseslint.config({
  extends: [
    // Use the recommended type-aware rules
    ...tseslint.configs.recommendedTypeChecked,

    // Optionally use this for stricter rules
    // ...tseslint.configs.strictTypeChecked,

    // Add this for stylistic rules (optional)
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // Other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
});
```

### Optional: Add React-Specific ESLint Plugins

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific linting:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x';
import reactDom from 'eslint-plugin-react-dom';

export default tseslint.config({
  plugins: {
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // Enable recommended TypeScript rules from the plugins
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
});
```
