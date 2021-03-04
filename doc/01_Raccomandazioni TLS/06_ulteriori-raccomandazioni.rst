Ulteriori raccomandazioni
=========================

Rinegoziazione della sessione
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

La rinegoziazione di una  sessione TLS  è vulnerabile ad una serie di 
attacchi. Le implementazioni utilizzate DEVONO rispettare le indicazioni 
contenute in  RFC5746 [1]_. Un server DOVREBBE rifiutare una rinegoziazione 
della sessione iniziata dal client. 

Analogamente a quanto indicato in RFC5756 [2]_, quando si utilizza
HTTP/2 RFC7540 [3]_ con TLS 1.3, il servizio NON DEVE permettere la 
post-handshake authentication, come indicato in RFC8740 [4]_.

Considerazioni simili valgono in tutti i contesti in cui richieste 
multiple HTTP vengono trasmesse con meccanismi di multiplexing su 
singola connessione.

Compressione TLS
^^^^^^^^^^^^^^^^

La compressione TLS DOVREBBE essere disabilitata; essa è stata rimossa 
dalla versione 1.3 di TLS perché sfruttata in passato da diversi exploit, 
tra cui il noto CRIME [5]_.

Estensione Heartbeat
^^^^^^^^^^^^^^^^^^^^
L'estensione Heartbeat specificata in RFC 6520 [6]_ permette di prolungare 
la durata di una connessione TLS senza dover eseguire una rinegoziazione 
della sessione. Questa estensione è stata utilizzata in  Heartbleed, 
con cui l'attaccante è in grado di accedere ad alcune aree di memoria 
del server che potrebbero contenere dati riservati. L'uso dell'estensione 
Heartbeat è NON RACCOMANDATO e nel caso fosse necessario il suo utilizzo, 
si raccomanda di verificare che non sia vulnerabile a Heartbleed.



.. [1]
   Cf.
   https://tools.ietf.org/html/rfc5746

.. [2]
   Cf.
   https://tools.ietf.org/html/rfc5756

.. [3]
   Cf.
   https://tools.ietf.org/html/rfc7540 

.. [4]
   Cf.
   https://tools.ietf.org/html/rfc8740

.. [5]
   Cf.
   https://en.wikipedia.org/wiki/CRIME

.. [6]
   Cf.
   https://tools.ietf.org/html/rfc6520

