<!DOCTYPE html>
<html>
    <head>
        <meta http-equiv="Content-type" content="text/html; charset=utf-8">
        <title>Markdown</title>
        <style type="text/css" media="screen">
            .markdown {
                position:relative;
                border:10px solid gray;
                width:188px; height:108px;
                border-radius:15px;
                -webkit-font-smoothing:antialiased;
            }
            .markdown:before {
                color:gray;
                font:bold 100px "Gill Sans";
                content:"M";
                position:absolute;
                top:-4px;
                left:12px;
            }
            .markdown .stem {
                border:10px solid gray;
                position:absolute;
                height:30px;
                right:34px;
                top:20px;
            }
            .markdown .arrow {
                width:0;
                height:0;
                position:absolute;
                bottom:0px;
                right:14px;
                border-style:solid;
                border-width:34px 30px 20px 30px;
                border-color:gray transparent transparent transparent;
            }

            .markdown.spec {
                border-color:#ccc;
            }
            .markdown.spec:before {
                color:#ccc;
            }
            .markdown.spec .stem {
                border-color:#ccc;
            }
            .markdown.spec .arrow {
                border-top-color:#ccc;
            }

            .markdown.cutout {
                border-color:black;
            }
            .markdown.cutout:before {
                color:black;
            }
            .markdown.cutout .stem {
                border-color:black;
            }
            .markdown.cutout .arrow {
                border-top-color:black;
            }

            .markdown.solid {
                background-color:black;
                border-color:black;
            }
            .markdown.solid:before {
                color:white;
            }
            .markdown.solid .stem {
                border-color:white;
            }
            .markdown.solid .arrow {
                border-top-color:white;
            }

            .cutout-positioner {
                position:absolute;
                top:8px;
                left:269px;
            }
            
            .solid-positioner {
                position:absolute;
                top:8px;
                left:530px;
            }
        </style>
    </head>
    <body>
        <div class="markdown spec">
            <div class="stem"></div>
            <div class="arrow"></div>
        </div>
        <div class="cutout-positioner">
            <div class="markdown cutout">
                <div class="stem"></div>
                <div class="arrow"></div>
            </div>
        </div>
        <div class="solid-positioner">
            <div class="markdown solid">
                <div class="stem"></div>
                <div class="arrow"></div>
            </div>
        </div>
    </body>
</html>

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default tseslint.config({
  extends: [
    // Remove ...tseslint.configs.recommended and replace with this
    ...tseslint.configs.recommendedTypeChecked,
    // Alternatively, use this for stricter rules
    ...tseslint.configs.strictTypeChecked,
    // Optionally, add this for stylistic rules
    ...tseslint.configs.stylisticTypeChecked,
  ],
  languageOptions: {
    // other options...
    parserOptions: {
      project: ['./tsconfig.node.json', './tsconfig.app.json'],
      tsconfigRootDir: import.meta.dirname,
    },
  },
})
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default tseslint.config({
  plugins: {
    // Add the react-x and react-dom plugins
    'react-x': reactX,
    'react-dom': reactDom,
  },
  rules: {
    // other rules...
    // Enable its recommended typescript rules
    ...reactX.configs['recommended-typescript'].rules,
    ...reactDom.configs.recommended.rules,
  },
})
```
