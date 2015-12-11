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

##Introdução

Como última entrega do projeto desenvolvido durante este semestre na unidade curricular de **Engenharia de Software** foi-nos pedida a identificação e **implementação** de uma nova funcionalidade no projeto escolhido (mGBA) ou **evolução** de uma existente. Com este relatório o grupo pretende apresentar a *feature* implementada e reflectir sobre o seu **processo de desenvolvimento**.

O termo *software evolution* é frequentemente utilizado em Engenharia de *Software* para designar o processo de desenvolvimento inicial de *software*, seguido de constantes alterações ao sistema previamente implementado com vista a satisfazer determinadas necessidades ou requisitos. A evolução do *software* é um processo inevitável a qualquer *developer*: todos os dias são encontrados novos erros com a utilização do *software* que devem ser corrigidos e surgem novos requisitos, novas metodologias de trabalho, necessidade de optimização do seu desempenho e melhorias na segurança e fiabilidade do sistema. 

- **Corrective maintenance**: modificações efetuadas no *software* após o seu lançamento para corrigir problemas que tenham sido descobertos;
- **Adaptive maintenance**: modificações efetuadas no *software* após o seu lançamento para manter o produto reutillizável num ambiente em mudança constante;
- **Perfective maintenance**: modificações efetuadas no *software* após o seu lançamento com vista a melhorar o desempenho e fiabilidade da solução;
- **Preventive maintenance**: modificações efetuadas no *software* após o seu lançamento com vista a detectar e corrigir falhas de segurança e/ou vulnerabilidades antes que estas sejam descobertas e se tornem ameaças efetivas.

##Identificação da *feature*

O repositório do projeto disponibiliza uma secção de *issues* (como já foi referido em entregas anteriores) onde os vários **contribuidores** e **utilizadores** da aplicação relatam habitualmente os *bugs* que encontraram durante a sua utilização e sugerem uma série de funcionalidades que gostavam de ver implementadas no decorrer do desenvolvimento deste projeto. Após uma análise da mesma, o grupo decidiu evoluir a *feature* referenciada pelos issues [#179](https://github.com/mgba-emu/mgba/issues/179) *[Request] screen rotation*, [#162](https://github.com/mgba-emu/mgba/issues/162) *[Request] Tilt the game 'screen' along with the tilt value* que dizem respeito à rotação da imagem de saída produzida pela aplicação.

Para tal acrescentamos um novo sub-menu no menu "Audio/Video" da *interface* gráfica designado "Rotate screen", consituído por quatro opções que o utilizador poderá escolher em qualquer altura durante a emulação: Default (rotação de 0 graus), 90º CW (rotação de 90 graus no sentido horário), 90º CCW (rotação de 90 graus no sentido anti-horário) e 180º (rotação de 180 graus). Tal como as outras opções que constituem este menu, esta também fica guardada entre sessões num ficheiro de configuração criado pela aplicação. Com efeito, sempre que o utilizador abre esta aplicação, as suas preferências são lembradas e a imagem aparece rodada tal e qual a última utilização.

##Identificação das componentes

Para a implementação desta *feature* foi necessário ____

##Submissão do *patch*

Após a sua implementação, a nossa *feature* foi sujeita a um pedido de *pull request* com vista a ser integrada no *branch* principal do projeto em estudo.

##Análise crítica

O grupo considera que a má organização geral do projeto e a falta de documentação no seu código fonte dificultou a realização da tarefa proposta para esta entrega. Numa fase inicial não fazíamos ideia por onde devíamos começar a realizar alterações no projeto, pois a distnção entre a máquina virtual e a camada da *interface* gráfica revelou não ser tão óbvia como o grupo achava inicialmente, embora as classes e responsabilidades tenham sido colocadas pelo autor do projeto em diretórios diferentes. A contribuir para o aumento do grau de dificuldade, não encontramos nenhuma aplicação capaz de realizar engenharia reversa no código gerado pelo editor de *interfaces* gráficas da framework Qt, o que reduziu a produtividade do grupo. A própria framework revelou-se bastante complexa, com uma extensa documentação online e um grau de aprendizagem elevado.
