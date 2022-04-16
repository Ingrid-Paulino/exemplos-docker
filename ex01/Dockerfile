# Imagem base mínima (5.59MB)
#FROM === Apartir de qual imagem eu vou começar a construir a minha imagem.

# FROM scratch  --> Temos a possibilidade de não começar por nada: é um comando dentro do Docker build que ele não faz nada. Ou seja, é uma imagem que não vai ter nada.

# Depois dos 2 pontos é a tag, que indica a versão da imagem

#OBS: Encontamos imagens la no DockerHub

FROM alpine:3.14 


# CMD --> Executa o comando passado 
# Executa comando "echo"
CMD ["echo", "Sou pessoa estudante da Trybe!"]

# Construção da imagem:
#RODAR O COMANDO NO TERMINAL:
  # docker build . -t ex01
    # O ponto sinaliza para o executar na pasta atual
    # ex01 é o nome dado para a imagem
  # docker run ex01 -->  sobe o container
  # docker start -a nomeDoContainer
    # -a --> mostra o container na tela depois de executado
    # start --> Roda o conteiner novamente


# Comandos a mais:
# docker system prune -a --> Limpa o docker, apaga tudoooooo

# docker images ls OU docker images --> mostra todas as imagens

# docker ps -a --> mostra todos os containers(ativos e parados)

# docker rm nomeDoContainer --> remove o container