<details>  

# Manual de instalação UEFI do arch-linux + Gnome puro + systemd-boot [PT_BR]
Testei diversas distros Linux, especialmente as mais populares (Arch, Mint, Fedora, Ubuntu e Debian), e cheguei à conclusão que essa combinação foi a melhor para o meu uso cotidiano com melhor suporte ativo da comunidade, boa compatibilidade com pacotes de aplicativos e com maior liberdade de personalização, basicamente tudo que serve pra outras distros, serve aqui também e algumas vezes até mais fácil ainda de ser feito. E acima de tudo, que contenha apenas o obrigatório para o sistema funcionar, mas sempre deixando a possibilidade de instalar qualquer coisa que eu precisar futuramente.

## Por quê o Arch-Linux?
Ele é baseado no Debian que é uma das primeiras distros baseadas em Linux, a qual eu percebi que tem uma variedade de pacotes e de suporte muito grande comparado com outras distros. E possui uma comunidade ativa que te ensina a fazer qualquer tipo de coisa nele, além da [ArchWiki](https://wiki.archlinux.org/) que parece uma Bíblia de tão completa e sempre atualizada. 

- Por quê não instalar o Debian então?

Diferente do Debian, o Arch tem um ambiente puro, sem GUI (interface) integrada na instalação. Além de não possuir aplicativos nativos, algo que testei no Fedora e gostei muito! Você tem um sistema limpo onde remove até a tela do Terminal Kernel se quiser. 
Resumindo, se eu não uso algo, então não preciso daquilo ocupando o armazenamento do meu computador.

## Por quê o Gnome?
Quando testei as interfaces gráficas Gnome, KDE Plasma e Cinnamon. Tentei fazer a mesma aparência nelas, modificar ao ponto de ficar idêntica ao Mac Tahoe (Que acho a interface mais bonita até o momento), e um pouco mais intuitiva por lembrar o smartphone que é algo que usamos durante o dia inteiro, então pegar o computador não causa a sensação de "OK... Agora estamos no computador aqui é tudo diferente". ISSO NÃO FAZ SENTIDO!!! Meu cérebro quer continuar no mesmo fluxo sem essas "readaptações" ao longo do dia. 

### No KDE Plasma...
Achei bem prático a função de clicar em personalizar e sair arrastando as coisas pela tela, incluindo ícones, baixar e aplicar temas direto das configurações de aparência. Mas... Isso é extremamente limitado, o KDE é feito para funcionar como KDE, ponto final. 

### O Cinnamon...
É semelhante ao KDE nesse sentido, mas achei ainda mais limitado, pela falta de opções disponíveis e pela pouca variaedade de coisas feitas pela comunidade.

Além disso tudo, tem mais um ponto muito importante, a interface às vezes é mais do tipo "apontar e clicar" muito idêntico ao Windows. Não há atalhos de navegação com gestos no touchpad, e até os atalhos de teclas para as janelas de aplicativo são bem limitados.

Ok, isso até poderia ser modificado com diversas tentativas até conseguir o resultado esperado, mas isso levaria tempo, e MUITA disposição. Coisa que pra mim  NÃO FAZ SENTIDO!
A vida é curta de mais pra gastar tentando apenas mudar a aparência do meu computador!

### E sobre o Gnome? 
Parti do mesmo princípio usado para a escolha do Arch: Tudo que é mais antigo tem mais conteúdo na comunidade e mais coisas desenvolvidas, testadas e estáveis.

No Gnome achei muito mais intuitiva a função de arrastar com três dedos no touchpad do notebook. Para os lados, ele muda a área de trabalho, geralmente deixo as janelas maximizadas e uso como se estivesse apenas pulando de um aplicativo pra outro, igual no iPhone ou outros smartphones com a função de deslizar entre aplicativos.
Arrastando de baixo pra cima, ele mostra a lista com todos os aplicativos que inclusive é idêntica ao MacOS, e ao menu dos smartphones com Android.

Além disso, ele tem um site de extensões excelentes, quase todas estáveis e sem bugs, criadas e testadas pela comunidade de usuários, com direito a feedback nos comentários. Então acredite quando eu digo que tem tudo que você imaginar de funções, pra deixar o Gnome do seu jeito, só instalando uma extensão e configurando no menu próprio dela pra fazer algum ajuste fino, se quiser, pode também clicar no link e ir direto pro Git de cada uma delas e ver como ajustar.
E se por acaso alguma extensão não for compatível, você simplesmente desativa a verificação de versão no site e instala ela mesmo assim (geralmente elas funcionam sem problemas). 
Já o gerenciamento de todas as extensões pode ser feito direto pelo site via navegador, ou pelo aplicativo de gerenciamento de extensões instalado no sistema. Isso é algo excelente!

## Por quê o Systemd-boot?
A maioria dos tutoriais que eu vi, falam de instalar o Grub como Bootloader, mas eu acho um desperdício. Porque o Arch já vem com um bootloader integrado, especialmente para quem usa UEFI que é o meu caso. Além disso, testando eu também achei mais rápido iniciar com o Systemd-boot em vez do Grub.

### Dito tudo isso... Segue o manual de instalação abaixo.
</details>

# Instalando o Arch-Linux
O processo pode ser feito seguindo o (Manual da ArchWiki)[https://wiki.archlinux.org/title/Installation_guide]. Mas recomendo seguir este método de instalação para deixar ele já configurado para o portugês e evitar várias etapas da pós instalação. 

# 1 Pré-instalação
## 1.1 Baixar uma imagem de instalação
Faça o [Download do Arch-Linux](https://archlinux.org/download/) via Magnet Link ou Torrent.

## 1.2 Preparar a mídia de instalação (Pendrive ou HD)
Pode usar o [Rufus](https://rufus.ie), [Ventoy](https://www.ventoy.net/en/download.html), [Balena Etcher](https://etcher.balena.io/#download-etcher) ou o [Easy2Boot](https://easy2boot.xyz/download/) (uso esse). Caso for um Mr. Robot na vida, é só usar um desses [outros métodos](https://wiki.archlinux.org/title/USB_flash_installation_medium). 

Feito isso, já pode ligar pressionando `DEL`, `ESC`, `F2`, `F4`, `F10`, `F12` ou alguma outra tecla, depende do seu equipamento. O importante é iniciar pelo USB no computador que vai ser instalado.  

Depois que iniciar ele vai mostrar "Welcome to Arch-Linux" e depois subir uma pá de letras. Quando parar, vai ter um trecho assim:  
`root@archiso~#`  

Daqui em diante é escrever comandos, imaginar como se fosse uma conversa com um bot de atendimento do delivery de comida e estou apenas digitando as opções do pedido.  

## 1.3 Definir o layout e fonte do teclado do console
Se não escolher o correto algumas teclas ficam digitando errado e vai atrapalhar. Esse comando mostra a lista de todos os layouts de teclado.
``` 
localectl list-keymaps
```
No Brasil se usa dois tipos de teclado ABNT, tem que escolher o certo. Caso seja um Mac a posição das teclas é diferente, mas o princípio é o mesmo. Também é possível remapear as teclas depois de finalizar a instalação e deixar identico aos outros computadores normais.

ABNT (teclados que **não tem** a tecla `AltGr` à direita da barra de espaço e tem no máximo dois caracteres na mesma tecla) 
```
loadkeys br-abnt   
```
ABNT2 (teclados que **tem** a tecla `AltGr` à direita da barra de espaço e tem três caracteres na mesma tecla, por exemplo `+ = §`).
```
loadkeys br-abnt2   
```
<details>  

## 1.4 Verificar o modo de boot  
Pra saber se vai dar certo nesse computador tem que digitar
```
cat /sys/firmware/efi/fw_platform_size
```
>- Se o comando retornar 64, o sistema será inicializado no modo UEFI e terá um UEFI x64 de 64 bits.
>- Se o comando retornar 32, o sistema será inicializado no modo UEFI e terá um UEFI IA32 de 32 bits. Embora isso seja suportado, limitará a escolha do carregador de inicialização àqueles que suportam inicialização em modo misto.
>- Se não retornar tal arquivo ou diretório, o sistema poderá ser inicializado no modo BIOS (ou CSM).
>Se o sistema não inicializou no modo desejado (UEFI ou BIOS), provavelmente a configuração da BIOS tá errada.
</details>

## 1.5 Conectar na internet
Se for uma conexão LAN pelo cabo de rede, é só confirmar se está habilitado
```
ip link
```
Se estiver `Enable` então já deve estar funcionando, pra testar é só dar um comando de ping.
```
ping google.com
```
Se for uma conexão via Wi-Fi, então use o comando pra entrar no menu de configuração de wi-fi
```
iwctl
```
<details>
  
Depois o comando pra listar as placas de rede e saber o nome do dispositivo pra usar na próxima etapa
> Se for um notebook ou se o computador tiver apenas uma placa de rede wi-fi, o dispositivo vai ser sempre `wlan0` então dá até pra pular essa parte

```
device list
```
  
Pra buscar as redes disponíveis
> Se souber o nome exato da rede wi-fi pra digitar (maiúsculas e minúsculas), também pode pular essa parte
```
station nome_do_dispositivo scan
```
</details>

Selecionar o dispositivo de Wi-fi e conectar na rede  
```
station nome_do_dispositivo connect nome_da_rede
```
Aqui ele vai pedir a `passphrase` que é a senha, é só digitar. Se em até 10 segundos não mostrar uma mensagem de erro. É porque funcionou!

> Dá pra testar usando o comando de ping.

## 1.6 Definir o idioma para pt_BR
Abrir o arquivo modelo de configuração com o editor de texto via terminal
```
nano /etc/locale.gen
```
Descer com a seta e descomentar (apagar o `#` da frente) na linha escrito `pt_BR.UTF-8 UTF-8` e `pt_BR ISO-8859-1`. 
Salvar com `CTRL`+`X` e `ENTER`

Gerar o arquivo de idioma
```
locale-gen
```

# 2 Particionar, formatar e montar as partições
Só pra esclarecer como funciona essa etapa. Primeiro tem que criar a partição, que é avisar pro sistema quanto espaço do disco pode ser usado pra cada partição criada, já que o disco tem escrita dinâmica então ele tá sempre gravando em setores diferentes mas sempre mantem a proporção de espaço pra cada partição. E também avisar pro sistema que tipo de partição é cada uma, principalmente pra ele saber onde fica o EFI do Boot. 

Depois tem que formatar as partições pra definir o formato de arquivo, nesse caso vai ser só dois: Fat32 e Btrfs.

Por último tem que montar os diretórios de pasta, dentro das partições, pra poder gravar cada coisa no lugar certo durante a instalação.

## 2.1 Particionar o disco antes de formatar
Na instalação do sistema ele interpreta as unidades de disco como /dev/... (Sd pra SSD, nvme0n pra NVME, ...)  
Pra saber qual é o dispositivo tem que usar o comando pra listar todas as unidades e descobrir pelo tipo ou pelo tamanho, o ideal é deixar conectado só o disco que vai ser formatado e a mídia de instalação.
```
fdisk -l
```
Pra facilitar nos exemplos, vou considerar que seja um SSD
```
fdisk /dev/sda
```
Usar o comando `d` pra ir apagando as partições que já existam no disco

Daqui pra frente é assim: 
- O comando `n` cria uma nova partição
- O terminal pergunta um número pra identificar a partição. Ex: `1`
- Vai ser sugerido um setor inicial, é só pressionar `Enter`
- Vai perguntar o setor final, tem que colocar quanto vai ser somado no tamanho da partição e a unidade de medida, tudo junto. Ex: `+1g`
- digitar `t` pra definir o tipo de partição e informar pro sistema pra que ela vai ser usada depois. Ex: `uefi`

### Modelo pra partição /dev/sda1 (boot, só serve pra iniciar o sistema)
> 1 , +1g, UEFI
### Modelo pra pratição /dev/sda2 (root, onde fica os arquivos de sistema e de usuário)
> 2 , +espaço restante do disco, btrfs

Salvar usando `w` e `Enter`

## 2.2 Formatar o disco

Partição boot
```
mkfs.fat -F32 /dev/sda1 
```

Partição root
```
mkfs.btrfs /dev/sda2
```

## 2.3 Criar os pontos de montagem

Pra montar o root tem que usar o comando
```
mount /dev/sda2 /mnt
```

Pra montar o boot tem que usar o comando
```
mount --mkdir /dev/sda1 /mnt/boot
```

# 3 Instalação, finalmente!
Tem que começar instalando os pacotes básicos
```
 pacstrap /mnt base linux linux-firmware
```









































