#Autor: Robson Vaamonde<br>
#Procedimentos em TI: http://procedimentosemti.com.br<br>
#Bora para Prática: http://boraparapratica.com.br<br>
#Robson Vaamonde: http://vaamonde.com.br<br>
#Facebook Procedimentos em TI: https://www.facebook.com/ProcedimentosEmTi<br>
#Facebook Bora para Prática: https://www.facebook.com/BoraParaPratica<br>
#Instagram Procedimentos em TI: https://www.instagram.com/procedimentoem<br>
#YouTUBE Bora Para Prática: https://www.youtube.com/boraparapratica<br>
#Data de criação: 16/01/2023<br>
#Data de atualização: 12/12/2023<br>
#Versão: 0.10<br>

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO NODEJS SE VOCÊ CONSEGUIU FAZER O DESAFIO COM 
A SEGUINTE FRASE: Desafio do Node.JS realizado com sucesso!!! #BoraParaPrática

COMPARTILHAR O SELO DO DESAFIO NAS SUAS REDES SOCIAIS (LINKEDIN, FACEBOOK, INSTRAGRAM)
MARCANDO: ROBSON VAAMONDE COM AS HASHTAGS E COPIANDO O CONTEÚDO DO DESAFIO ABAIXO: 

LINK DO SELO: https://github.com/vaamonde/ubuntu-2204/blob/main/selos/05-nodejs.png

#boraparapratica #boraparaprática #vaamonde #robsonvaamonde #procedimentosemti #ubuntuserver 
#ubuntuserver2204 #desafiovaamonde #desafioboraparapratica #desafionodejs #desafiojavascript

Conteúdo estudado nesse desafio:<br>
#01_ Instalado as Dependências do Node.JS;<br>
#02_ Instalando o Node.JS no Ubuntu Server;<br>
#03_ Verificando as Versões do Node.JS e NPM;<br>
#04_ Criando o diretório do Projeto do Node.JS;<br>
#05_ Inicializando o Projeto do Node.JS e Instalando o Express;<br>
#06_ Criando o Arquivos INDEX.JS do Node.JS;<br>
#07_ Criando o Primeiro Código em JavaScript do Node.JS;<br>
#08_ Executando uma Aplicação Node.JS via Terminal;<br>
#09_ Verificando a Porta de Conexão da Aplicação Node.JS;<br>
#10_ Testando a Aplicação via Navegador;<br>
#11_ Gerenciando Processos do Node.JS no Ubuntu Server;<br>
#12_ Desafio de uma Nova Aplicação do Node.JS.

Site Oficial do Node.JS: https://nodejs.org/en/<br>
Site Oficial do NPM: https://www.npmjs.com/<br>
Github do Nodesource: https://github.com/nodesource/distributions#debian-and-ubuntu-based-distributions

Site Oficial do W3C School HTML5: https://www.w3schools.com/html/default.asp<br>
Site Oficial do W3C School CSS: https://www.w3schools.com/css/default.asp<br>
Site Oficial do W3C School JavaScript: https://www.w3schools.com/js/default.asp<br>
Site Oficial do W3C School PHP: https://www.w3schools.com/php/default.asp<br>
Site Oficial do W3C School Node.JS: https://www.w3schools.com/nodejs/

Node.js é um software de código aberto, multiplataforma, baseado no interpretador V8 do<br>
Google e que permite a execução de códigos JavaScript fora de um navegador web. A principal<br>
característica do Node.js é sua arquitetura assíncrona e orientada por eventos.

