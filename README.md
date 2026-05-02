
# Manual de instalação UEFI do arch-linux + Gnome puro + systemd-boot [PT_BR]
Testei diversas distros Linux, especialmente as mais populares (Arch, Mint, Fedora, Ubuntu e Debian), e cheguei à conclusão que essa combinação foi a melhor para o meu uso cotidiano com melhor suporte ativo da comunidade, boa compatibilidade com pacotes de aplicativos e com maior liberdade de personalização, basicamente tudo que serve pra outras distros, serve aqui também e algumas vezes até mais fácil ainda de ser feito. E acima de tudo, que contenha apenas o obrigatório para o sistema funcionar, mas sempre deixando a possibilidade de instalar qualquer coisa que eu precisar futuramente.
<details>  

### Por quê o Arch-Linux?
Ele é baseado no Debian que é uma das primeiras distros baseadas em Linux, a qual eu percebi que tem uma variedade de pacotes e de suporte muito grande comparado com outras distros. E possui uma comunidade ativa que te ensina a fazer qualquer tipo de coisa nele, além da [ArchWiki](https://wiki.archlinux.org/) que parece uma Bíblia de tão completa e sempre atualizada. 

- Por quê não instalar o Debian então?

Diferente do Debian, o Arch tem um ambiente puro, sem GUI (interface) integrada na instalação. Além de não possuir aplicativos nativos, algo que testei no Fedora e gostei muito! Você tem um sistema limpo onde remove até a tela do Terminal Kernel se quiser. 
Resumindo, se eu não uso algo, então não preciso daquilo ocupando o armazenamento do meu computador.

### Por quê o Gnome?
Quando testei as interfaces gráficas Gnome, KDE Plasma e Cinnamon. Tentei fazer a mesma aparência nelas, modificar ao ponto de ficar idêntica ao Mac Tahoe (Que acho a interface mais bonita até o momento), e um pouco mais intuitiva por lembrar o smartphone que é algo que usamos durante o dia inteiro, então pegar o computador não causa a sensação de "OK... Agora estamos no computador aqui é tudo diferente". ISSO NÃO FAZ SENTIDO!!! Meu cérebro quer continuar no mesmo fluxo sem essas "readaptações" ao longo do dia. 

- No KDE Plasma...
  Achei bem prático a função de clicar em personalizar e sair arrastando as coisas pela tela, incluindo ícones, baixar e aplicar temas direto das configurações de aparência. Mas... Isso é extremamente limitado, o KDE é feito para funcionar como KDE, ponto final. 

- O Cinnamon...
É semelhante ao KDE nesse sentido, mas achei ainda mais limitado, pela falta de opções disponíveis e pela pouca variedade de coisas feitas pela comunidade.

Além disso tudo, tem mais um ponto muito importante. No Cinnamon e no KDE a interface às vezes é mais do tipo "apontar e clicar" muito idêntico ao Windows. Não há atalhos de navegação com gestos no touchpad, e até os atalhos de teclas para as janelas de aplicativo são bem limitados.

Ok, isso até poderia ser modificado com diversas tentativas até conseguir o resultado esperado, mas isso levaria tempo, e MUITA disposição. Coisa que pra mim  NÃO FAZ SENTIDO!
A vida é curta de mais pra gastar tentando apenas mudar a configuração do meu computador!

- E sobre o Gnome?  

Parti do mesmo princípio usado para a escolha do Arch: Tudo que é mais antigo tem mais conteúdo na comunidade e mais coisas desenvolvidas, testadas e estáveis.

No Gnome achei muito mais intuitiva a função de arrastar com três dedos no touchpad do notebook. Para os lados, ele muda a área de trabalho, geralmente deixo as janelas maximizadas e uso como se estivesse apenas pulando de um aplicativo pra outro, igual no iPhone ou outros smartphones com a função de deslizar entre aplicativos.  
Arrastando de baixo pra cima, ele mostra a lista com todos os aplicativos que inclusive é idêntica ao MacOS, e ao menu dos smartphones com Android.

Além disso, ele tem um site de extensões excelentes, quase todas estáveis e sem bugs, criadas e testadas pela comunidade de usuários, com direito a feedback nos comentários.  
Então acredite quando eu digo que tem tudo que você imaginar de funções, pra deixar o Gnome do seu jeito, só instalando uma extensão e configurando no menu próprio dela pra fazer algum ajuste fino, se quiser, pode também clicar no link e ir direto pro Git de cada uma delas e ver como ajustar.  
E se por acaso alguma extensão não for compatível, você simplesmente desativa a verificação de versão no site e instala ela mesmo assim (geralmente elas funcionam sem problemas).  
Já o gerenciamento de todas as extensões pode ser feito direto pelo site via navegador, ou pelo aplicativo de gerenciamento de extensões instalado no sistema. Isso é algo excelente!

### Por quê o Systemd-boot?
A maioria dos tutoriais que eu vi, falam de instalar o Grub como Bootloader, mas eu acho um desperdício. Porque o Arch já vem com um bootloader integrado, especialmente para quem usa UEFI que é o meu caso. Além disso, testando, eu também achei mais rápido iniciar com o Systemd-boot em vez do Grub.

### Dito tudo isso... Segue o manual de instalação abaixo.
</details>

# 1 Pré-instalação
O processo pode ser feito seguindo o (Manual da ArchWiki)[https://wiki.archlinux.org/title/Installation_guide]. Mas prefiro seguir este método de instalação, para deixar ele já configurado e evitar várias etapas da pós instalação. 

## 1.1 Baixar uma imagem de instalação

Fazer o [Download do Arch-Linux](https://archlinux.org/download/) via Magnet Link ou Torrent.

## 1.2 Preparar a mídia de instalação (Pendrive ou HD)

Pode usar o [Rufus](https://rufus.ie), [Ventoy](https://www.ventoy.net/en/download.html), [Balena Etcher](https://etcher.balena.io/#download-etcher) ou o [Easy2Boot](https://easy2boot.xyz/download/) (uso esse). Caso for um Mr. Robot na vida, é só usar um desses [outros métodos](https://wiki.archlinux.org/title/USB_flash_installation_medium). 

Feito isso, já pode ligar pressionando `DEL`, `ESC`, `F2`, `F4`, `F10`, `F12` ou alguma outra tecla, depende do equipamento. O importante é iniciar pelo USB no computador que vai ser instalado.
> A Bios da placa-mãe precisa estar com o `Secure Mode` desativado e o `UEFI Boot` habilitado. No menu de boot, tem que inciar pela opção que tem UEFI no nome.

Depois que iniciar ele vai mostrar "Welcome to Arch-Linux" e depois subir uma pá de letras. Quando parar, vai ter um trecho assim:  
`root@archiso~#`  

Daqui em diante é escrever comandos, imaginar como se fosse uma conversa com um bot de atendimento do delivery de comida e estou apenas digitando as opções do pedido.  

## 1.3 Definir o layout do teclado

No Brasil se usa dois tipos de teclado ABNT. No Macbook a posição das teclas é meio diferente, mas funciona igual.  

ABNT (teclados que **não tem** a tecla `AltGr` à direita da barra de espaço e tem no máximo dois caracteres na mesma tecla) 
```
loadkeys br-abnt   
```
ABNT2 (teclados que **tem** a tecla `AltGr` à direita da barra de espaço e tem três caracteres na mesma tecla, por exemplo `+ = §`).
```
loadkeys br-abnt2   
```
Se não escolher o correto, algumas teclas ficam digitando errado e isso vai atrapalhar. Esse comando mostra a lista de todos os layouts de teclado, caso precisar de um diferente.
``` 
localectl list-keymaps
```
<details>  

## 1.4 Verificar o modo de boot

Pra saber se vai dar certo nesse computador tem que digitar
```
cat /sys/firmware/efi/fw_platform_size
```
>- Se o comando retornar `64` ou `32`, o sistema será inicializado no modo UEFI e terá um UEFI x64 de 64 bits, ou UEFI IA32 de 32 bits.
>  Ambos funcionam com Systemd-boot e vai dar certo.
>- Se retornar `No such file or directory`, o sistema pode ter inicializado no modo BIOS (ou CSM) em vez de UEFI.
>  Nesse caso, tem que confirmar se a placa-mãe tem suporte a UEFI e se tá habilitado, se não tiver suporte, vai ter que usar o GRUB em vez do Systemd-boot.
</details>

## 1.5 Conectar na internet

É obrigatório ter internet pra instalar o Arch-linux, porque ele só contém o básico do terminal Kernel na imagem de instalação, todos os aplicativos e interface gráfica é baixado de acordo com a escolha do usuário.  
- Conexão Ethernet, via cabo  
Se for uma conexão LAN pelo cabo de rede, é só confirmar se está habilitado
```
ip link
```
Se estiver `Enable` então já deve estar funcionando, pra testar é só dar um comando de ping.
```
ping google.com
```
- Conexão Wireless, via Wi-Fi  
Se for uma conexão via Wi-Fi, então use o comando pra entrar no menu de configuração de wi-fi
```
iwctl
```
<details>
  
Esse é o comando pra listar as placas de rede e saber o nome do dispositivo pra usar na próxima etapa
> Se for um notebook com Wi-Fi integrado ou se o computador tiver apenas uma placa de rede Wi-Fi, o nome do dispositivo vai ser `wlan0`, então dá até pra pular essa parte.
```
device list
```
> (Vou considerar que o nome do dispositivo seja `wlan0`, porque é esse na maioria dos casos)

Pra buscar as redes disponíveis
> Se souber o nome exato da rede Wi-Fi (incluindo maiúsculas/minúsculas e pontuações), também pode pular essa parte.
```
station wlan0 scan
```
</details>

Selecionar o dispositivo de Wi-Fi e conectar na rede  
> No meu caso eu conectei na que estava disponível aqui, tem que ser o nome exato incluindo espaços e até quando tem `2.4` ou `_5G` no final.
```
station wlan0 connect Internet do vizinho_5G
```
Aqui ele vai pedir a `passphrase` que é a senha, é só digitar. Se em até 10 segundos não mostrar uma mensagem de erro. É porque funcionou!

> Dá pra testar usando o comando de ping.

## 1.6 Definir Hora e Data pela rede
Essa etapa é opcional, nunca tive problemas, mas é melhor fazer ela só pra evitar problemas relacionado a baixar pacotes por causa da diferença na data e hora do sistema comparado aos servidores.

```
timedatectl set-ntp true
```
<details>
  
# 2 Particionar, formatar e montar as partições

Só pra esclarecer como funciona isso.  
- Primeiro tem que criar a partição, que é avisar pro sistema quanto espaço do disco pode ser usado pra cada partição criada, já que o disco tem escrita dinâmica então ele tá sempre gravando em setores diferentes mas sempre mantem a proporção de espaço pra cada partição. E também avisar pro sistema que tipo de partição é cada uma, pra ele saber onde provavelmente vai ficar o EFI do Boot.  
- Depois tem que formatar as partições pra definir o formato de arquivo, nesse caso vai ser só dois: Fat32 e Btrfs.  
- Por último tem que montar os diretórios de pasta, dentro das partições, pra poder gravar cada coisa no lugar certo durante a instalação.  
</details>

## 2.1 Particionar o disco antes de formatar

Pra saber qual é o dispositivo, tem que usar o comando pra listar todas as unidades e descobrir pelo tipo ou pelo tamanho, o ideal é deixar conectado só o disco que vai ser formatado e a mídia de instalação, pra não apagar o disco errado por engano.
```
lsblk
```
<details>

> Na instalação do sistema, ele entende as unidades de disco como caminhos `/dev/ ...`  e usa abreviações como `sda` pra disco Sata, `nvme0n1` pra NVME e `vda` pra disco virtual. Ex: `/dev/sda`  
> Quando tem mais de um disco do mesmo tipo, eles ficam com as abreviações diferentes em sequência alfabética ou numérica:  
> `sda`, `sdb`, `sdc` ...  `nvme0n1`, `nvme0n2`, `nvme0n3` ... `vda`, `vdb`, `vdc`  
> Nomes de disco com `rom`, `loop` or `airootfs`. ou cartões de memória removíveis com `rpmb`, `boot0` and `boot1` podem ser ignorados.
</details>

Nos exemplos vou considerar que seja pra particionar o primeiro disco Sata.
```
fdisk /dev/sda
```
Quando abrir o menu de partição é só usar o comando `d` e `Enter` pra ir apagando as partições que já existam no disco até retornar  
`No partition is defined yet!`  

Usar o comando `g` (minúsculo) pra criar a tabela de partição em GPT.

### Criar a 1ª partição `/dev/sda1` <sup>(Boot, só serve pra iniciar o sistema)</sup>
> Sda1, 1Gb, UEFI

- Comando `n` pra criar uma nova partição
- Escolher um número pra identificar a partição: `1`
- Vai ser sugerido um setor inicial, é só pressionar `Enter`
- Vai perguntar o setor final, tem que colocar quanto vai ser somado no tamanho da partição e a unidade de medida, tudo junto: `+1g`
- digitar `t` pra definir o tipo de partição, pro sistema saber pra que ela vai ser usada depois: `1`
> Pra ver o número da opção de cada tipo de partição é só usar o comando `l` e depois `q` pra voltar

### Criar a 2ª partição `/dev/sda2` <sup>(Root, onde fica os arquivos do sistema e do usuário)</sup>
> Sda2, +espaço pra guardar os arquivos, Linux File System

- Comando `n` pra criar uma nova partição
- Escolher um número pra identificar a partição: `2`
- Vai ser sugerido um setor inicial, é só pressionar `Enter`
- Vai perguntar o setor final, pode digitar um tamanho igual feito antes. Ou, pra usar o disco todo é só pressionar `Enter` 
- digitar `t` pra definir o tipo de partição, pro sistema saber pra que ela vai ser usada depois: `20`  
> Pra ver o número da opção de cada tipo de partição é só usar o comando `l` e depois `q` pra voltar

Salvar usando `w` e `Enter`  

<details> 

- Usar o comando abaixo pra ver se o tamanho e o tipo das partições ficou certo
```
lsblk
```

<img width="452" height="112" alt="image" src="https://github.com/user-attachments/assets/cf3b7796-16d7-40db-a80b-5ffec70eaff3" />

> Aqui ficou como 1gb na partição boot, e 19gb na partição root
</details>

## 2.2 Formatar o disco
É só definir qual é o formato do sistema de arquivo em cada partição

- Partição boot
```
mkfs.fat -F32 /dev/sda1 
```

- Partição root
```
mkfs.btrfs /dev/sda2
```
<details> 

- Usar o comando abaixo pra ver se o formato do sistema de arquivo ficou certo em cada partição
```
lsblk -f
```

<img width="980" height="112" alt="image" src="https://github.com/user-attachments/assets/2acf2a0d-b074-4b4d-ab5f-ebc2bf2a9dcd" />

> Partição sda1: EFI, vFAT (FAT32)
> Partição sda2: btrfs
</details>

## 2.3 Criar os pontos de montagem
Apontar pro sistema em qual diretório de pasta vai ficar o Boot e onde é o Root

- Pra montar o root tem que usar o comando
```
mount /dev/sda2 /mnt
```

- Pra montar o boot tem que usar o comando
```
mount --mkdir /dev/sda1 /mnt/boot
```

<details> 

- Usar o comando abaixo pra ver se o `mountpoints` das partições ficou certo
```
lsblk -f
```

<img width="951" height="114" alt="image" src="https://github.com/user-attachments/assets/24d1264c-1fa5-4390-af72-df36844ea1eb" />

> Partição sda1: EFI, vFAT (FAT32), /mnt/Boot
> Partição sda2: btrfs, /mnt
</details>

# 3 Instalação, finalmente!
O Arch é igual um Lego, tem que ir montando cada parte dele durante a instalação

## 3.1 Instalar os pacotes básicos
Esse comando baixa e salva no root: o pacote mínimo base pra instalação do sistema; um editor de texto via terminal; o kernel com módulos Linux; Firmware pra o funcionamento do hardware (drivers básicos). 
```
 pacstrap /mnt base nano linux linux-firmware
```

## 3.2 Gerar o a tabela de partições 
Para o sistema salvar a lista das partições criadas é preciso gerar o arquivo `fstab` usando o comando:
```
genfstab -U /mnt >> /mnt/etc/fstab
```
> Percebi que algumas vezes o sistema não lista todas as partições, então é bom usar o comando abaixo, pra confirmar se já contém todas, ou vai ser preciso repetir o processo.
```
cat /mnt/etc/fstab
```
<details> 

## 3.3 Criando uma partição de swap <sup>(Opcional)</sup> 
O Linux pode simular uma extensão de memória RAM usando uma parte do disco de armazenamento, igual os dispositivos da Xiaomi. Pra ativar é preciso criar uma `partição swap`.  

- Começar entrando no modo de gerenciamento root do disco
```
arch-chroot /mnt
```
- Depois alocar, separando uma parte do armazenamento e criando um diretório
```
fallocate -l 4GB /swapfile
```
- Dar as permissões necessárias para o diretório criado
```
chmod 600 /swapfile
```
- Definir o diretório pro formato swap
```
mkswap /swapfile
```
- Ativar o diretório para o Swap
```
swapon /swapfile
```
- Adicionar o diretório na lista de partições
```
nano /mnt/etc/fstab
```
Usar a seta pra ir até a ultima linha em branco e digitar 

```
/swapfile none swap defaults 0 0 
```
Usar `CTRL`+`O` pra salvar e `Enter` pra confirmar. `CTRL`+`X` pra fechar.
</details>

3.4 Criar 
```
fallocate -l 4GB /swapfile
```
```
fallocate -l 4GB /swapfile
```
```
fallocate -l 4GB /swapfile
```
```
fallocate -l 4GB /swapfile
```
























## 1.7 Definir o idioma para pt_BR
Abrir o arquivo modelo de configuração com o editor de texto via terminal
```
nano /etc/locale.gen
```
Descer com a seta e descomentar (apagar o `#` da frente) na linha escrito `pt_BR.UTF-8 UTF-8` e `pt_BR ISO-8859-1`. 

Usar `CTRL`+`O` pra salvar e `Enter` pra confirmar. `CTRL`+`X` pra fechar.

Gerar o arquivo de idioma
```
locale-gen
```













