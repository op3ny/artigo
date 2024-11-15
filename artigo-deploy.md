Titulo: "Por quê você dev deveria dominar Bash e Linux o quanto antes?"
Descrição: "Entenda qual é a importância de dominar e aprender sobre duas coisas que estão muito presentes na vida de todos nós, seja nos sites que você acessa, seja nos seus sites."



# Lá vem ele...

Olá meu amigo dev, tudo bem? Bem vindos a mais um artigo de eu tentando te ensinar como fazer seu próprio driver pra aquele mouse que não tá funcionando no Linux a mais de um mês! Brincadeiras a parte, hoje eu quero falar sobre um tema que me fez refletir muito durante a minha bela semana, por quê aprender bash e linux? Bem, e como eu estou escrevendo para um site para devs, eu pensei, como diabus eu vou conseguir encaixar isso no público alvo do meu texto? Foi quando na sexta (15 de novembro de 2024), lá no Discord da Play Devs, o White (pojinho) enviou uma pergunta, sendo ela na íntegra: "rpzd, pq é bom um dev saber bash? tenho um ubuntu e queria saber o pq", e bingo, achei o que eu precisava! Desde então, fiquei mechendo nuns projetos malucos, e agora, aqui estou fazendo este artigo pra vocês, neste mesmo dia, 15 de novembro. Bem, acho que agora é a hora que eu paro de ser o professor de português maneiro, pro professor de matemática chato...


# Que comece a ópera!

Bem, agora que vocês entenderam de onde o "jênio", sim, gênio com J tirou esse lindo tema de artigo, vou logo te falar, você com certeza já deve ter tido seu primeiro deploy, e nele, você já começou a ter aquele frio na barriga quando você tentava configurar o servidor, e dava erro no deploy, pois é meu querido amigo, tudo porquê você achava que era os mesmos comandos do Windows, bem, se você nunca passou por isso, de duas a uma, ou você viu um tutorial, ou você é maluco igual a mim, e começou na computação aprendendo a customizar Arch... De qualquer forma, o meu objetivo aqui, é trazer a teoria e a prática separados, então calma, que essa teoria vai ser bem divertida, eu acho... (pra quem não entendeu, é porquê nessa parte eu ainda não tinha feito a teoria...)


# Starting the computer, i think...
## (Leitores acíduos: Denovo???)

Bom, se você não entendeu a referência do título, é porquê usamos esse mesmo título do artigo "Como usar o docker no Linux? (Aula 3 - Bash Script)", e bem, agradeça por essa introdução já com referências, porquê agora, você vai ver o circo pegar fogo!

---

Pela minha expêriencia conversando em servers de development no Discord, e com alguns entusiastas na vida real, eu percebi que as pessoas tem um certo preconceito com Linux, e isso, é algo que me deixa levemente incomodado, já que incrivelmente, alguns YouTubers famosos como o "William Azarado", comenta barbaridades sobre a tecnologia em geral em seu canal, ou seja, qualquer um que conheça o minimo de tech, já entende que são coisas que não tem sentido, é tipo uma teoria da conspiração, mas que pode ser quebrado com um "googada". Dentre algumas coisas que dizem, é que o Linux tem uma interface antiquada, ou que Linux é inseguro, ou até mesmo, que Linux tem poucos apps. E isso, é quase uma ofensa a qualquer amante de Linux e tecnologias OpenSource, e bem, se você não se tocou ainda, eu sou um amante de Linux e tecnologias OpenSource, então seja bem vindo a mim quebrando cabeça por 1 milésimo de segundo para retrucar a essas afirmações...


# Confrontando fake-news! (Só pelo entreterimento, se quiser só pula essa parte)

1° Afirmação: "O Linux tem uma interface antiquada..."

---

Bem, pra começar a falar, o Linux nem interface tem, pra falar a verdade, nem sequer algo de clicavel ele mostra, e bem, o Linux é um simples Kernel, ou seja, falando na linguagem popular e resumida, o Linux é a Rocha Matriz, a base, o responsável por outros sistemas operacionais baseados nele (Vulgo: Distros), e essas distros baseadas nele que realmente tem uma interface, podendo elas ser parecidas com o MacOS (Gnome), alguns mais simples e direto ao pontos, para máquinas mais fracas (XFCE/LXQT), e alguns parecidos com a interface do Windows 10 (KDE Plasma). Ou seja, alguns realmente podem ter uma interface dita mais antiga, porém, isso são para máquinas mais simples, e que não aguentam interfaces mais pesadas, que por sinal, é um dos públicos alvo do Linux.

---

2° Afirmação: "O Linux é inseguro..."

---

Bem, acho que pra começo de conversa, temos que entender que muito pelo contrário, graças ao seu sistema de privilégios e permissões, que por sinal é bem complexo, permite ele ser um dos sistemas mais seguros do mundo. Assim, podemos comprovar com um exemplo, no Windows, quando você instala uma aplicação, ele não requisita nada, além de clicar em um "Sim" numa caixinha, isso porquê um virus nem disso precisa porquê a permissão padrão do usuário Windows já dá diversas brechas. Já no Linux, qualquer operação, seja de instalação, remoção de apps ou arquivos, e até mesmo edição, necessita da permissão "sudoer", que só pode ser adquirida com a inserção de sua senha.

