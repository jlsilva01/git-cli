# Github CLI

Para criar um repositório no Github através do Github CLI, basta seguir os passos abaixo:

```bash
gh auth login
```
<table>
  <tr>
    <td>
? What account do you want to log into? GitHub.com<br>
? What is your preferred protocol for Git operations on this host? HTTPS<br>
? Authenticate Git with your GitHub credentials? Yes<br>
? How would you like to authenticate GitHub CLI? Login with a web browser<br>
<br>
! First copy your one-time code: FA33-F347<br>
Press Enter to open github.com in your browser...<br>
✓ Authentication complete.<br>
- gh config set -h github.com git_protocol https<br>
✓ Configured git protocol<br>
✓ Logged in as jlsilva01<br>
! You were already logged in to this account<br>
    </td>
  </tr>
</table>

```bash
gh repo create
```
<table>
  <tr>
    <td>
? What would you like to do? Create a new repository on GitHub from scratch<br>
? Repository name repo-teste<br>
<br>
? Repository name repo-teste<br>
? Description<br>
? Visibility Public<br>
? Would you like to add a README file? Yes<br>
? Would you like to add a .gitignore? No<br>
? This will create "repo-teste" as a public repository on GitHub. Continue? Yes<br>
? Clone the new repository locally? No<br>
    </td>
  </tr>
</table>

Depois do repositório remoto criado, você pode utilzá-lo basicamente de duas formas:

1. Clonando o repositório remoto recém criado e atualizá-lo a partir do zero.
2. Adicionando o repositório remoto a um projeto/paste local já existente.

## 1. Clonando o repositório remoto recém criado e atualizá-lo a partir do zero.

1.1. Copiar a URL do repositório remoto.

![image](https://github.com/user-attachments/assets/043f27a2-2fc3-4597-88b2-69f71e3a2e6a)

1.2. Executar o comando de `git clone` a partir da URL copiada.

```bash
git clone https://github.com/jlsilva01/repo-teste.git
```
<table>
  <tr>
    <td>
Cloning into 'repo-teste'...<br>
remote: Enumerating objects: 3, done.<br>
remote: Counting objects: 100% (3/3), done.<br>
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)<br>
Receiving objects: 100% (3/3), done.<br>
    </td>
  </tr>
</table>

1.3. Entrar no repositório local e validar o status da branch atual.

```bash
cd repo-teste
git status
```
<table>
  <tr>
    <td>
On branch main<br>
Your branch is up to date with 'origin/main'.<br>
<br>
nothing to commit, working tree clean<br>
    </td>
  </tr>
</table>

## 2. Adicionando o repositório remoto a um projeto/paste local já existente.

2.1. Inicializar a pasta local usando os comandos abaixo (caso não tenha sido inicializado ainda).

```bash
git init
git add .
git commit -m "build: setup inicial do projeto"
git branch -M main
```
2.2. Copiar a URL do repositório remoto.

![image](https://github.com/user-attachments/assets/043f27a2-2fc3-4597-88b2-69f71e3a2e6a)

2.3. Adicionar o repositório remoto a pasta local já inicializada.

```bash
git remote add origin https://github.com/jlsilva01/teste.git
```

2.4. Efetuar o upload dos arquivos locais para o repositório remoto

```bash
git push origin main
```
