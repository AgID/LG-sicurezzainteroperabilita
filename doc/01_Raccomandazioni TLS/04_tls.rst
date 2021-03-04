Transport Layer Security
========================

Versioni TLS disponibili
------------------------

Ad oggi sono disponibili le seguenti versioni TLS:
●	TLS 1.3    (pubblicato nel 2018)    
●	TLS 1.2    (pubblicato nel 2008)  
●	TLS 1.1    (pubblicato nel 2006)
●	TLS 1.0    (pubblicato nel 1999)

TLS 1.0 e 1.1 sono protocolli obsoleti che non supportano i moderni 
algoritmi crittografici e risultano vulnerabili ad attacchi [1]_. 
Questi due protocolli sono da ritenersi deprecati come da comunicazioni 
di Google [2]_, Microsoft [3]_, Cisco [4]_, Apple [5]_ e Mozilla [6]_.


Suite di cifratura (cipher suite) 
---------------------------------

Il supporto crittografico in TLS è fornito attraverso l'uso di varie 
suite di crittografia. Una suite di cifratura definisce una combinazione 
di algoritmi per lo scambio di chiavi e per fornire riservatezza e 
integrità della sessione durante lo scambio di messaggi. Al momento 
della negoziazione di una sessione TLS il client presenta una serie di 
cipher suite supportate che propone al server il quale ne seleziona una.

Suite di cifratura versione 1.2 
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Le suite di crittografia TLS 1.2 contengono quattro singoli algoritmi 
che rendono sicuro il canale in fase di handshake. 

Una suite di cifratura può, ad esempio, essere composta dai seguenti 4 
gruppi di algoritmi: 

.. list-table:: 
   :widths: 15 40
   :header-rows: 1

   * -    Funzione
     -    Algoritmo

   * -    Scambio di chiavi
     -    RSA, Diffie-Hellman, ECDH, SRP, PSK

   * -    Autenticazione
     -    RSA, DSA, ECDSA

   * -    Cifratura dati
     -    RC4, 3DES, AES

   * -    Hashing
     -    HMAC-SHA256, HMAC-SHA1, HMAC-MD5

Un esempio di cipher suite TLS 1.2 con i relativi algoritmi utilizzati 
delle varie fasi è la seguente:

.. code-block:: none

    TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256

Suite di cifratura versione 1.3
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

La nuova versione di TLS ha portato con sé molti miglioramenti. Tra i 
più importanti è stata la dismissione di algoritmi e cifrari vulnerabili 
o non adatti a garantire PFS, tra i quali:

- RC4 Stream Cipher
- RSA Key Exchange
- SHA-1 Hash Function
- CBC (Block) Mode Ciphers
- MD5 Algorithm
- Vari gruppi di Diffie-Hellman non-ephemeral 
- EXPORT-strength ciphers
- DES
- 3DES

Inoltre, è stata migliorata la fase di handshake, dimezzando la latenza 
della crittografia e riducendo il tempo di handshake. 

Le suite di crittografia TLS 1.3 non includono più gli algoritmi di 
scambio chiave e firma e l’autenticazione è stata unita alla crittografia 
in un unico algoritmo di tipo AEAD (Authenticated Encryption with 
Additional Data). Ciò ha semplificato le possibili combinazioni di 
cipher suite.  

Attualmente sono solo cinque le cipher disponibili per TLS 1.3:

Attualmente sono solo cinque le cipher disponibili per TLS 1.3:  

- TLS_AES_256_GCM_SHA384
- TLS_CHACHA20_POLY1305_SHA256
- TLS_AES_128_GCM_SHA256
- TLS_AES_128_CCM_8_SHA256
- TLS_AES_128_CCM_SHA256

.. list-table:: 
   :widths: 15 40
   :header-rows: 1

   * -    Componente
     -    Contenuto

   * -    TLS
     -    La stringa "TLS"

   * -    AEAD
     -    Algoritmo AEAD usato per la protezione dei dati

   * -    HASH
     -    Algoritmo di hash usato con HKDF

.. [1]
   Cf.
   https://en.wikipedia.org/wiki/Transport_Layer_Security#Attacks_against_TLS/SSL

.. [2]
   Cf.
   https://security.googleblog.com/2018/10/modernizing-transport-security.html

.. [3]
   Cf.
   https://docs.microsoft.com/en-us/office365/troubleshoot/o365-security/tls-1-2-in-office-365-gcc

.. [4]
   Cf.
   https://support.umbrella.com/hc/en-us/articles/360033350851-End-of-Life-for-TLS-1-0-1-1-

.. [5]
   Cf.
   https://webkit.org/blog/8462/deprecation-of-legacy-tls-1-0-and-1-1-versions/

.. [6]
   Cf.
   https://blog.mozilla.org/security/2018/10/15/removing-old-versions-of-tls/
