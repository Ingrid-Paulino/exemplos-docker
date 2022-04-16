# Imagem base mínima (5.59MB)
FROM alpine:3.14

# Instala o programa thttpd.
RUN apk add thttpd

# Cria um novo usuário simples que não tem permissões de root
RUN adduser -D static
USER static

# Cria-se um nova pasta dentro da imagem
WORKDIR /home/static

# Copia arquivo HTML para dentro da imagem e setando permissão ao mesmo tempo
# Estou falando que o usuario dono do meu destiono é o static, e não o root
# static:static --> sig que vai ser do usuario e grupo static (todo usuario tbm é um grupo)
COPY --chown=static:static index.html index.html

# Executa o programa thttpd para entregar arquivos HTML na pasta "/home/static"
CMD ["thttpd", "-D", "-h", "0.0.0.0", "-p", "3000", "-d", "/home/static", "-u", "static", "-l", "-"]


# Enviando uma imagem para um register:
#RODAR O COMANDO NO TERMINAL:
  # docker build . -t ex05
  # docker run --rm -p 1234:3000 --name meu-container ex05
  # docker exec -it meu-container sh-> executa um comandos dentro de um container que ja esta em execução
    #ls
    #vi index.html --> editor de texto dentro do meu container. Eu posso editar alguma frase
    #cat index.html --> mostra o arquivo
    #exit
  #docker logs meu-container --> começa e termina(n mantem)
  #docker logs meu-container -f --> continua vendo o container

    