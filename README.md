<!-- Banner principal -->
<div align="center">
  <img src="https://github.com/Anmol-Baranwal/Cool-GIFs-For-GitHub/assets/74038190/d48893bd-0757-481c-8d7e-ba3e163feae7" width="100%" alt="Banner principal do guia de Git">
</div>
<br>
<br>
<br>
<!-- Cabeçalho com animação -->
<div align="center" style="margin-top: -20px;">
  <img src="https://user-images.githubusercontent.com/74038190/212281775-b468df30-4edc-4bf8-a4ee-f52e1aaddc86.gif" width="100" />
  <br>
  <br>
  <br>

  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&duration=3000&pause=1000&color=FFD700&center=true&vCenter=true&width=900&lines=Dominando+o+Git:+Seu+Guia+Essencial+Multilingue" alt="Typing SVG">
  </a>
</div>

## 🛠️ 1. Primeiras configurações


```bash
# Para definir seu nome de usuário
git config --global user.name "seu nome"

# Para definir seu e-mail:
git config --global user.email "seu.email@examplo.com"
````

<h4>⚠️ ATENÇÃO: O Git é case sensitive viu. Se liga na hora de usar maiúsculo e minúsculo!</h4>

---

## 📦 2. Agora, vamos criar / clonar repositórios

### ❓ O que é um repositório?

<span><strong>Repositório</strong></span> é um local — seja na sua máquina ou online — usado para centralizar arquivos, dados e recursos de um projeto, facilitando o gerenciamento.
🗃️ É tipo um cofre digital: nele você guarda seus projetos, acompanha o histórico de alterações, vê quem modificou o quê, inclui a documentação do código, arquivos importantes e até o README.md, que apresenta seu projeto pra galera.

---

### 🔁 Repositório remoto e local são a mesma coisa?

Boa pergunta! Bora destrinchar isso:

* 🖥️ O repositório **local** é o que tá na sua máquina.
  Sabe quando você cria uma pasta no VS Code ou IntelliJ pra praticar uma linguagem? Então, isso já pode ser um repositório local.

* ☁️ Se você quiser mandar isso pro GitHub, precisa ter esse repositório local criado primeiro — ele é o ponto de partida pro repositório remoto, que é o que vai pra nuvem.

---

### 🔨 Como criar/clonar?

```bash
# Inicializa um repositório local vazio
git init

# Clona um repositório remoto
git clone <url_do_repositorio>
```

---

## 🔍 3. Ver o status e adicionar arquivos

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

## 💾 4. Salvar (commitar) suas alterações

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

## ✅ Boas práticas de commit

### ✔️ Escreve mensagens curtas, claras e no imperativo:

* `Corrige bug em produção`
* `Resolve exercícios de POO`
* `Atualiza título do README`

### ❌ Evita mensagens genéricas:

* `Ajustes no código` ❌
* `Refatora função de envio de e-mails` ✅

---

## 🏷️ Prefixos que ajudam na organização

Esses prefixos seguem o padrão [Conventional Commits](https://www.conventionalcommits.org):

| Prefixo     | Quando usar                               |
| ----------- | ----------------------------------------- |
| `feat:`     | Funcionalidade nova                       |
| `fix:`      | Correção de bug                           |
| `docs:`     | Mudança só na documentação                |
| `refactor:` | Refatoração que não altera comportamento  |
| `test:`     | Adição ou modificação de testes           |
| `chore:`    | Tarefas internas (configs, dependências…) |

---

Quer dar uma aprofundada na coisa?
👉 Visita o [site oficial do Conventional Commits](https://www.conventionalcommits.org), tem muita coisa bacana!

---


### 🔄 5. Histórico dos seus commits

```bash
# Ver seus commits anteriores
git log

# Ver um commit específico
git show <hash_do_commit>

# Ver de forma mais visual, com gráfico e informações de branches
git log --graph --oneline --decorate --all
````

💡 Esse é mamão demais, nem precisa de muita explicação! 👌

---

### 🌿 6. Vamo entender as branches?

**Branches** são ramificações do seu projeto.
Por padrão, tudo começa na `main` ou `master`, que é a branch principal.

👉 Mas quando você quer desenvolver algo separado — sem afetar o que tá em produção — a melhor prática é **criar uma nova branch**, fazer suas alterações ali e depois **mesclar** (via `merge`) com a principal.

```bash
# Lista as branches locais e mostra qual você está
git branch

# Cria uma nova branch
git branch <nome_da_branch>

# Troca de branch
git checkout <nome_da_branch>

# Cria e já troca pra ela de uma vez
git checkout -b <nome_da_nova_branch>

# Mescla as alterações de outra branch na atual
git merge <nome_da_branch_que_tem_as_alterações>

# Exclui uma branch local (já mesclada)
git branch -d <nome_da_branch>

# Exclui uma branch local sem precisar ter mesclado (⚠️ perigoso!)
git branch -D <nome_da_branch>
```

---

<h3>🚀 7. Hora de mandar pro repositório remoto</h3>

<p>
  <img src="https://user-images.githubusercontent.com/74038190/218266069-da299265-d22b-41f5-99f1-cf8bfa951c42.gif" width="220" align="left" style="margin-right: 15px;" />
</p>

```bash
# Lista os repositórios remotos vinculados
git remote -v

# Adiciona um novo repositório remoto
git remote add origin <url_do_repositorio_remoto>

# Envia os commits para a branch remota
git push origin <nome_da_branch>

# Traz alterações do repositório remoto e já mescla com seu local
git pull origin <nome_da_branch>

# Traz as alterações do repositório remoto SEM mesclar ainda
git fetch origin <nome_da_branch>

```
<br clear="all" />

<hr>


<h3>⏪ 8. Precisa reverter alguma cagada?</h3>
<br>

<p>⚠️ Essa parte é delicada. Usa com calma!</p>

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

<br clear="all"/>

<hr>


### 🎁 9. BÔNUS

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

---

## Gostou do conteúdo? 

Me acompanha nas redes abaixo, quem sabe eu apareço com mais. 😉

<div style="display: flex; justify-content: left; gap: 20px; align-items: center; margin-top: 10px;">
  <a href="https://www.instagram.com/css_breno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294012-0a55e343-37ad-4b0f-924f-c8431d9d2483.gif" width="50" alt="Instagram"/>
  </a>
  <a href="https://www.linkedin.com/in/cssbreno" target="_blank" rel="noopener">
    <img src="https://user-images.githubusercontent.com/74038190/235294013-a33e5c43-a01c-43f6-b44d-a406d8b4ab75.gif" width="50" alt="LinkedIn"/>
  </a>
</div>
