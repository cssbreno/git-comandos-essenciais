<div align="center">
  <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/d48893bd-0757-481c-8d7e-ba3e163feae7" width="100%" alt="Banner principal do guia de Git">
</div>
<br>
<br>
<br>

<div align="center" style="margin-top: -20px;">
  <img src="https://user-images.githubusercontent.com/74038190/212281775-b468df30-4edc-4bf8-a4ee-f52e1aaddc86.gif" width="100" />
  <br>
  <br>
  <br>

  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&duration=3000&pause=1000&color=FFD700&center=true&vCenter=true&width=900&lines=Dominando+o+Git:+Seu+Guia+Essencial+Multilingue" alt="Typing SVG">
  </a>
</div>

---

# Índice / Table of Contents / Índice

- [🇧🇷 Português](#-português)
  - [1. Primeiras configurações](#1-primeiras-configurações)
  - [2. Agora, vamos criar / clonar repositórios](#2-agora-vamos-criar--clonar-repositórios)
  - [3. Ver o status e adicionar arquivos](#3-ver-o-status-e-adicionar-arquivos)
  - [4. Salvar (commitar) suas alterações](#4-salvar-commitar-suas-alterações)
  - [5. Histórico dos seus commits](#5-histórico-dos-seus-commits)
  - [6. Vamo entender as branches?](#6-vamo-entender-as-branches)
  - [7. Hora de mandar pro repositório remoto](#7-hora-de-mandar-pro-repositório-remoto)
  - [8. Precisa reverter alguma cagada?](#8-precisa-reverter-alguma-cagada)
  - [9. BÔNUS](#9-bônus)
  - [Gostou do conteúdo?](#gostou-do-conteúdo)

- [🇺🇸 English](#-english)
- [🇪🇸 Español](#-español)

---

## 🇧🇷 Português

### 1. Primeiras configurações

```bash
# Para definir seu nome de usuário
git config --global user.name "seu nome"

# Para definir seu e-mail:
git config --global user.email "seu.email@examplo.com"
````

> ⚠️ **ATENÇÃO:** O Git é case sensitive. Se liga na hora de usar maiúsculo e minúsculo!

---

### 2. Agora, vamos criar / clonar repositórios

#### O que é um repositório?

**Repositório** é um local — seja na sua máquina ou online — usado para centralizar arquivos, dados e recursos de um projeto, facilitando o gerenciamento.
🗃️ É tipo um cofre digital: nele você guarda seus projetos, acompanha o histórico de alterações, vê quem modificou o quê, inclui a documentação do código, arquivos importantes e até o README.md, que apresenta seu projeto pra galera.

#### Repositório remoto e local são a mesma coisa?

Boa pergunta! Bora destrinchar isso:

* 🖥️ O repositório **local** é o que tá na sua máquina.
  Sabe quando você cria uma pasta no VS Code ou IntelliJ pra praticar uma linguagem? Então, isso já pode ser um repositório local.

* ☁️ Se você quiser mandar isso pro GitHub, precisa ter esse repositório local criado primeiro — ele é o ponto de partida pro repositório remoto, que é o que vai pra nuvem.

#### Como criar/clonar?

```bash
# Inicializa um repositório local vazio
git init

# Clona um repositório remoto
git clone <url_do_repositorio>
```

---

### 3. Ver o status e adicionar arquivos

```bash
# Confere o status dos arquivos
git status

# Adiciona um arquivo específico à área de staging
git add nome_do_arquivo

# Adiciona todos os arquivos modificados
git add .
```

💡 **O que é a área de staging?**
Basicamente, é como dizer: *"Ok, quero incluir essas alterações no meu próximo commit"*.
Ou seja, as alterações são preparadas antes de serem salvas no histórico.

---

### 4. Salvar (commitar) suas alterações

Agora que você manja do que é área de staging, bora entender o que é esse tal commit:

> ✍️ Um **commit** salva no histórico do projeto todas as alterações feitas, e você pode (e deve) descrever o que mudou.

```bash
# Commitar com mensagem? 
git commit -m "mensagem do commit"

# Bora unir o git add . com o git commit + mensagem? 
git commit -am "mensagem do commit"

# Hmm... precisava corrigir a mensagem do ultimo commit?
git commit --amend -m "Nova mensagem"
```

⚠️ **Cuidado com o `--amend` se já tiver feito push**, porque ele altera o histórico.

---

### 5. Histórico dos seus commits

```bash
# Quero ver meus commits anteriores?
git log

# Quero ver um commit especifico?
git show <hash_do_commit>

# Preciso saber pra qual branch foi o commit e ver de forma mais visual?
git log --graph --oneline --decorate --all
```

---

### 6. Vamo entender as branches?

**Branches** são ramificações do seu projeto.
Por padrão, tudo começa na `main` ou `master`, que é a branch principal.

👉 Mas quando você quer desenvolver algo separado — sem afetar o que tá em produção — a melhor prática é **criar uma nova branch**, fazer suas alterações ali e depois **mesclar** (via `merge`) com a principal.

```bash
# Lista as branches que você tem localmente e mostra a branch atual
git branch

# E pra criar branch nova? Fácil
git branch <nome_da_branch>

# Precisou trocar de branch?
git checkout <nome_da_branch>

# Cria e já troca pra ela de uma vez
git checkout -b <nome_da_nova_branch>

# Mescla as alterações de outra branch na atual
git merge <nome_da_branch_que_tem_as_alterações>

# Exclui uma branch local (já mesclada)
git branch -d <nome_da_branch>

# Não preciso dessa branch local mais nem vou precisar ter mesclar (⚠️ cuidado ao usar, hem!)
git branch -D <nome_da_branch>
```

---

### 7. Hora de mandar pro repositório remoto

<p>
  <img src="https://user-images.githubusercontent.com/74038190/218266069-da299265-d22b-41f5-99f1-cf8bfa951c42.gif" width="220" align="left" style="margin-right: 15px;" />
</p>

```bash
# Lista os repositórios remotos vinculados
git remote -v

# Quer adicionar um repositório remoto?
git remote add origin <url_do_repositorio_remoto>

# Adicionou o repositório remoto? Hora de enviar seus commits pra ele
git push origin <nome_da_branch>

# Precisa trazer alterações do repositório remoto e já mesclar com seu local?
git pull origin <nome_da_branch>

# E trazer as alterações do repositório remoto SEM mesclar? (ainda)
git fetch origin <nome_da_branch>
```

<br clear="all" />

---

### 8. Precisa reverter alguma cagada?

Essa parte é delicada. Usa com calma!

```bash
# Volta o HEAD pra um commit e APAGA tudo que veio depois (⚠️ irreversível)
git reset --hard <hash_do_commit>

# Faz o mesmo, mas mantém as alterações na área de staging
git reset --soft <hash_do_commit>

# Remove um arquivo da área de staging (foi adicionado por engano)
git reset HEAD <nome_do_arquivo>

# Quer desfazer alterações NÃO commitadas de um arquivo?
git checkout -- <nome_do_arquivo>

# Cria um novo commit que desfaz o commit anterior (mantém histórico)
git revert <hash_do_commit>
```

---

### 9. BÔNUS

```bash
# Comparar dois commits
git diff <hash_1> <hash_2>

# Ver a diferença entre staging e último commit
git diff
```

🔥 Fez mudanças numa branch mas precisou correr pra outra?

```bash
# Salva temporariamente as alterações e limpa o ambiente
git stash
```

🧠 *Dica*: O `stash` é perfeito quando você ainda **não fez commit**, mas precisa sair daquela branch sem perder o que tava fazendo.

---

## Gostou do conteúdo?

Me acompanha nas redes abaixo, quem sabe eu apareço com mais. 😉

<div style="display: flex; justify-content: left; gap: 20px; align-items: center; margin-top: 10px;">
  <a href="https://www.linkedin.com/in/cssbreno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c8431d9d2483.gif" width="50" alt="Instagram"/>
  </a>
  <a href="https://www.instagram.com/css_breno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294013-a33e5c43-a01c-43f6-b44d-a406d8b4ab75.gif" width="50" alt="LinkedIn"/>
  </a>
</div>

---

## 🇺🇸 -English

### 1. Initial Setup

```bash
# To set your user name
git config --global user.name "your name"

# To set your email:
git config --global user.email "your.email@example.com"
```

> ⚠️ **Attention:** Git is case sensitive. Be careful when using uppercase and lowercase letters!

---

### 2. Now, let's create / clone repositories

#### What is a repository?

A **repository** is a place — either on your machine or online — used to centralize files, data, and resources of a project, making management easier.
🗃️ It’s like a digital vault: you store your projects there, track change history, see who modified what, include code documentation, important files, and even the README.md, which introduces your project to others.

#### Are remote and local repositories the same?

Good question! Let’s break it down:

* 🖥️ The **local** repository is the one on your machine.
  You know when you create a folder in VS Code or IntelliJ to practice a language? That can already be a local repository.

* ☁️ If you want to push that to GitHub, you need to have the local repository first — it’s the starting point for the remote repository, which lives in the cloud.

#### How to create/clone?

```bash
# Initialize an empty local repository
git init

# Clone a remote repository
git clone <repository_url>
```

---

### 3. Check status and add files

```bash
# Check the status of files
git status

# Add a specific file to the staging area
git add file_name

# Add all modified files
git add .
```

💡 **What is the staging area?**
Basically, it’s like saying: *"Ok, I want to include these changes in my next commit"*.
That means changes are prepared before being saved to the history.

---

### 4. Save (commit) your changes

Now that you know about the staging area, let’s understand what a commit is:

> ✍️ A **commit** saves all changes made to the project’s history, and you can (and should) describe what changed.

```bash
# Commit with a message
git commit -m "commit message"

# Combine git add . with commit + message
git commit -am "commit message"

# Need to fix the last commit message?
git commit --amend -m "New message"
```

⚠️ **Be careful with `--amend` if you already pushed**, as it changes the history.

---

### 5. Commit history

```bash
# Want to see previous commits?
git log

# Want to see a specific commit?
git show <commit_hash>

# Want to see which branch a commit belongs to, visually?
git log --graph --oneline --decorate --all
```

---

### 6. Understanding branches

**Branches** are forks of your project.
By default, everything starts on `main` or `master`, the main branch.

👉 When you want to develop something separate — without affecting production — the best practice is to **create a new branch**, make your changes there, and then **merge** with the main one.

```bash
# List local branches and show current branch
git branch

# Create a new branch
git branch <branch_name>

# Switch branch
git checkout <branch_name>

# Create and switch to a new branch at once
git checkout -b <new_branch_name>

# Merge changes from another branch into current
git merge <branch_with_changes>

# Delete a local branch (already merged)
git branch -d <branch_name>

# Force delete local branch (use with caution!)
git branch -D <branch_name>
```

---

### 7. Time to push to remote repository

<p>
  <img src="https://user-images.githubusercontent.com/74038190/218266069-da299265-d22b-41f5-99f1-cf8bfa951c42.gif" width="220" align="left" style="margin-right: 15px;" />
</p>

```bash
# List linked remote repositories
git remote -v

# Add a remote repository
git remote add origin <remote_repository_url>

# Push your commits to remote
git push origin <branch_name>

# Pull remote changes and merge with local
git pull origin <branch_name>

# Fetch remote changes WITHOUT merging yet
git fetch origin <branch_name>
```

<br clear="all" />

---

### 8. Need to undo something?

This part is tricky. Use with caution!

```bash
# Move HEAD to a commit and DELETE everything after (⚠️ irreversible)
git reset --hard <commit_hash>

# Same, but keep changes staged
git reset --soft <commit_hash>

# Remove a file from staging (added by mistake)
git reset HEAD <file_name>

# Undo uncommitted changes in a file
git checkout -- <file_name>

# Create a new commit that undoes a previous commit (keeps history)
git revert <commit_hash>
```

---

### 9. BONUS

```bash
# Compare two commits
git diff <hash_1> <hash_2>

# See differences between staging and last commit
git diff
```

🔥 Made changes on one branch but need to switch quickly?

```bash
# Temporarily save changes and clean workspace
git stash
```

🧠 *Tip:* `stash` is perfect when you haven’t committed yet but need to switch branches without losing your work.

---

## Like the content?

Follow me on the socials below, maybe I’ll bring more. 😉

<div style="display: flex; justify-content: left; gap: 20px; align-items: center; margin-top: 10px;">
  <a href="https://www.linkedin.com/in/cssbreno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c8431d9d2483.gif" width="50" alt="Instagram"/>
  </a>
  <a href="https://www.instagram.com/css_breno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294013-a33e5c43-a01c-43f6-b44d-a406d8b4ab75.gif" width="50" alt="LinkedIn"/>
  </a>
</div>

---

## 🇪🇸 - Español

### 1. Primeros ajustes

```bash
# Para configurar tu nombre de usuario
git config --global user.name "tu nombre"

# Para configurar tu correo:
git config --global user.email "tu.email@ejemplo.com"
```

> ⚠️ **Atención:** Git distingue mayúsculas y minúsculas. ¡Cuida cuando uses letras grandes o pequeñas!

---

### 2. Ahora, vamos a crear / clonar repositorios

#### ¿Qué es un repositorio?

Un **repositorio** es un lugar — ya sea en tu máquina o en línea — usado para centralizar archivos, datos y recursos de un proyecto, facilitando la gestión.
🗃️ Es como una caja fuerte digital: ahí guardas tus proyectos, sigues el historial de cambios, ves quién modificó qué, incluyes documentación del código, archivos importantes e incluso el README.md, que presenta tu proyecto a los demás.

#### ¿Son iguales el repositorio remoto y local?

¡Buena pregunta! Vamos a explicarlo:

* 🖥️ El repositorio **local** es el que está en tu máquina.
  ¿Sabes cuando creas una carpeta en VS Code o IntelliJ para practicar un lenguaje? Eso ya puede ser un repositorio local.

* ☁️ Si quieres subir eso a GitHub, necesitas tener primero el repositorio local — es el punto de partida para el repositorio remoto, que está en la nube.

#### ¿Cómo crear/clonar?

```bash
# Inicializa un repositorio local vacío
git init

# Clona un repositorio remoto
git clone <url_del_repositorio>
```

---

### 3. Ver el estado y añadir archivos

```bash
# Verifica el estado de los archivos
git status

# Añade un archivo específico al área de staging
git add nombre_del_archivo

# Añade todos los archivos modificados
git add .
```

💡 **¿Qué es el área de staging?**
Básicamente, es como decir: *"Ok, quiero incluir estos cambios en mi próximo commit"*.
Es decir, los cambios se preparan antes de guardarse en el historial.

---

### 4. Guardar (commitear) tus cambios

Ahora


que sabes qué es el área de staging, vamos a entender qué es un commit:

> ✍️ Un **commit** guarda en el historial del proyecto todos los cambios realizados, y puedes (y debes) describir qué cambió.

```bash
# Commits con mensaje
git commit -m "mensaje del commit"

# Une git add . con commit + mensaje
git commit -am "mensaje del commit"

# ¿Necesitas corregir el mensaje del último commit?
git commit --amend -m "Nuevo mensaje"
```

⚠️ **Cuidado con `--amend` si ya hiciste push**, porque cambia el historial.

---

### 5. Historial de tus commits

```bash
# Quieres ver tus commits anteriores?
git log

# Quieres ver un commit específico?
git show <hash_del_commit>

# ¿Necesitas saber a qué branch pertenece el commit y verlo visualmente?
git log --graph --oneline --decorate --all
```

---

### 6. ¿Entendemos las branches?

**Branches** son ramificaciones de tu proyecto.
Por defecto, todo comienza en `main` o `master`, que es la rama principal.

👉 Pero cuando quieres desarrollar algo separado — sin afectar lo que está en producción — la mejor práctica es **crear una nueva branch**, hacer tus cambios ahí y luego **fusionar** (via `merge`) con la principal.

```bash
# Lista las branches locales y muestra la actual
git branch

# ¿Cómo crear una branch nueva? Fácil
git branch <nombre_de_branch>

# ¿Necesitas cambiar de branch?
git checkout <nombre_de_branch>

# Crear y cambiar a una branch nueva al mismo tiempo
git checkout -b <nombre_de_nueva_branch>

# Fusiona cambios de otra branch a la actual
git merge <nombre_de_branch_con_cambios>

# Borra una branch local (ya fusionada)
git branch -d <nombre_de_branch>

# Borra una branch local sin importar si está fusionada (¡cuidado!)
git branch -D <nombre_de_branch>
```

---

### 7. Hora de mandar al repositorio remoto

<p>
  <img src="https://user-images.githubusercontent.com/74038190/218266069-da299265-d22b-41f5-99f1-cf8bfa951c42.gif" width="220" align="left" style="margin-right: 15px;" />
</p>

```bash
# Lista repositorios remotos vinculados
git remote -v

# ¿Quieres agregar un repositorio remoto?
git remote add origin <url_del_repositorio_remoto>

# ¿Agregaste el remoto? Ahora manda tus commits para allá
git push origin <nombre_de_branch>

# ¿Necesitas traer cambios del remoto y fusionarlos con tu local?
git pull origin <nombre_de_branch>

# ¿Traer cambios del remoto SIN fusionar todavía?
git fetch origin <nombre_de_branch>
```

<br clear="all" />

---

### 8. ¿Necesitas revertir algo?

Esta parte es delicada. ¡Usa con cuidado!

```bash
# Vuelve el HEAD a un commit y BORRA todo lo que vino después (⚠️ irreversible)
git reset --hard <hash_del_commit>

# Igual, pero mantiene los cambios en staging
git reset --soft <hash_del_commit>

# Quita un archivo del área de staging (lo agregaste por error)
git reset HEAD <nombre_del_archivo>

# ¿Quieres deshacer cambios NO commiteados de un archivo?
git checkout -- <nombre_del_archivo>

# Crea un commit que deshace el commit anterior (mantiene historial)
git revert <hash_del_commit>
```

---

### 9. BÓNUS

```bash
# Comparar dos commits
git diff <hash_1> <hash_2>

# Ver diferencias entre staging y último commit
git diff
```

🔥 ¿Hiciste cambios en una branch pero necesitas cambiar rápido a otra?

```bash
# Guarda temporalmente los cambios y limpia el entorno
git stash
```

🧠 *Consejo:* El `stash` es perfecto cuando aún **no hiciste commit** pero necesitas salir de esa branch sin perder lo que estabas haciendo.

---

## ¿Te gustó el contenido?

Sígueme en las redes abajo, quizás traiga más contenido. 😉

<div style="display: flex; justify-content: left; gap: 20px; align-items: center; margin-top: 10px;">
  <a href="https://www.linkedin.com/in/cssbreno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c8431d9d2483.gif" width="50" alt="Instagram"/>
  </a>
  <a href="https://www.instagram.com/css_breno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294013-a33e5c43-a01c-43f6-b44d-a406d8b4ab75.gif" width="50" alt="LinkedIn"/>
  </a>
</div>

---