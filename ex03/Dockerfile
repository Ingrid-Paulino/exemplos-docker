FROM python:alpine3.15

# Estou copiando a arquivo hello.py e hello2.py, para dentro da imagem
COPY hello.py hello.py
COPY hello2.py hello2.py

# OBS: Os 3 comandos são a mesma coisa:

# RUN: executa durante o build
# RUN ["python", "hello.py"]

# CMD podemos mudar o ENTRYPOINT não. (Quando subimos essa imagem como container, o CMD ele é apenas uma dica para oque vai executar. Podemos trocar o comando do CMD na hora de dar docker run).
#Podemos usar os dois juntos: o meu entrypoint vai ser sempre python e caso o cmd não seje passado sera hello.py
  #  ENTRYPOINT ["python"]
  #  CMD ["hello.py"]


# ENTRYPOINT: Indica qual é o comando que vai ser executado
# ENTRYPOINT ["python", "hello.py"]


# CMD: executa o comando quando quando a imagem vira um container
#OBS: Se eu não passar o comando, o docker vai utilizar a sugestão que estou passando no cmd
CMD ["python", "hello.py"]



# Construção da imagem:
#RODAR O COMANDO NO TERMINAL:
  # docker build . -t ex03
  # docker run ex03
  # docker run ex03 python hello.py
  # docker run ex03 python hello2.py
    # CMD é rudo depois do docker run
  #OU
  # docker run --rm ex03
  # docker run --rm ex03 python hello.py
  # docker run --rm ex03 python hello2.py
  # docker start -a nomeDoContainer
