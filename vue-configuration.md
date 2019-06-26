## Enable API through proxy vue.config.js:

```
let cookie = '...'
module.exports = {
    devServer: {
        proxy: {
            '/api': {
                target: 'http://<machinename>.local:<port>',
                onProxyReq: function(proxyReq, req, res){
                    proxyReq.setHeader('Cookie', cookie);
                }
            }
        }
    }
}
```

# LINT

https://alligator.io/vuejs/vue-eslint-plugin/

```
$ vue add @vue/eslint
$ vue add @vue/cli-plugin-eslint
```

## Lint Rules

https://github.com/vuejs/eslint-plugin-vue/tree/master/docs/rules

## ./.eslintrc.js

```
module.exports = {
  root: true,
  env: {
    node: true
  },
  'extends': [
    'plugin:vue/recommended',
    'eslint:recommended'
  ],
  rules: {
    'no-console': 'off',
    'no-debugger': 'off',
    "vue/max-attributes-per-line": 'off'
  },
  parserOptions: {
    parser: 'babel-eslint'
  }
}
```

## access to PACKAGE_JSON ./vue.config.js

```
module.exports = {
    ...,
    configureWebpack: {
        plugins: [
          new webpack.DefinePlugin({
            'process.env': {
              PACKAGE_JSON: '"' + escape(JSON.stringify(require('./package.json'))) + '"'
            }
          })
        ]
    },

    lintOnSave: true
}
