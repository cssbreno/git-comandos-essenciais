<div align="center">
  <a href="https://git.io/typing-svg">
    <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=700&size=28&duration=3000&pause=1000&color=FFD700&center=true&vCenter=true&width=900&lines=Dominando+o+Git:+Seu+Guia+Essencial+Multilingue+(PT,+EN,+ES)" alt="Typing SVG">
  </a>
</div>

<h3>1. Primeiras configurações</h3>

- Para definir seu nome de usuário: ```git config --global user.name "seu nome"```
- Para definir seu e-mail: ```git config --global user.email "seu.email@examplo.com"```

#

<h3>2. Agora, vamos criar / clonar repositórios</h3>

Antes de mais nada, você sabe o que é um repositório?

<span><strong>Repositório</strong></span> é um local — seja na sua máquina ou online — usado para centralizar arquivos, dados e recursos de um projeto, facilitando o gerenciamento. É tipo um cofre digital: nele você guarda seus projetos, acompanha o histórico de alterações, vê quem modificou o quê, inclui a documentação do código, arquivos importantes e até o README.md, que apresenta seu projeto pra galera.

<p><strong>Repositório remoto e local são a mesma coisa?</strong></p>

- Boa pergunta! Bora destrinchar isso:

  O repositório <strong>local</strong> é o que tá na sua máquina. Sabe quando você cria uma pasta no VS Code ou IntelliJ pra praticar uma linguagem? Então, isso já pode ser um repositório local. Agora, se você quiser mandar isso pro GitHub, precisa ter esse repositório local criado primeiro — ele é o ponto de partida pro repositório remoto, que é o que vai pra nuvem.

E como eu crio um repositório local? Dá uma conferida aqui embaixo que eu te mostro:

- Para inicializar/criar um repositório novo e vazio: ```git init```
- Mas se você já tiver criado um repositório remoto? É só mandar um: ```git clone <url_do_repositorio>``` pra trazer o que tiver dentro dele

#

<h3>3. Ver o status e adicionar arquivos</h3>

- Pra ver como tá seus arquivos, só jogar um: git status
- Quer adicionar seu arquivo na área de staging? git add <nome_do_arquivo>
    - Vou ter que fazer isso pra todos? Que nada! Usa um ```git add .``` que serve pra  todos.

    Quase me esqueci de um detalhe. Afinal, o que é área de staging?
        -- Basicamente dá pra resumir como se você estivesse dizendo: "Ok, eu quero incluir essas alterações (ou esse novo arquivo) no meu próximo commit", assim, as alterações são preparadas pra você commitar. 

#

<h3>4. Salvar (commitar) suas alterações</h3>