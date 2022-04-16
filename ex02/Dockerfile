# Imagem base mínima (5.59MB)
FROM alpine:3.14

# Instala o programa thttpd.
# thttpd --> Serve o html, ele não faz nenhum tipo de processamento
# alpine utiliza o apk como gerenciador de pacotes, ele é como o apt-get instal do ubuntu ou outas distribuiçoes
# apk add thttpd é como se fosse apt-get install thttpd
# RUN: executa o comando passado na hora( Durante o build / durante a criação da imagem)
RUN apk add thttpd

#OBS: por padrão, quando estamos construindo a imagem, é como se eu fosse o root dessa imagem. Isso é muito perigoso em questão de segurança. Então como boa pratica, crie sempre um usuario novo.

# Cria um novo usuário simples que não tem permissões de root
# static é o nome do usuario, poderia ser qualquer outro nome
RUN adduser -D static
# Estou mandando o docker parar de usar root e apartir desse ponto começar a usar static. (Não utilize mais um usuário com permiçoes de root)
USER static

# Cria-se um nova pasta dentro da imagem
# Geralmente crio uma pasata chamada /app
WORKDIR /home/static
#WORKDIR: Poupa eu escrever
  # RUN mkdir home
  # RUN cd home
  # RUN mkdir static

# Copia arquivo HTML da minha maquina para dentro da imagem
# Podemos passar um caminho tbm com varios arquivos
# Nesse caso estou copiando de um arquivo para outro arquivo
# COPY . . ---> sig: copie tudo da pasta atual, para a pasta atual da minha imagem
# OBS: Por padrao o copy vai deixar o arquivo da minha imagem com permição de root. Ennt se eu me conectar dentro do container e tentar editar, eu não vou conseguir. (Nos próximos exercicios será mostrado como mudar isso caso seja necessário)
COPY index.html index.html

# Executa o programa thttpd para entregar arquivos HTML na pasta "/home/static"
CMD ["thttpd", "-D", "-h", "0.0.0.0", "-p", "3000", "-d", "/home/static", "-u", "static", "-l", "-"]
  # thttpd --> execute esse binario
  #  "-D" --> Deixa em background. Se não tiver o -D o container morre na hora, 
  # "-h", "0.0.0.0" --> permite executar em qualquer IP (Então qualquer IP vai poder se comunicar com a imagem)
  # "-p", "3000" --> a porta é a 3000
  # "-d", "/home/static" --> diretorio
  #  "-u", "static" --> usuario que vai servir esses arquivos
  #  "-l", "-" --> logs de acesso vai esta no -(traço) que é o proprio console(ao inves de jogar no arquivo, vai ser jogado na tela)

# Construção da imagem:
#RODAR O COMANDO NO TERMINAL:
  # docker build . -t ex02
  # docker run -p 1234:3000 ex02 
  #OU
  # docker run --rm -p 1234:3000 ex02 -> remove o container depois que executar 
    # -p : Mapeia uma porta de dentro do container para uma da minha maquina. 1° argumento é a porta da minha maquina o outro é o do container
  # docker start -a nomeDoContainer
