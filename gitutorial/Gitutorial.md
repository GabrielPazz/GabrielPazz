# Como usar o Git e Github na prática
 
## Criar um projeto novo

* Criar um arquivo `README.md` por exemplo

* Abre o Git Bash (pode ser pelo terminal do VSCode mesmo) na pasta

* `git init` para inicializar o repositório

Foi criada uma pastinha `.git` e é ali que toda a mágica acontece, então não apague

* `git add README.md` para colocar o arquivo na área de stagging 

<img src="https://i1.wp.com/www.markus-gattol.name/misc/mm/si/content/git_git_add.png">

* `git commit -m "primeiro commit"` para de fato dar o commit no repositório

* `git branch -M "main"` para alterar o nome da branch principal de `master` para `main` (isso é uma boa prática atualmente recomendada)

## Repositório no Github

* Para passar o commit do meu repositório local (da minha máquina) para um repositório na plataforma do Github, usamos o `git remote add origin <link do repositório>`

* `origin` é o nome utilizado para referenciar o nosso repositório a partir de agora


* Para isso precisaremos empurrar, enviar para lá com o `git push -u origin main`

Agora se recarregarmos a página iremos ver o nosso arquivo aqui na plataforma!

## Alterando e adicionando arquivo

Primeira coisa que faremos então é alterar esse arquivo que já commitamos

* Adiciona mais uma frase no arquivo `Essa é uma alteração`

* Além disso iremos criar um novo arquivo `Projeto.md`, onde escreveremos `Esse é o novo arquivo onde continuarei o meu projeto`

* Agora então precisamos subir essa alteração, pra isso seguiremos os mesmos passos de `git add .` (agora ponto `.` pois adiciona todos os arquivos) e `git commit -m "Primeira alteração"`

* Lembrando que para alterar algo no nosso respositório do Github precisamos dar o push, então `git push origin main` (sem o -u)

Se olharmos agora o nosso código no Github, ele terá sido alterado, e não só isso, se clicarmos no nome do `commit`, podemos ver exatamente as alterações que foram feitas nele.
O verde com `+` e o vermelho com `-` mostra, os conteúdos que foram adicionados e editados dentro do código.

## Branch

* Nesse caso vamos adicionar um novo arquivo para desenvolver a nossa feature `Botão`

* Então a primeira coisa que fazemos é `git checkout -b "novo-botao"`, assim criando uma branch para ele

* Vou então criar o arquivo, criar o `botão.md` "aqui eu crio o botão"

* E agora fazemos o passo a passo que já sabemos, colocamos a nossa alteração em stagging com o `git add .` e commitamos com o `git commit -m "novo botão"`

* Para enviarmos agora que vai ser diferente. Vocês lembram que utilizávamos o `git push orgin main` né? Porém main era aquela branch principal. Agora então usaremos `git push origin botao`

Agora se olharmos o nosso Github, veremos que tem 2 branches, a `main` e a `botao`

<img src="https://media.discordapp.net/attachments/812313742192279612/836820670037622854/unknown.png">

Vamos supor que eu ainda não tivesse terminado de desenvolver o botão, eu poderia continuar tranquilamente na branch `botao` até terminar!

E se eu precisasse por algum motivo voltar naquela branch `main` e desenvolver a partir do que deixei lá? Sem problemas, a única coisa que você precisa fazer nesse caso é `git checkout main`, e pra voltar depois é só `git checkout botao` novamente

Beleza! Agora desenvolvi tudo o que queria aqui na branch `botao`, como que junto ela com a main sem problemas?

## Merge

* Agora o que precisamos fazer é ir para a nossa branch principal `git checkout main` e lá faremos o merge com a branch `botao` que criamos, com `git merge botao`

Pronto, agora tudo o que tinha de alteração na branch `botao` juntou com a `main`

* Para finalizar então, vamos jogar lá no Github isso tudo com o `git push origin main`

## Clone

* O comando para puxar o projeto para a sua máquina é o `git clone https://github.com/rafaballerini/GitTutorial.git`

## Pull

E se eu fizer uma alteração no repositório, como vocês podem atualizar na máquina de vocês?

* Basta vocês executarem o comando `git pull`, ele irá puxar todas as alterações feitas no repositório do Github para o seu repositório local

## Pull request

O último conceito que quero ensinar para vocês é o de Pull Request, vamos entender como ele funciona:

* Após você ter dado um fork no projeto e ele ter ido pra sua conta, você poderá alterar o projeto e adicionar as funcionalidades que deseja

* Depois disso, você poderá salvar o projeto, dar o `git add .`, `git commit -m "validação de botões"` e `git push origin main`

Quando você for olhar o seu Github, você verá que branch do seu repositório está 1 commit "na frente" da branch original

Ao clicar no botão `contribute`, você será direcionado para uma página que fará a avaliação se esse `pull request` terá conflitos ou não com o código no repositório original. Caso não tenha, bastão clicar no botão de `Create pull request`

Depois disso, basta esperar para que o dono da branch original aceite o seu pull request

## Lista de Comandos do Git

* git init
* git status
* git config --list -> configuração atual
* git config user.email/user.name -> email/nome atual
* git add 'file.txt'
* git remote add origin -> adicionar conexão
* git remote -v -> conexões feitas
* git commit -m "Mensagem"
* git push origin main
* git branch -> branchs existentes
* git checkout branch -> trocar de branch
* git checkout -b branch_origem branch_nova -> criar uma nova branch a partir da antiga
* git merge "branch" -> juntar branchs
* git pull -> atualizar codigo 
