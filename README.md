# Fundamentos de Design de Sistemas

## Sistema Operacional Linux

### Estrutura de diretórios
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

### Instalação, remoção e gerenciamento de Pacotes no Debian
É possível instalar, remover e atualizar programas no sistema Linux por linha de comando ou por meio da loja virtual que se encontra no SO, dependendo de qual distro Linux, no caso de qualquer distro baseada no Debian é importante se atentar na extensão **.deb** .O Ubuntu, por exemplo, tem uma loja e se utiliza do APT como ferramenta para gerenciar os pacotes que podem ser instalados e removidos pelo usuário.
Portanto, há dois meios de se instalar softwares, por meio do repositório oficial ou através da própria empresa que distribui. Desse modo, vamos aos principais comandos para tal objetivo:
1. Primeiramente, verifique sempre se existe algum pacote novo atualizado para ser baixado antes de instalar qualquer programa:
```
sudo apt update
```
2. Caso queira procurar um programa específico, execute:
```
sudo apt search <nome-do-pacote>
```
3. Encontrando o programa, agora é só instalar:
```
sudo apt install <nome-do-pacote>
```
4. Removendo o programa por outro lado:
```
sudo apt remove <nome-do-pacote>
```
5. E se quiser atualizar todos os programas de seu sistema, execute:
```
sudo apt upgrade
```
Agora aqui são dicas para gerenciar o armazenamento de tais pacotes no seu PC, nunca deixe de fazer uma faxina em tais arquivos, pois há grandes possibilidades de se enfrentar falta de espaço em disco para qualquer coisa. Por isso é bom aprender alguns comandos.
* Cache do APT

O APT tem um cache com todos os programas que foram instalados, mesmo aqueles que foram removidos por você continuarão lá se nada for feito. Por isso é um local que fica acumulando dados sem necessidade. O cache do apt se encontra no caminho **/var/cache/apt**. Tem como ver o tamanho que ocupa com o comando abaixo:
```
sudo du -sh /var/cache/apt
```
Então, é possível remover somente os pacotes desatualizados ou totalmente essa pasta com os seguintes comandos respectivamente:
```
sudo apt-get autoclean
sudo apt-get clean
```
* Pacotes baixados automaticamente como dependências

Esse é um caso onde um programa precisa de outros pacotes como dependentes para então ser executado. São libs por exemplo. Nesse caso, um comando ajuda a remover tanto tais pacotes como versões antigas do Kernel do Linux.
```
sudo apt autoremove
```
* Utilize o comando abaixo como atalho para remover todo pacote desatualizado:
```
sudo apt autoremove && sudo apt autoclean
```
