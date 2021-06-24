# Instalação, remoção e gerenciamento de pacotes no Debian
## Principais comandos do APT
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

## Limpeza de pacotes em disco
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