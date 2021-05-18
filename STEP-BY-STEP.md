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
