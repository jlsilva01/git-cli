# Git CLI

Para criar um repositório no Github através do Git CLI, basta seguir os passos abaixo:

```bash
gh auth login
```
? What account do you want to log into? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: FA33-F347
Press Enter to open github.com in your browser...
✓ Authentication complete.
- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as jlsilva01
! You were already logged in to this account

```bash
gh repo create
```
```
? What would you like to do? Create a new repository on GitHub from scratch
? Repository name repo-teste

? Repository name repo-teste
? Description
? Visibility Public
? Would you like to add a README file? Yes
? Would you like to add a .gitignore? No
? This will create "repo-teste" as a public repository on GitHub. Continue? Yes
? Clone the new repository locally? No
```

Depois do repositório remoto criado, você pode utilzá-lo basicamente de duas formas:

1. Clonando o repositório remoto recém criado e atualizá-lo a partir do zero.
2. Adicionando o repositório remoto a um projeto/paste local já existente.

## Clonando o repositório remoto recém criado e atualizá-lo a partir do zero.

1. Copiar a URL do repositório remoto.

![image](https://github.com/user-attachments/assets/043f27a2-2fc3-4597-88b2-69f71e3a2e6a)

2. Executar o comando de `git clone` a partir da URL copiada.

```bash
git clone https://github.com/jlsilva01/repo-teste.git
```
```
Cloning into 'repo-teste'...
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (3/3), done.
```
3. Entrar no repositório local e validar o status da branch atual.

```bash
cd repo-teste
git status
```
```
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
```

## Adicionando o repositório remoto a um projeto/paste local já existente.

1. Inicializar a pasta local usando os comandos abaixo (caso não tenha sido inicializado ainda).

```bash
git init
git add .
git commit -m "build: setup inicial do projeto"
git branch -M main
```
2. Copiar a URL do repositório remoto.

![image](https://github.com/user-attachments/assets/043f27a2-2fc3-4597-88b2-69f71e3a2e6a)

3. Adicionar o repositório remoto a pasta local já inicializada.

```bash
git remote add origin https://github.com/jlsilva01/teste.git
```

4. Efetuar o upload dos arquivos locais para o repositório remoto

```bash
git push origin main
```
