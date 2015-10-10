```
  _____        _         _     __         _        
 |  __ \      | |       | |   /_/        (_)       
 | |__) | ___ | |  __ _ | |_  ___   _ __  _   ___  
 |  _  / / _ \| | / _` || __|/ _ \ | '__|| | / _ \ 
 | | \ \|  __/| || (_| || |_| (_) || |   | || (_) |
 |_|  \_\\___||_| \__,_| \__|\___/ |_|   |_| \___/ 
 ```
##Engenharia de Software - 2015/2016
:floppy_disk:  *Mestrado Integrado em Engenharia Informática e Computação*   :floppy_disk:

Faculdade de Engenharia da Universidade do Porto

###Grupo
* Carlos Jorge Rocha Soares (up201305514@fe.up.pt)
* Carlos Manuel Carvalho Boavista Samouco (up201305187@fe.up.pt)
* Diogo Belarmino Coelho Marques (up201305642@fe.up.pt)

###Gestão de Requisitos

Os conceitos estudados nas aulas teóricas dizem respeito a projetos de software comercial. Nesse sentido, esses conceitos aplicam-se apenas em parte a um projeto comunitário e sem fins lucrativos fundamentado no *open-source*



###Levantamento de Requisitos

Apesar de estar a ser marioritariamente desenvolvido pelo proprietário do projeto, o mGBA é bastante dependente dos seus contributors e da comunidade de *retro gaming*, pois são sobretudo estes que contribuem para uma melhoria do projeto e da compatibilidade com os vários jogos lançados para esta consola, dando conta de *bugs*, imperfeições no resultado da emulação e propondo novas funcionalidades.

O próprio autor definiu alguns destes objetivos no início do projeto, tendo a comunidade contribuido com os restantes. Estes objetivos e funcionalides estão habitualmente presentes e são amplamente utilizados em *software* do mesmo género. Entre os requisitos enumerados pelo autor no documento README.md, destacam-se os seguintes, todos eles realizados até à data de elaboração deste relatório:

- compatibilidade com a maioria dos periféricos e jogos da Game Boy Advance
- emulação rápida, capaz de executar em tempo real mesmo em computadores e dispositivos com características inferiores
- ports para outros sistemas operativos e plataformas recorrendo a frameworks como Qt/SDL
- frameskipping configurável
- suporte a *screenshots* (capturas de ecrã) e *cheat codes*
- suporte a *savestates* e visualização dos mesmos na *interface* gráfica do utilizador
- gravação de vídeos e GIFs animados
- possibilidade de mapear os botões em qualquer dispositivo de entrada ligado ao computador
- suporte a leitura de ficheiros comprimidos nos formatos ZIP e 7Zip
- suporte a *patches* IPS, UPS e BPS
- suporte a debugging recorrendo a uma *interface* em linha de comandos

Os requisitos que se encontram ainda em aberto são:
- suporte a comunicações em rede utilizando um link cable emulado
- suporte à linguagem de *scripting* Lua
- uma suite de *debugging* mais completa

###Validação de Requisitos
