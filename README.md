# Manual de instalação do arch-linux + Gnome puro + systemd-boot
Testei diversas distros Linux, especialmente as mais populares (Arch, Mint, Fedora, Ubuntu e Debian), e cheguei à conclusão que essa combinação foi a melhor para o meu uso cotidiano com melhor suporte ativo da comunidade, boa compatibilidade com pacotes de aplicativos e com maior liberdade de personalização, basicamente tudo que serve pra outras distros, serve aqui também e algumas vezes até mais fácil ainda de ser feito. E acima de tudo, que contenha apenas o obrigatório para o sistema funcionar, mas sempre deixando a possibilidade de instalar qualquer coisa que eu precisar futuramente.

## Por quê o Arch-Linux?
Ele é baseado no Debian que é uma das primeiras distros baseadas em Linux, a qual eu percebi que tem uma variedade de pacotes e de suporte muito grande comparado com outras distros.

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
























