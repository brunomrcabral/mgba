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

Como última entrega do projeto desenvolvido durante este semestre na unidade curricular de Engenharia de Software foi-nos pedida a identificação e implementação de uma nova funcionalidade ou evolução de uma existente no projeto escolhido (mGBA). Com este relatório o grupo pretende apresentar a *feature* implementada e reflectir sobre o seu **processo de desenvolvimento**.

O termo *software evolution* é frequentemente utilizado em Engenharia de *Software* para designar o processo de desenvolvimento inicial de *software*, seguido de constantes alterações ao sistema previamente implementado com vista a satisfazer determinadas necessidades ou requisitos.

A evolução do *software* é um processo inevitável para qualquer *developer* ou empresa de *software*: todos os dias são encontradas novas imperfeições e *issues* com a utilização das soluções de *software* desenvolvidas por estes que devem ser corrigiaos, todos os dias surgem novos **requisitos**, uma necessidade constante de **evoluir** e tornar o *software* reutilizável, optimizando-o e adaptando-o a novas metodologias de trabalho e à constante evolução dos sistemas informáticos, nunca esquecendo eventuais melhorias na **segurança** e **fiabilidade** do sistema, evitando o aparecimento de **vulnerabilidades** que possam comprometer a integridade da máquina ou dos dados nele utilizados.

##Identificação da *feature*

O repositório do projeto disponibiliza uma secção de *issues* onde os vários **contribuidores** e **utilizadores** da aplicação expõem frequentemente os *bugs* encontrados durante a sua utilização e sugerem uma série de funcionalidades que gostavam de ver implementadas no decorrer do desenvolvimento do projeto. Após uma análise desta secção, o grupo decidiu evoluir a *feature* referenciada nos *issues* [#179](https://github.com/mgba-emu/mgba/issues/179) *[Request] screen rotation*, [#162](https://github.com/mgba-emu/mgba/issues/162) *[Request] Tilt the game 'screen' along with the tilt value* que dizem respeito à implementação de uma funcionalidade que permitisse a rotação da imagem produzida pela aplicação.

Para tal acrescentamos um novo sub-menu no menu "Audio/Video" da *interface* gráfica designado "Rotate screen" (inserindo algumas linhas no método responsável pela construção dos menus), consituído por quatro opções: None (sem rotação), 90º CW (rotação de 90 graus no sentido horário), 90º CCW (rotação de 90 graus no sentido anti-horário) e 180º (rotação de 180 graus). Verificámos que esta opção ficava guardada entre sessões num ficheiro de configuração criado pela aplicação, e sempre que voltávamos a abrir a aplicação, as nossas preferências eram lembradas e a imagem aparecia rodada tal e qual como a tínhamos deixado na última utilização.

##Identificação das componentes

Para a implementação desta *feature* foi necessário alterar parte das componentes da interface gráfica em [platform](https://github.com/mgba-emu/mgba/tree/master/src/platform/qt), nomeadamente as classes [Window](https://github.com/mgba-emu/mgba/blob/master/src/platform/qt/Window.cpp), [Display](https://github.com/mgba-emu/mgba/blob/master/src/platform/qt/Display.cpp), [DisplayGL](https://github.com/mgba-emu/mgba/blob/master/src/platform/qt/DisplayGL.cpp).

##Submissão do *patch*

Após a sua implementação, a nossa *feature* foi sujeita a um pedido de *pull request* com vista a ser integrada no *branch* principal do repositório do **mGBA**.

##Análise crítica

O grupo considera que a **má organização** do repositório e a **ausência de documentação** no código fonte do projeto dificultou a realização da tarefa proposta para esta entrega. Numa fase inicial não fazíamos ideia por onde devíamos começar a realizar as alterações no projeto com vista a implementar a *feature* escolhida, pois a distinção entre a camada que implementa a **máquina virtual** e a camada da **interface gráfica** revelou não ser tão óbvia como o grupo achava inicialmente, embora as classes e responsabilidades tivessem sido separada pelo autor do projeto e colocadas em diretórios diferentes.

A contribuir ainda mais para o aumento da **dificuldade** desta tarefa, não encontramos nenhuma aplicação capaz de realizar **engenharia reversa** no código gerado pelo editor de *interfaces* gráficas da *framework* Qt, o que reduziu de uma maneira geral a produtividade do grupo. As próprias *frameworks* utilizadas (*OpenGL*, *SDL*, *Qt*, ...) revelaram-se bastante **complexas** e **confusas**, com uma extensa documentação disponível online e um **grau de aprendizagem** relativamente elevado.
