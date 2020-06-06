# vue-shop
## 3.x版本脚手架
 npm install -g @vue/cli
 vue create my-project
 =>Manully select features
 =>选中需要安装的功能(空格选中)=>
=>是否使用历史模式n
=>ESLint + Standard config (标准模式的ESLint)
=>Lint on save
=>In dedicated config files (方便维护)
=>是否保存模板(n/y)
=>use NPM
=>npm run serve 
### vscode代码格式化自动添加双引号及分号问题
前端 vue 项目根目录下添加 .prettierrc.json 文件, 配置如下就好了
singleQuote: true 使用单引号
semi: false 在语句末尾不打印分号
```
{
    "singleQuote": true,
    "semi": false
}
```


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
