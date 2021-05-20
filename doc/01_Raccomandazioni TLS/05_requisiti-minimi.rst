Requisiti minimi lato server
============================

Questa sezione fornisce una serie minima di requisiti che un server deve 
implementare per soddisfare queste linee guida, ma non ha l’obiettivo
di fornire alcuna indicazione implementativa. 

Si ribadisce che il presente documento verrà aggiornato all’eventuale 
insorgere di problemi di sicurezza legati ai protocolli e/o algoritmi. 

Versioni TLS raccomandate
-------------------------

I servizi esposti DEVONO utilizzare la versione TLS 1.2, o superiori, e 
DOVREBBERO rifiutare la negoziazione di una versione inferiore. 

Versioni precedenti del protocollo sono insicure o contengono vulnerabilità 
note. 

Periodicamente bisogna controllare tutte le versioni e rimanere aggiornati 
per evitare configurazioni errate e nuove vulnerabilità.

Suite di cifratura raccomandate
-------------------------------

Per agevolare la configurazione del protocollo TLS, Mozilla fornisce un 
tool [1]_ che genera configurazioni sicure dei suoi principali software. 

DOVREBBE essere utilizzato nella configurazioni "Modern" (rivolte ai client 
con TLS 1.3 e che non necessitano di retro-compatibilità) e "Intermediate" 
(compatibili con la maggior parte dei client). 

NON DOVREBBE essere utilizzato nella configurazioni di tipo "Old" perché 
potrebbero includere cipher suite vulnerabili.

Di seguito sono elencate le versioni minime dei client per ciascuna 
categoria di configurazione: 

.. list-table:: 
   :header-rows: 1

   * -    Configuration
     -    Firefox
     -    Android
     -    Chrome
     -    Edge
     -    Internet Explorer
     -    Java
     -    OpenSSL
     -    Opera
     -    Safari

   * -    Modern
     -    63	
     -    10.0	
     -    70	
     -    75	
     -    	
     -    11	
     -    1.1.1	
     -    57	
     -    12.1

   * -    Intermediate
     -    27	
     -    4.4.2	
     -    31	
     -    12	
     -    11 (Win7)	
     -    8u31	
     -    1.0.1	
     -    20	
     -    9

   * -    Old
     -    1	
     -    2.3	
     -    1	
     -    12	
     -    8 (WinXP)	
     -    6	
     -    0.9.8	
     -    5	
     -    1 

Cipher suite Modern
^^^^^^^^^^^^^^^^^^^

Sono accettate le suite di cifratura con le seguenti caratteristiche: 

- Versione TLS: 1.3 (la 1.2 non è accettata)
- Tipo di certificato: ECDSA (P-256)
- Curva TLS: X25519, prime256v1, secp384r1
- Durata del certificato: 90 giorni

Suite di cifratura (TLS 1.3):

- TLS_AES_128_GCM_SHA256 
- TLS_AES_256_GCM_SHA384
- TLS_CHACHA20_POLY1305_SHA256

Note: Le suite di cifratura moderne sono più sicure, ma potrebbero non 
essere compatibili con client obsoleti, rendendo inutilizzabile 
l’applicazione. 

Cipher suite Intermediate
^^^^^^^^^^^^^^^^^^^^^^^^^

Sono accettate le suite di cifratura con le seguenti caratteristiche: 

- Versione TLS: 1.3, 1.2
- Curva TLS: X25519, prime256v1, secp384r1
- Tipo di certificato: ECDSA (P-256) (raccomandato) o RSA (2048 bits)
- Durata del certificato: da 90 giorni (raccomandato) a 366 giorni
- Dimensione del parametro DH: 2048 (solo per Intermediate RFC7919)

Suite di cifratura (TLS 1.3):

- TLS_AES_128_GCM_SHA256 
- TLS_AES_256_GCM_SHA384
- TLS_CHACHA20_POLY1305_SHA256

Suite di cifratura (TLS 1.2):

- ECDHE-ECDSA-AES128-GCM-SHA256 
- ECDHE-RSA-AES128-GCM-SHA256 
- ECDHE-ECDSA-AES256-GCM-SHA384 
- ECDHE-RSA-AES256-GCM-SHA384 
- ECDHE-ECDSA-CHACHA20-POLY1305 
- ECDHE-RSA-CHACHA20-POLY1305 
- DHE-RSA-AES128-GCM-SHA256 
- DHE-RSA-AES256-GCM-SHA384

.. [1]
   Cf.
   https://wiki.mozilla.org/Security/Server_Side_TLS 


   

.. forum_italia::
  :topic_id: 22272
  :scope: document
