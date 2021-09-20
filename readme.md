# Passo a passo Git + Github
## Configurando a máquina local como uma máquina confiável para o Github
* No git bash:
. Digitar (sem as aspas) "ssh-keygen -t ed25519 -C email@email.com" 
	Este email deve ser o mesmo utilizado na conta do Github;
. Escolher o local que será salva a chave SSH, aconselha-se manter na pasta C/Users/_nomeUsuario_, então apenas pressione _enter_ para confirmar;
. Escolha uma senha da chave e depois confirme
. Navegue até a pasta onde foi criada a chave
	"cd /c/Users/_nomeUsuario_/.ssh/"
	Caso já esteja dentro da pasta de usuário digite apenas
	"cd .ssh/"
. Digite o comando (sem aspas) "cat id_ed25519.pub"
. Copie a chave gerada (todo o texto, até o final do e-mail)
* No navegador:
. Clique na imagem de perfil no canto superior direito;
. Clique em "settings";
. Clique em "SSH and GPG keys" no menu lateral;
. Clique no botão "new SSH key" no canto superior direito;
. Escolha um título para a chave (ex: Meu PC);
. Cole a chave gerada no gitbash dentro da área key;
. Confirme a senha do github
* Voltando ao Gitbash, dentro da pasta /.ssh
. Digite o comando (sem aspas)
	"eval $(ssh-agent -s)"
. Digite o comando (sem aspas)
	"ssh-add id_ed25519"
. Digite a senha da chave criada anteriormente e pressione enter

## Resolvendo problema de autenticação
[password authentication was removed please use a personal access to](https://stackoverflow.com/questions/68775869/support-for-password-authentication-was-removed-please-use-a-personal-access-to)

## Iniciando um novo repositório com git (criaremos a pasta workspace dentro da pasta c)
* Criar a pasta
. Dentro da pasta c/Users/_nomeUsuario_ digite o comando 
	"mkdir workspace"
. Digite o comando
	"cd workspace"
. Digite o comando
	"mkdir _nomePastaProjeto_"
. Digite o comando
	"cd _nomePastaProjeto_"
* Inicializar e configurar um repositório vazio dentro da pasta criada
. Dentro da pasta criada, digite o comando (sem aspas)
	"git init"
. Para confirmar se o repositório foi inicializado, digite o comando (sem aspas) e verifique se existe a pasta .git
	"ls -a"
. Digite os comandos (sem aspas simples) para atrelar o autor do github (caso seja a promeira vez usando o git)
	'git config --global user.email "email@email.com"' (email de usuario do github)
	'git config --global user.name "_nomeUsuario_" (usuário do github)

## Versionar
. Depois de criar ou modificar os arquivos, digite o comando no gitbash (dentro do repositório criado)
	"git add *" para adicionar todos os arquivos que estavam com o status modified para serem comitados
. Digite o comando (sem aspas simples) para commitar os arquivos modificados
	'git commit -m "_aqui vai uma mensagem_"

## Trabalhar com repositório remoto
* No navegador:
. No github, clique em _Repositories_
. Clique no botão _new_
. Escolha o nome do repositório e a descrição
. Selecione a opção _Public_
. Pode criar um README, caso não tenha criado
. Clique no botão _Create repository_
. Copie a url criada (está no quadro "or push an existing repository from the command line)
* No gitbash:
. Digite o comando (sem aspas)
	". git remote add origin _https://github.com/_nomeUsuario_/_nomeRepositorio_"
. Digite o comando (sem aspas) para ver se está tudo ok
	"git remote -v"
. Digite o comando (sem aspas) para enviar o repositório local para o remoto
	"git push origin main" 
	Dependendo da situação pode ser master no lugar de main

**Pronto, os arquivos agora estão no repositório remoto!** 
