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

##Gestão de Requisitos

Os conceitos abordados nas aulas teóricas dizem respeito a projetos de software comercial. No entanto, estes conceitos não se aplicam na totalidade a um projeto comunitário sem fins lucrativos fundamentado no *open-source*, tal como este aqui abordado.

Existem dois tipos de requisitos em engenharia de *software*:
- requisitos funcionais - descrevem as funcionalidades que o produto final deve ter (também chamados de "capacidades")
- requisitos não-funcionais are the ones that act to constrain the solution

###Levantamento de Requisitos

Apesar de estar a ser marioritariamente desenvolvido pelo seu proprietário, o mGBA depende também dos seus *main contributors* que submetem *pull requests* com as suas ideias e dos seus *stakeholders*, isto é, das pessoas que têm influência na elaboração dos requisitos. No contexto deste projeto, os *stakeholders* representam um público alvo mais específico, com conhecimentos básicos nesta área, a comunidade de *retro gaming*, pois são sobretudo estes que contribuem para a melhoria da qualidade global do *software*.

No contexto dos emuladores como o mGBA, ter qualidade significa ser capaz de garantir a compatibilidade com a maior parte do *software* e dos periférios lançados para o dispositivo a ser emulado. São os stakeholders que vão dando conta de eventuais *bugs* na aplicação, que se mostram exigentes e insatisfeitos pelas imperfeições no resultado obtido e propõem novas funcionalidades para complementarem a sua experiência de utilização deste *software*.

O próprio autor definiu alguns destes objetivos aquando o início do desenvolvimento deste projeto, após uma análise por comparação com outros emuladores *open-source* e comerciais disponíveis na *Internet*, tendo a comunidade contribuido com os restantes e mais variados requisitos ao longo dos últimos meses. Estas novas funcionalidades que foram requisitadas são as que estão habitualmente presentes em *software* do mesmo género, conferindo características que distingue este de *software* equivalente. Entre os requisitos enunciados pelo autor no documento README presente na raiz deste repositório, destacam-se os seguintes, todos eles conseguidos até ao momento de elaboração deste relatório:

- compatibilidade com grande parte dos periféricos e jogos da Game Boy Advance
- emulação rápida, capaz de executar em tempo real mesmo em computadores e dispositivos com características inferiores
- ports para outras plataformas recorrendo a *frameworks* como Qt/SDL
- *frameskipping* configurável
- suporte a *screenshots* (capturas de ecrã) e *cheat codes*
- suporte a *savestates* e visualização dos mesmos na *interface* gráfica do utilizador
- gravação de vídeos
- possibilidade de mapear os botões em qualquer dispositivo de entrada ligado ao computador
- suporte a leitura de ficheiros nos formatos ZIP e 7Zip
- suporte a *patches* IPS, UPS e BPS
- suporte a debugging recorrendo a uma *interface* em linha de comandos

No entanto existem alguns em aberto, à espera de serem implementados:
- suporte a *multiplayer* em rede utilizando um link cable emulado
- suporte à linguagem de *scripting* Lua
- ferramentas de *debugging* mais completas

### Especificação de Requisitos

####Bugs/Issues
No repositório existe também uma secção de issues bastante ativa, com utilizadores e *contributors* a submeter relatórios de bugs todas as semanas devidamente acompanhados por uma pequena mensagem a descrever o problema e por vezes uma imagem ou captura de ecrã ilustrando a situação descrita.

####Novas funcionalidadaes
O utilizador com a intenção de contribuir deverá fazer um fork ou um branch do repositório na sua versão atual, e após realizar alterações significantes no código, pedir ao proprietário que as incorpore no branch principal, através de um pull request. No momento do pull request será também necessário indicar qual a finalidade daquele código, ou seja, qual o componente que foi implementado ou melhorado, bem como um parágrafo sucinto onde explique essas alterações.

###Validação de Requisitos

As alterações submetidas pelos utilizadores estão sujeitas a um processo de validação manual pelo proprietário deste projeto antes de serem aprovadas. Estas alterações devem ser pertinentes, não causar problemas nem perturbações no funcionamento do programa nem regressões nos testes e/o compatibilidade do *software*. Não há muitas informações disponíveis publicamente quanto aos processos utilizados e a frequência com que esses testes são realizados.

Motivação: Os requisitos apresentados são marioritamente funcionais e representam funcionalidades secundárias que apenas melhoram a experiência do utilizador.

O proprietário enumera uma série de ... : serão apenas aceites se o código estiver devidamente formatado e organizado segundo uma determinada nomenclatura e estilo de código que devem ser obedecidos (também definidas pelo proprietário no documento). 
