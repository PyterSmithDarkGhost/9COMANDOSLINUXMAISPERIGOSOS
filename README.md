Os 9 comandos mais perigosos do Linux


Existem alguns comandos do Linux que podem travar o sistema operacional ou até danificá-lo permanentemente. Eis os 9 mais perigosos.

sudo rm -rf /* 2>/dev/null
Esse comando apagará tudo que estiver no diretório raiz e em todos os outros diretórios a partir deste (opção “-r”), sem questionar ao usuário se deve ou não apagar (opção “-f”) e toda possível mensagem de erro deve ser invisível ao usuário (2>/dev/null).

sudo shred /dev/sda
O comando shred é, como o próprio nome diz, destruidor. Ele literalmente destrói arquivos de forma que é impossível recuperar! Mesmo com recuperador de arquivos! Este comando tem algumas opções bastante interessantes que valem a pena serem estudadas

Ainda que a execução do processo seja finalizada no meio, o sistema ainda ficará inoperante.

$(echo 7375646f20726d202d7266202f2a | xxd -r -p)
Este comando é o mesmo “sudo rm -rf /*” do primeiro item desta lista. A diferença é que ele está codificado em hexadecimal.

Usando esta técnica, é possível codificar qualquer comando.

python -c ‘import os; os.system(“”.join([chr(ord(i)-1) for i in “sn!.sg!0+”]))’
Este é a versão “Python” do “rm -rf /*” usando uma pequena “ofuscação” para não ficar tão na cara.

sudo dd if=/dev/zero of=/dev/sda
Este comando preencherá o HD com zeros! Ou seja, apagará tudo que tiver nele.

sudo chmod -R 777 / 2>/dev/null
Neste comando, todos os arquivos de sistema adquirirão permissão de leitura, escrita e execução para todos os usuários! Assim qualquer usuário poderá fazer o que quiser no sistema.

source ~/.bash_history
O source “executa comandos de um arquivo no shell atual”. Imagina executar todos os comandos já digitados novamente? No mínimo faria uma bagunça imensa…

sudo chmod -R -x / 2>/dev/null
Este comando retira a execução de todos os arquivos do sistema! Após este comando ser executado, o sistema parará de funcionar completamente.

:(){ :|:& };:
Esse comando é conhecido como “Fork Bomb”. O que ele faz é criar uma função chamada “:” na parte inicial com “:()”, abre parênteses para definir os comandos que irão dentro dessa função e, dentro da função, o script chama a si mesmo recursivamente em background “ :|:&”. Finalmente a função é fechada e chamada de fato “};:”.

Dos comandos apresentados, esse é o mais inocente. Ele rapidamente irá consumir toda a memória do sistema e travará completamente. Porém tudo estará intacto após reiniciar.
