## History:
Initial, ViolentlyPeaceful (Aug. 2017)

---

## 1) – Introdução

Monero é o dinheiro eletrônico seguro, não-rastreável e privado. Ele é código aberto e de livre acesso a todos.
Nesse vídeo, vamos focar nas assinaturas em anel (ring signatures).

## 2) – Recapitulação tecnológica

No último vídeo, vimos como os endereços sigilosos impedem as saídas financeiras de serem associadas ao endereço público do destinatário.
Isso é possível com o uso de chaves públicas de destino e uso únicos.
Chaves públicas de uso único só podem ser usadas pelo destinatário, e somente ele pode detectar sua saída financeira no blockchain.
Como todas as saídas não podem ser vinculadas, a privacidade do destinatário é garantida.

Do outro lado da transação, a privacidade do remetente é protegida com o uso das assinaturas em anel.

## 3) – O termo: Assinaturas em Anel, Imagem Chave

Assinatura em anel é um tipo de assinatura digital no qual um grupo de possíveis assinantes são combinados a produzir uma nova assinatura que autoriza a transação.
Isso é análogo à assinatura de um cheque de uma conta conjunta, mas com o verdadeiro assinante permanecendo desconhecido.
A assinatura digital é composta pelo assinante real combinado com não-assinantes que formam o anel, onde todos os membros são iguais e válidos.
O verdadeiro assinante é uma chave de gasto única que corresponde a uma saída financeira da carteira do remetente.
Os não-assinantes são as saídas financeiras de antigas transações do blockchain, que funcionam como armadilha.
Essas saídas compõem as entradas de uma transação.
Para um terceiro, todas as entradas são igualmente prováveis de serem a saída gasta na transação.
Essa característica ajuda o remetente a esconder a origem da transação, tornando as entradas indistinguíveis entre si.


Você deve estar se perguntando, “se não há como um terceiro verificar qual saída está sendo gasta, o que impediria que alguém gastasse a mesma saída duas vezes?”
Essa questão é abordada com o uso de “imagens-chave.”
Uma imagem-chave é uma chave criptográfica derivada de uma saída que está sendo gasta, e faz parte de cada transação de assinatura em anel.
Existe somente uma imagem-chave para cada saída do blockchain, mas devido às suas propriedades criptográficas, não é possível determinar qual saída criou qual imagem-chave.
Uma lista de todas as imagens-chave usadas é mantida no blockchain, permitindo que os mineiros verifiquem que nenhuma saída é gasta duas vezes.

Vamos ver um exemplo de como tudo isso funciona.

## 4) – Transação de Assinaturas em Anel

Alice deseja enviar Monero para Bob em um anel de tamanho cinco.
Uma das cinco entradas vem da carteira da Alice, que será consumida na transação.
As outras quatro entradas foram selecionadas de forma arbitrária do blockchain, e são usadas como armadilha.
Isso forma um grupo de cinco possíveis assinantes, onde todos os membros do anel são, plausivelmente, o assinante real da transação.
Para um observador externo, incluindo o próprio Bob, não é claro qual entrada realmente foi assinada pela chave de uso único da Alice.
Porém, com a imagem-chave, a rede é capaz de confirmar com segurança que o Monero enviado ao Bob não foi gasto anteriormente.
Como vimos, usando as assinaturas em anel, o Monero protege a privacidade do remetente escondendo a fonte das entradas, garantindo que a origem de qualquer Monero permaneça não-rastreável.

## 5) – RingCT

Para aumentar a privacidade das duas partes, as Transações em Anéis Confidenciais, chamadas de RingCT, foram implementadas para ocultar os valores das transações.
O RingCT traz algumas melhorias ao protocolo das assinaturas em anel.
Falaremos mais do RingCT no próximo vídeo.

## 6) – Fim?

Se você está interessado em saber mais do que faz o Monero a principal criptomoeda privada, veja nossos outros vídeos ou visite getmonero.org.