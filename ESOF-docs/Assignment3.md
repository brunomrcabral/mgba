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

##Logical View

No seguinte diagrama de packages encontram-se esquematizadas as principais abstrações do sistema, a separação das várias camadas da aplicação e as dependências entre packages que caracterizam a vista lógica do projeto em estudo.

![](Assignment3/logical-view.png)

Após análise cuidada do código disponibilizado no repositório pela equipa deste projeto, foi possível verificar que este é constuitído por seis pacotes que definem a organização e estrutura do projeto.

O pacote "gba" é responsável por implementar uma máquina virtual no host que serve como base na simulação do comportamento do hardware original da consola Game Boy Advance. Emulação do hardware e BIOS originais, dispositivos de entrada/saída (teclado, rato, comando), serialização  (possibilidade de carregar e guardar o estado da máquina virtual)...

O pacote "arm" implementa recompilação dinâmica de instruções de processadores da família ARM7.
O recompilador dinâmico é responsável pela leitura do programa ou código máquina da plataforma a ser emulada e pela produção de código máquina nativo da plataforma ou arquitetura onde esta corre.

O pacote "platform" contém frameworks e APIs (application programming interfaces) de terceiros específicas para cada plataforma e sistema operativo, necessárias para a criação de interfaces gráficas de utilizador e acesso a di

O package "third-party" contém bibliotecas de terceiros (third-party) independentes da plataforma necessárias ao funcionamento do software. Estas bibliotecas normalmente são open-source e acrescentam funcionalidades extra à aplicação.
- [blip_buf](https://code.google.com/p/blip-buf/) **:** *Blip_buf is a small waveform synthesis library meant for use in classic video game sound chip emulation. It greatly simplifies sound chip emulation code by handling all the details of resampling. The emulator merely sets the input clock rate and output sample rate, adds waveforms by specifying the clock times where their amplitude changes, then reads the resulting output samples.*
- [inih](https://github.com/benhoyt/inih) **:** *a simple .INI file parser written in C. It's only a couple of pages of code, and it was designed to be small and simple, so it's good for embedded systems.*
- [libpng](http://www.libpng.org/pub/png/libpng.html) **:** *The libpng package contains a library of functions para criação e manipulação de ficheiros de imagem no formato PNG (Portable Network Graphics). PNG is a bit-mapped graphics format similar to the GIF format. PNG was created to replace the GIF format, since GIF uses a patented data compression algorithm.*
- [lzma](http://www.7-zip.org/sdk.html) **:** biblioteca multi-plataforma de compressão de dados que implementa o algoritmo LZMA desenvolvido por *Igor Pavlov*, também conhecido como *Lempel-Ziv-Markov chain algorithm*.
- [zlib](http://www.zlib.net) **:** biblioteca multi-plataforma de compressão de dados escrita por Jean-Loup Gailly e Mark Adler, baseada no algoritmo DEFLATE

O package "debugger" implementa as funcionalidades de debugging na interface em linha de comandos (CLI), bem como uma interface da aplicação com gdb (GCC Debugger).

O package "util" contém algumas dependências e estruturas de dados comuns utilizadas pelos outros packages.
