# Capitulo 01 - Guia Iniciante de Git e GitHub

- [Cap01 - Guia Iniciante](/dicionario-git-iniciante.md)
- [Cap02 - Utilizando Branches](dicionario-git-brach.md)

## Sumário

1. [Primeiro acesso ao Git Bash](#1-primeiro-acesso-ao-git-bash)
2. [Criando o repositório local](#2-criando-o-repositório-local)
3. [Criando o `.gitignore`](#3-criando-o-gitignore)
4. [Primeiro versionamento](#4-primeiro-versionamento)
5. [Criando o repositório no GitHub](#5-criando-o-repositório-no-github)
6. [Conectando o repositório local ao GitHub](#6-conectando-o-repositório-local-ao-github)
7. [Definir a branch principal](#7-definir-a-branch-principal)
8. [Enviar o projeto para o GitHub](#8-enviar-o-projeto-para-o-github)
9. [Fluxo completo do primeiro envio](#9-fluxo-completo-do-primeiro-envio)
10. [Comandos do dia a dia](#10-comandos-do-dia-a-dia)
11. [Receber alterações do GitHub](#11-receber-alterações-do-github)
12. [Comandos úteis para consulta](#12-comandos-úteis-para-consulta)

---

# 1. Primeiro acesso no GitBash

> Execute esta etapa apenas para configurar o Git na máquina.

### Configurar nome

```bash
git config --global user.name "Seu Nome"
```

### Configurar e-mail

```bash
git config --global user.email "seuemail@gmail.com"
```

### Verificar configurações

```bash
git config --global --list
```

**Observação:**
Caso tenha preenchido alguma informação errada, basta executar novamente o comando correspondente com o dado correto.

---

# 2. Criando o repositório local

> Estes comandos devem ser executados dentro da pasta do projeto.

### Acessar a pasta do projeto

```bash
cd /c/caminho/da/pasta/projeto
```

### Inicializar o Git

```bash
git init
```

Esse comando transforma a pasta do projeto em um **repositório Git local**.

### Verificar o estado do repositório

```bash
git status
```

O `git status` mostra informações como:

* branch atual;
* arquivos modificados;
* arquivos que ainda não foram adicionados;
* arquivos preparados para commit;
* commits pendentes.

---

# 3. Criando o `.gitignore`

> O `.gitignore` define arquivos e pastas que o Git deve ignorar.

### Criar o arquivo

```bash
touch .gitignore
```

Depois, abra o `.gitignore` e coloque os arquivos/pastas que não devem ser versionados.

Exemplo:

```gitignore
.env
.exe
output/
.vscode/
```

**Observação:**
O conteúdo do `.gitignore` depende da tecnologia utilizada no projeto.

Por exemplo, projetos Laravel normalmente ignoram arquivos como `.env`, `vendor/` e `node_modules/`.

---

# 5. Criando o repositório no GitHub

Acesse:

https://github.com/

Crie um novo repositório.

Por exemplo:

```text
meu-projeto
```

Como o projeto já possui um repositório Git local, é recomendado criar o repositório do GitHub **vazio**.

Evite marcar inicialmente:

* README;
* .gitignore;
* License.

Após criar o repositório, o GitHub fornecerá uma URL semelhante a:

```text
https://github.com/seu-usuario/meu-projeto.git
```

---


# 6. Conectando o repositório local ao GitHub

### Adicionar o repositório remoto

```bash
git remote add origin https://github.com/seu-usuario/meu-projeto.git
```

`origin` é o nome normalmente utilizado para identificar o repositório remoto principal.

### Verificar a conexão

```bash
git remote -v
```

Deve aparecer algo semelhante a:

```text
origin  https://github.com/seu-usuario/meu-projeto.git (fetch)
origin  https://github.com/seu-usuario/meu-projeto.git (push)
```

---

# 7. Definir a branch principal

```bash
git branch -M main
```

Esse comando renomeia a branch atual para `main`.

---

# 8. Enviar o projeto para o GitHub

```bash
git push -u origin main
```

O comando envia a branch `main` local para o GitHub.

O `-u` estabelece a relação entre:

```text
main local
    ↓
origin/main
```

Depois disso, nos próximos envios, normalmente será suficiente utilizar:

```bash
git push
```

---

# 9. Fluxo completo do primeiro envio

Depois de configurar o Git e criar o projeto no GitHub, o processo pode ser resumido em:

```bash
cd /c/caminho/da/pasta/projeto

git init

touch .gitignore

git add .

git commit -m "Primeiro commit"

git branch -M main

git remote add origin https://github.com/seu-usuario/meu-projeto.git

git remote -v

git push -u origin main
```

---

# 10. Comandos do dia a dia

## Enviar alterações para o GitHub

Sempre que fizer alterações no projeto:

### 1. Verificar alterações

```bash
git status
```

### 2. Adicionar alterações

```bash
git add .
```

### 3. Criar um commit

```bash
git commit -m "Descrição da alteração"
```

### 4. Enviar para o GitHub

```bash
git push
```

### Fluxo resumido

```bash
git status
git add .
git commit -m "Descrição da alteração"
git push
```

---

# 11. Receber alterações do GitHub

Para baixar alterações que estão no GitHub:

```bash
git pull
```

O `git pull` atualiza o repositório local com as alterações existentes no repositório remoto.

---

# 12. Comandos úteis para consulta

### Ver o estado do projeto

```bash
git status
```

### Ver histórico de commits

```bash
git log
```

### Ver histórico resumido

```bash
git log --oneline
```

### Ver os repositórios remotos

```bash
git remote -v
```

### Ver as branches

```bash
git branch
```

### Ver alterações feitas nos arquivos

```bash
git diff
```

---

# Resumo do fluxo

```text
                 PRIMEIRO ENVIO

                Pasta do projeto
                        ↓
                    git init
                        ↓
                   .gitignore
                        ↓
                    git add .
                        ↓
                   git commit
                        ↓
           Criar repositório no GitHub
                        ↓
              git remote add origin
                              ↓
               git branch -M main
                        ↓
              git push -u origin main
                        ↓
                      GitHub


                 DIA A DIA

               Alterar código
                     ↓
                 git status
                     ↓
                  git add .
                     ↓
                 git commit
                     ↓
                  git push
                     ↓
                  GitHub


         RECEBER ALTERAÇÕES

               GitHub
                 ↓
              git pull
                 ↓
            Projeto local
```