---

3° Afirmação: "O Linux tem poucos apps..."

---

Novamente, temos algo que não tem nenhum sentido. Assim comos muitos apps Windows não tem no MacOS, vários apps Mac não tem em Windows. O mesmo ocorre com o Linux, porém, temos uma diferença absurda quando falamos de "OpenSource", isso porquê, acaba que a própria comunidade cria alternativas a esses apps, e lançando em lojas como o FlatHub, Snap, e até no Repositório oficial de sua distro. E com isso, editores de vídeo como o Adobe Premiere, podem ser substituidos pelo Kdenlive (Editor de vídeo da criadora da interface KDE), ou então, aquele famoso joguinho com o Wine! Ah, e já com isso podemos ir para a proxima afirmação.

---

4° e ultima afirmação: "WINE é um emulador..."

---

Nos outros eu precisei argumentar, mas aqui, eu só preciso falar o que WINE significa... (Wine Is Not an Emulator), ou a tradução, (Wine Não é Um Emulador)... Eu acho que essa é a pior afirmação de todas...

---

Agora que desmistificamos basicamente todos os boatos sobre Linux, e você já tem na mente o que realmente é Linux, podemos voltar ao tema principal...


# Deploys....

Os deploys, são basicamente um processo de colocar o seu serviço, app ou site no ar, e bem, isso pode ser feito de inúmeras formas. Pode ser por serviços de deploy (Heroku, Vercel, Render, etc...), pode ser por VPS (Virtual Private Server) ou em Português (Servidor Privado Virtual), eu deveria explicar, mas acho que o próprio nome já diz, que nele você vai ter que entender bash, e só seguir rumo pra conseguir fazer deploy (usando o Deploy Manual). E por último, usando a técnica Você e Deus (é zueira tá, o nome não é esse askkask), que em resumo, é tu instalar o Debian num computador teu aí, e ir fazendo deploy pelo seu teclado e monitor aí, enquanto você reflete o porquê você tá fazendo aquilo, e tendo uma crise existencial! Pelo menos tu já tira 10 na aula de filosofia...


# A importância

Chegamos no tópico principal, bem, todos os serviços de deploy utilizam linux por debaixo dos panos para realizar o seu deploy, então sim, seu site na Vercel tá rodando num Linux okey? E bem, quando você deseja realizar um deploy num serviço desses, você precisa entender como a infra funciona, para que o deploy funcione do jeito que você quer. Por exemplo, as vezes é necessário naquela parte do comando pra instalar os requerimentos, tu ter que dar um "npm install discord.js | echo 'arquivo-importante-pra-funcionar' > arquivo.txt", e esse tipo de gambiarra, as vezes ela é necessária para que aquilo que você pensava dê certo! E exatamente por isso precisamos entender como funciona os comandos Linux e Bash Script, para que possamos criar certas gambiarras que permitam com o que o nosso código funcione! Portanto, além de isso ser uma chave de ouro no seu currículo, entender sobre redes, Linux, Bash Script e ter fé, é bem importante enquanto você desenvolve, ou no caso, vai te libertar de muitos erros de deploy e você igual um besta tentando achar de onde tá vindo o problema... Uma experiência própria, foi em um bot que eu estava hospedando na Render, e eu tive que usar o serviço de "Web Services", pra no código em JS, ele abrir um servidor HTTP, apenas pra ele rodar o bot de discord e eu conseguir usar o Uptime Bot pra ele se manter ativo. Em resumo, saiba que isso vai ser primordial para você que precisa fazer deploy diáriamente, e saiba, agora ou depois você vai ter que entender como funciona o básico de Linux para que você evolua, afinal, é tipo ser engenheiro sem saber matemática, só artes. Você consegue se virar, mas uma hora ou outra, você vai precisar de matemática.


# Recomendações

"Humberto, beleza, esse artigo me exclareceu muita coisa (se é boa ou ruim é melhor deixar quieto), mas, como eu vou evoluir?". Então meu pequeno gafanhoto (referência ao Gustavo Guanabara), acho que você vai precisar entender sobre muita coisa. Primeiramente, acho interessante você se aprofundar em Sistemas Operacionais (especificamente Linux), redes e Bash Script. Especialmente Linux, é uma área que quase ninguém se liga e quer entender, geralmente só lidam como se fosse um extra, então, confia em mim, um dia, quando você tiver cheio de erro no console da Render, eu avisei (isso me dá flashback de guerra... zueira.), em fim, só tenta estudar *Linux*, *Redes* e *Sistemas Operacionais (só o basico)*, que com certeza tu vai ficar tranquilo quando ouvir Deploy, e vai dormir em paz.


# Fim!

Muito Obrigado a você que leu esse artigo, afinal, poucos são os que querem se aprofundar num asunto que alguns acham óbvio, acho que pra finalizar, eu só quero dizer, que Linux e OpenSource são áreas necessárias para nós devs, e bem, meu objetivo aqui, foi além de explicar a importância, te contextualizar de que o óbvio nem sempre é o óbvio, e que eu espero de coração ter te ajudado nessa jornada, então... Vlw, flw e fui!