[![Node.JS](http://img.youtube.com/vi//0.jpg)]( "Node.JS")

Link da vídeo aula: 

#01_ Instalando as Dependências do Node.JS<br>

	#atualizando as listas do Apt
	sudo apt update
	
	#instalando as dependências do Node.JS
	#opção da contra barra (\): criar uma quebra de linha no terminal
	sudo apt install git vim curl gnupg gcc g++ make software-properties-common \
	build-essential ca-certificates

#02_ Instalando a Versão LTS do Node.JS e do NPM (Node Packet Manager)<br>

	#adicionando o repositório do Node.JS via Nodesource: https://deb.nodesource.com/
	#opção do comando curl: -f (fail), -s (silent), -S (show-error), -L (location)
	#opção do redirecionador |: Conecta a saída padrão com a entrada padrão de outro comando
	#opção do comando sudo: -E (preserve-env)
	
	#Script de configuração do Repositório do Node.JS descontinuado, não é mais indicado
	#utilizar esse script em servidores de produção.
	#sudo curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash
	
	#Adicionando a Chave GPG do Node.JS via Nodesource
	curl -fsSL https://deb.nodesource.com/gpgkey/nodesource-repo.gpg.key | sudo gpg --dearmor -o /usr/share/keyrings/nodesource.gpg
	
	#Adicionando o Repositório do Node.JS
	#OBSERVAÇÃO IMPORTANTE: é indicado utilizar sempre a versão LTS (Long Time Support) do
	#Node.JS em servidores de Produção, consulte sempre a versão LTS no Site Oficial do Node 
	#no Link: https://nodejs.org/en e no Link: https://nodejs.org/en/about/previous-releases
	echo "deb [signed-by=/usr/share/keyrings/nodesource.gpg] https://deb.nodesource.com/node_20.x nodistro main" | sudo tee /etc/apt/sources.list.d/nodesource.list

	#Instalando o Node.JS e NPM (Node Package Manager)
	sudo apt update
	sudo apt install nodejs

#03_ Verificando as Versões do Node.JS e NPM (Node Package Manager)<br>

	#opção do comando node: -v (version)
	#opção do comando npm: -v (version)
	sudo node -v
	sudo npm -v

#04_ Criando um Projeto Simples para Testar o Node.JS<br>

	#criando o diretório do projeto de teste do Node.JS
	#opção do comando mkdir: -v (verbose)
	mkdir -v nodejs-hello
	cd nodejs-hello
		
		#Inicializando o diretório do Projeto do Node.JS
		#opção do comando npm: init (create package.json file), -y (yes)
		npm init -y
		
		#Instalando o Módulo/Pacote Express do Node.JS
		#opção do comando npm: install (install package in directory)
		npm install express

		#Listando o conteúdo do diretório do projeto do Node.JS
		#opção do comando ls: -l (long listing), -h (human-readable), -a (all)
		ls -lha

#05_ Criando um Projeto Simples do Node.JS<br>

	#Criando o arquivo index.js do projeto do Node.JS
	vim index.js
	INSERT

```js
// Criando as variáveis do Express e do App do Node.JS
var express = require ('express'); 
var app = express();

// Mensagem que será mostrada no browser (navegador) 
app.get('/', function (req, res) {
	res.send('Seu Nome e Sobrenome #BoraParaPrática!!!');
});

// Porta padrão utilizada pela aplicação do Node.JS
app.listen(3000, function() {
	console.log('Aplicativo de exemplo ouvindo na porta 3000');
});
```
	#salvar e sair do arquivo
	ESC SHIFT :x <Enter>

#06_ Executando o Projeto Simples do Node.JS utilizando o Express<br>

	#opção do comando &: background
	node index.js &

#07_ Verificando a Porta de Conexão do Node.JS Express<br>

	#opção do comando lsof: -n (network number), -P (port number), -i (list IP Address), -s (alone directs)
	sudo lsof -nP -iTCP:'3000' -sTCP:LISTEN

#08_ Acessando o Projeto Simples do Node.JS<br>

	firefox ou google chrome: http://endereço_ipv4_ubuntuserver:3000

#09_ Finalizando a Execução do Projeto Simples do Node.JS<br>

	#verificando os processos em segundo plano (background)
	jobs
	
	#trazendo o processo em segundo plano do Node.JS para o primeiro plano (foreground)
	fg

	#finalizando o processo do Node.JS Express
	Ctrl + C

	#OBSERVAÇÃO IMPORTANTE: caso você não consiga trazer os processos que estão em Segundo
	#Plano (Background) para o Primeiro Plano (Foreground) para finalizar o processo, você
	#pode utilizar o comando: ps -u e na coluna: PID finalizar o processo com o comando:
	#kill -9 PID

#10_ DESAFIO-01: FAZER A CRIAÇÃO DE UM NOVO PROJETO DO NODE.JS EXPRESS, CRIAR UM DIRETÓRIO COM:
seu_nome (TUDO EM MINÚSCULO) NA RAIZ DO PERFIL DO SEU USUÁRIO: /home/seu_usuário, CRIAR UMA 
PÁGINA DENTRO DO SEU DIRETÓRIO CHAMADA: seunome.js (TUDO EM MINÚSCULO), MUDAR A MENSAGEM NO 
BROWSER PARA: Meu novo projeto em Node.JS - Seu Nome, MUDAR A PORTA DO PROJETO PARA 3030 E
ADICIONAR MAIS ALGUM RECURSO DO NODE.JS NO SEU PROJETO (VEJA O SITE W3SCHOOLS)

#11_ DESAFIO-02: DEIXAR OS DOIS PROJETOS DO NODE.JS RODANDO EM SEGUNDO PLANO (BACKGROUND),
NO WORDPRESS CRIAR OS HYPER LINKS PARA OS PROJETOS IGUAL QUE FOI FEITO NO DESAFIO-03 DO
WORDPRESS PARA AS PÁGINAS HTML E PHP, NÃO ESQUEÇA DE TESTAR O ACESSO.

=========================================================================================

OBSERVAÇÃO IMPORTANTE: COMENTAR NO VÍDEO DO NODEJS SE VOCÊ CONSEGUIU FAZER O DESAFIO COM 
A SEGUINTE FRASE: Desafio do Node.JS realizado com sucesso!!! #BoraParaPrática

COMPARTILHAR O SELO DO DESAFIO NAS SUAS REDES SOCIAIS (LINKEDIN, FACEBOOK, INSTRAGRAM)
MARCANDO: ROBSON VAAMONDE COM AS HASHTAGS E COPIANDO O CONTEÚDO DO DESAFIO ABAIXO: 

LINK DO SELO: https://github.com/vaamonde/ubuntu-2204/blob/main/selos/05-nodejs.png

#boraparapratica #boraparaprática #vaamonde #robsonvaamonde #procedimentosemti #ubuntuserver 
#ubuntuserver2204 #desafiovaamonde #desafioboraparapratica #desafionodejs #desafiojavascripe