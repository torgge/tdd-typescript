# Important things

## Charpter 01

Initialize git in your project

```bash
git init -b main
```

Initialize the nodejs project

```bash
npm init -y
```

Use git commit conventional patterns like link:
[conventionalcommits](https://www.conventionalcommits.org/en/v1.0.0/)

Install in your project an git commit linter:
[git-commit-msg-linter](https://www.npmjs.com/package/git-commit-msg-linter)

```bash
    npm i -D git-commit-msg-linter
```

#### Create a .gitignore file and put in:

```bash
    echo 'node_modules' >> .gitignore
```

#### ..and commit this

```bash
    git add .
    git c "chore: add commit linter"
```

#### Than... add the Typescript and @types/node to project

```bash
    npm i -D typescript @types/node
```

#### Create and edit the tsconfig.json file

```bash
    echo '{
    "compilerOptions": {
        "outDir": "./dist",
        "module": "commonjs",
        "target": "es2020",
        "esModuleInterop": true,
        "allowJs": true
    }
}' >> tsconfig.json
```

### Rules to standarise the development: [standardjs](https://standardjs.com)

When use typescript we need to install eslint to works with standardjs: [eslint-config-standard-with-typescript](https://github.com/standard/eslint-config-standard-with-typescript)

```bash
npm install --save-dev eslint@7 eslint-plugin-promise@4 eslint-plugin-import@2 eslint-plugin-node@11 @typescript-eslint/eslint-plugin@4 eslint-config-standard-with-typescript
```

#### Configure the ESLint
```bash
echo '{
    "extends": "standard-with-typescript",
    "parserOptions": {
        "project": "./tsconfig.json"
    }
}' >> .eslintrc.json
```


#### Install package husky to hook scripts [Husky](https://www.npmjs.com/package/husky)
```bash
    npm i -D husky
```
#### ..and lint-staged
```bash
    npm i -D lint-staged
```
#### we need to configure Lint Staged creating .lintstagedrc.json file
```bash
echo '{
    "*.ts": [
        "eslint 'src/**' --fix",
        "git add"
    ]
}' >> .lintstagedrc.json
```
#### we need to configure Husky creating .huskyrc.json file
```bash
echo '{
    "hooks": {
        "pre-commit": "lint-staged"
    }
}' >> .huskyrc.json
```
### Install Jest test package
```bash
    npm i -D jest @types/jest ts-jest
```
#### initialize the jest
```bash
    jest --init
```