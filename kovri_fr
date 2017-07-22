Kovri Lightweight C++ I2P Router Script

Version 1 français- sgp / cryptochangements

Jusqu'à ce point, cette série a  discuté de la façon dont Monero obscurcit l'information qui est stocké sur le blockchain. Pourtant, information personnel peut-être divulgée en essayant d'annoncer sa transaction au réseau.

Supposons qu'Alice voudrait envoyer une transaction à Bob. Elle prépare la transaction Monero sur son ordinateur, et elle est prête à dire au réseau de nœuds et mineurs qu'elle voudrait que le réseau inclut sa transaction dans le prochain bloc.

Alice est connecté à pluseurs, mais pas tous, les nœuds du réseau. Sa requête de transaction va devoir atteindre autant de nœuds que possible pour avoir la plus grande chance d'être inclus dans le prochain bloc. Elle est connecté à 5 nœuds du réseau, elle envoie donc sa requête de transaction aux 5 nœuds. Le système continue comme ça jusqu'à beaucoup de nœuds ont cette donnée

Malheureusement, il y a toujours un peu de danger en envoyant sa requête. C'est possible que des nœuds du réseau enregistre l'adresse IP dont la requête vient. Une adresse IP est comme votre adresse de domicile, mais pour votre connexion internet. Un attaquant ne peut pas savoir si la première adresse IP qu'il a eu est la vraie adresse du envoyeur, et il ne peut pas savoir les détails de la transacion comme l'envoyeur, le montant, ou le récepteur. Pourtant, l'attaquant peut associer une transaction, comme la transaction qu'Alice a créé dans cet exemple, avec une adresse IP pour lui aider deviner l'envoyeur.

Un attaquant peut donc frapper à la porte d'Alice et exiger qu'Alice lui donne ses clés privées pour qu'il peut enquêter. Alternativement, l'attaquant peut essayer de bloquer les transactions d'Alice d'être transmis au réseau. On appel ce genre d'attaque une "Attaque Sybil"

Qu'est-ce qu'on peut faire pour atténuer ce problème? Alice ne sait pas quels nœuds enregistrent sa adresse IP, donc elle ne peut pas éviter ces mouvais nœuds. Son seul choix est de cacher sa adresse IP.

Il existe pluseurs de façons de cacher votre adresse IP. On peut utiliser TOR, un VPN, ou I2P. Nous allons nous concentre sur I2P dans cette vidéo puisque c'est le réseau dont Kovri participe.

Dans une seule phrase, Kovri est un routeur simple pour le réseau I2P qui est programmé en C++ et il est compatible avec des cryptomonnaies. I2P est une couche d'internet qui rend toutes les connexions dans le réseau privée. Au lieu de se connecter directement au réseau, comme un site du web, tout l'information est transmis aux autres routeurs du réseau I2P. Ces routeurs savent peu ou aucun détails sur la donnée qu'ils transmettent, du coup toute la donnée est privée.

Kovri sera intégré avec Monero dans des futures sorties et il sera activé par défaut pour annoncer les transactions aux réseau.

Maintenant, quand Alice envoie sa requête de transaction travers le réseau I2P avec Kovri, personne ne pourra savoir sa adresse IP. Les nœuds du réseau Monero qui enregistre des adresses IP ne verra qu'une adresse .i2p qui ne sert à rien. Donc, si ces nœuds continuent à enregistrer des adresses IP, ce genre d'information ne sera plus utile.

En outre, supposons qu'Alice a un fournisseur d'accès internet qui ne veut pas qu'elle utilise Monero. Alice peut choisir d'envoyer tout la donnée de Monero travers le réseau I2P. Maintenant, son fournisseur d'accès internet ne pourra pas savoir qu'elle utilise Monero.

Bref, Kovri est un routeur qui permet à utilisateurs de Monero de se connecter au réseau I2P pour qu'ils peuvent envoyer anonymement des requêtes de transaction. Des nœuds du réseau Monero ne pourra plus enregistrer les vrais adresses IP d'utilisateurs de Monero.

Visitez getkovri.org pour en savoir plus sur Kovri, ou getmonero.org pour en savoir plus sur Monero
