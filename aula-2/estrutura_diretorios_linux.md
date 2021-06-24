# Sistema Operacional Linux

## Estrutura de diretórios
Diferente do Windows, cuja raiz do sistema é C:\, no Linux é somente / .Nisso, vários diretórios fazem parte do SO para diferentes finalidades. Alguns são resumidos logo abaixo:
* **/home**  é onde ficam os arquivos do usuário logado. Seus arquivos pessoais, programas e relacionados. Antigamente, quem exercicia essa função era a pasta **/usr** , mas que agora é delegada a demais outros arquivos de diversos usuários.
* **/opt** é um diretório opcional para o sistema armazenar qualquer tipo de arquivo, mas que normalmente é utilizado como local de armazenamento de programas.
* **/boot** armazena os arquivos necessários para a inicialização do sistema.
* **/var** guarda dados que crescem muito de volume drásticamente. Por isso é montado em um volume de grande capacidade de armazenamento.
* **/dev** se encontra os volumes e dispositivos montados no sistema, como HDDs e SSDs por exemplo. Então, caso um computador tenha somente um HDD de uma só partição principal, o usuário entraria isso no sistema como /dev/sda1 por exemplo.
* **/bin** fica os binários dos programas instalados no computador.
* **/sbin** também fica os binários, mas dos programas instalados pelo usuário root.
* **/root** é a pasta do usuário root. Somente ele tem acesso.
* **/lib** fica as bibliotecas compartilhadas pelos programas.