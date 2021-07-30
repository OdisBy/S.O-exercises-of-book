Exercícios do capítulo 2

1. O que diferencia o núcleo do restante do sistema operacional? 

 

- É o coração do sistema. Ele tem a função de gerenciar os recursos que serão usados, e também tem a     função de fazer as principais abstrações. Ele está em contato com o     hardware da máquina.

 

 

2. Seria possível construir um sistema operacional seguro usando um processador que não tenha níveis de privilégio? Por quê? 

 

- Não, porque as aplicações comuns ficariam no mesmo nível do núcleo, o que poderia fornecer a elas a     capacidade de ter acesso direto ao hardware do computador.

 

 

3. Os processadores da família x86 possuem dois bits para definir o nível de privilégio, resultando em 4 níveis distintos. A maioria dos sistemas operacionais para esses processadores usam somente os níveis extremos (0 e 3, ou 002 e 112 ). Haveria alguma utilidade para os níveis intermediários?

 

- Não sei.

 

4. Quais as diferenças entre interrupções, exceções e traps? 

- A interrupção é um pedido de evento imediato de algo externo a máquina. 
- A exceção é o pedido de evento imediato de algo de dentro da máquina.
- Trap são eventos causados pelo processador.

 

5. O comando em linguagem C *fopen* é uma chamada de sistema ou uma função de biblioteca? Por quê?

- É uma biblioteca. Na linguagem C não existe um comando de entrada/saída direto, então para     conseguir executar um é necessário uma biblioteca.

 

6. A operação em modo usuário permite ao processador executar somente parte das instruções disponíveis em seu conjunto de instruções. Quais das seguintes operações não deveriam ser permitidas em nível usuário? Por quê? 

(a) Ler uma porta de entrada/saída 

(b) Efetuar uma divisão inteira

(c) Escrever um valor em uma posição de memória 

(d) Ajustar o valor do relógio do hardware 

(e) Ler o valor dos registradores do processador 

(f) Mascarar uma ou mais interrupções

 

- A, C, E, F. 
- A: o acesso direto a leitura de portas de estrada/saída gera uma falha de segurança. 
- C: pode sobrepor outras aplicações e encher a memória, além de causar uma falha de segurança.
- E: Pois lida diretamente com o hardware.
- F: Como atua sobre um dispositivo externo ele consegue acesso direto sobre esse, causando mais     falhas de segurança.

 

7. Considerando um processo em um sistema operacional com proteção de memória entre o núcleo e as aplicações, indique quais das seguintes ações do processo teriam de ser realizadas através de chamadas de sistema, justificando suas respostas: 

(a) Ler o relógio de tempo real do hardware. 

(b) Enviar um pacote através da rede. 

(c) Calcular uma exponenciação. 

(d) Preencher uma área de memória do processo com zeros. 

(e) Remover um arquivo do disco.

 

- Remover um arquivo do disco.     Pois se trata de um dispositivo externo, e apenas o núcleo tem acesso a     ele, então é necessário uma system call para acessá-lo.

 

8. Coloque na ordem correta as ações abaixo, que ocorrem durante a execução da função printf("Hello world") por um processo (observe que nem todas as ações indicadas fazem parte da sequência). 

(a) A rotina de tratamento da interrupção de software é ativada dentro do núcleo.

(b) A função printf finaliza sua execução e devolve o controle ao código do processo.

(c) A função de biblioteca printf recebe e processa os parâmetros de entrada (a string “Hello world”). (d) A função de biblioteca printf prepara os registradores para solicitar a chamada de sistema write() 

(e) O disco rígido gera uma interrupção indicando a conclusão da operação. 

(f) O escalonador escolhe o processo mais prioritário para execução. 

(g) Uma interrupção de software é acionada. 

(h) O processo chama a função printf da biblioteca C. 

(i) A operação de escrita no terminal é efetuada ou agendada pela rotina de tratamento da interrupção. (j) O controle volta para a função printf em modo usuário.

 

- H, C, G, A, I, E, B, J

- C, F, H, D, A, I, G, E, B, J

- Obs: Primeira minhas respostas, segunda a correção.