Tecnologia REST
===============

REST individua, accettando il livello 1 del Richardson Maturity Model 
[1]_, una modalità per implementare servizi basati sul protocollo HTTP 
che operano sulle risorse definite secondo la sintassi e la semantica 
previste per le URI e, sulle quali, si opera invocando delle operazioni 
(HTTP method) che agiscono su di esse. Il MODI include tale tecnologia 
per l’implementazione delle API.

Nel contesto delle tecnologie REST, in relazione ai temi oggetto delle 
Linee Guida, si evidenziano le specifiche JSON-based JWT (JSON Web Token), 
JWS (JSON Web Signatures), JWK (JSON Web Key), JWE (JSON Web Encryption) e 
JWA (JSON Web Algorithms) per assicurare la sicurezza dei messaggi scambiati 
tramite API REST. 

JSON - JavaScript Object Notation
---------------------------------

JSON è un formato di interscambio di dati leggero, basato su testo e 
indipendente dal linguaggio di programmazione.

JSON è basato su due strutture:

- gli oggetti, cioè una serie non ordinata di nomi/valori 
- gli array, cioè una raccolta ordinata di valori
  
Dove i valori possono essere stringhe, numeri, valori booleani (true/false), 
oggetti o array.

JSON è definito dall’Internet Engineering Task Force nell’:rfc:`8259` [2]_, 
a cui si rimanda per approfondimenti.

Come tutti i formati di interscambio general-purpose
e che permettono l'utilizzo di strutture nidificate,
in alcuni ambiti può essere opportuno limitare l'espressività della notazione
(eg. limitando il numero di oggetti nidificati in fase di processamento o di serializzazione).
Si veda a questo riguardo :rfc:`7493`, che definisce un sottoinsieme interoperabile di JSON
e che include tra l'altro raccomandazioni su:

- unicode code points da evitare;
- quando serializzare numeri in formato di stringa;
- accortezze riguardo la gestione di chiavi duplicate.

Per casi d'uso specifici come gli header HTTP,
sono di recente stati creati di recente formati di serializzazione appositi
con delle librerie di processamento e serializzazione dedicate:
si veda Structured Field Values for HTTP :rfc:`8941`.


JWS - JSON Web Signature
------------------------

JWS rappresenta il contenuto firmato utilizzando strutture dati JSON e 
codifica base64url. 

La serializzazione compatta, la rappresentazione maggiormente utilizzata, 
è composta da tre parti: 

- JWS Header, descrive il metodo di firma e i parametri utilizzati;
- JWS Payload, il contenuto del messaggio da proteggere;
- JWS Signature, garantisce l'integrità del JWS Header e del JWS Payload;

ed è rappresentata dalla concatenazione:

.. code-block:: http

   BASE64URL(UTF8(JWS Header)) ||'.' || BASE64URL(JWS Payload) || '.' || BASE64URL(JWS Signature)

Quando si firma un messaggio, si DEVONO prendere in considerazione una 
serie di possibili minacce, tra cui:
- la contraffazione delle firme o l'alterazione del contenuto;
- errati processi di validazione e verifica;
- il riuso non autorizzato di messaggi firmati.
Questo è particolarmente importante quando si utilizzano JWS nei processi di autenticazione o autorizzazione.
JWS è definito dall’Internet Engineering Task Force nell’:rfc:`7515` [3]_, 
a cui si rimanda per approfondimenti.

JWK - JSON Web Key
------------------------

JWK definisce delle strutture dati per rappresentare
una o più chiavi crittografiche associate a dei Json Web Algorithm,
a supporto dei meccanismi di firma definiti in JWS
o di cifratura definiti in JWE.

La specifica supporta sia chiavi associate ad algoritmi
simmetrici che asimmetrici, chiavi pubbliche e chiavi private.
Permette inoltre di rappresentare eventuali certificati associati
alle chiavi.

I tipi di chiavi supportate sono indicate nel
`JSON Object Signing and Encryption (JOSE) IANA Registry <https://www.iana.org/assignments/jose>`_
che viene periodicamente aggiornato
(eg. :rfc:`8037` ha aggiunto il supporto per l'algoritmo Ed25519).

JWK è definito dall’Internet Engineering Task Force nell’:rfc:`7517`,
a cui si rimanda per approfondimenti.


JWE - JSON Web Encryption
-------------------------

JWE rappresenta il contenuto crittografato utilizzando strutture dati 
JSON e codifica base64url.

La serializzazione compatta, la rappresentazione maggiormente utilizzata, 
è composta da cinque parti:

- JWE Header, descrive il metodo di cifratura e i parametri utilizzati;
- JWE Encrypted Key, valore della chiave di crittografia del contenuto 
  crittografato;
- JWE Initialization Vector, vettore di inizializzazione utilizzato 
  durante la crittografia del testo;
- JWE Ciphertext, testo cifrato risultante dalla crittografia;
- JWE Authentication Tag, valore del tag di autenticazione risultante 
  dalla crittografia autenticata del testo in chiaro;
  
ed è rappresentata dalla concatenazione:

.. code-block:: http

   BASE64URL(UTF8(JWE Header)) || '.' || BASE64URL(JWE Encrypted Key) || '.' || BASE64URL(JWE Initialization Vector) || '.' || BASE64URL(JWE Ciphertext) || '.' || BASE64URL(JWE Authentication Tag)

JWE è definito dall’Internet Engineering Task Force nell’:rfc:`7516` [4]_, 
a cui si rimanda per approfondimenti.

JWT - JSON Web Token
--------------------
JWT veicola asserzioni da trasmettere (JWT Claims Set) utilizzando 
strutture JSON e codificando in base64url. I JWT sono firmati digitalmente
e/o crittografati rispettivamente utilizzando JWS e JWE. 

Il JOSE Header contiene le operazioni crittografiche applicate al
JWT Claims Set:

- in un JWS, esso indica come è stato firmato il JWT Claims Set incluso 
  nel JWS Payload;
- in un JWE, indica come è stato cifrato il JWT Claims Set incluso nel 
  JWE Ciphertext.

Un JWT può anche prevede la possibilità di essere racchiuso in un'altra 
struttura JWE o JWS per creare un JWT annidato, consentendo l'esecuzione 
della firma e della crittografia annidate.
JWT è definito dall’Internet
Engineering Task Force nell’:rfc:`7519` [5]_, a cui si rimanda per approfondimenti.

I JWT DEVONO essere usati rispettando le indicazioni di sicurezza indicate in :RFC:`8725`.


JWA - JSON Web Algorithms
-------------------------

JWA individua gli algoritmi crittografici da utilizzare con le specifiche 
JWS e JWE. 

JWA è definito dall’Internet Engineering Task Force nell’:rfc:`7518` [6]_, 
a cui si rimanda per approfondimenti.

Le Linee Guida include, quale strumento operativo, l’allegato 
"Raccomandazioni in merito agli algoritmi per XML Canonicalization, 
Digest and signature public key SOAP e Digest and signature public key 
REST" in cui sono tabellati anche gli algoritmi crittografici individuati 
in JWA. In merito al citato all’allegato si ricorda che, così come 
indicato al paragrafo :ref:`structure`, l’aggiornamento è assicurato 
attraverso Circolari emanate dall’AgID.

OAuth 2.0
---------

OAuth 2.0 è un protocollo che consente alle applicazioni di accedere 
alle risorse protette di un servizio per conto di un soggetto e permette 
di proteggere risorse HTTP come un'API REST. 

OAuth 2.0 prevede per ogni ruolo un compito ben definito, permettendo 
una più robusta sicurezza dell'architettura di autorizzazione.

- Resource Owner: è il proprietario dell'informazione esposta via HTTP.
- Client: è l'applicazione autorizzata dal Resource Owner che richiede 
  l'accesso alla risorsa HTTP.
- Authorization Server: è il modulo che firma e rilascia i token di accesso.
- Resource Server: è il server che detiene l'informazione esposta via HTTP.
  
Un Grant Type è il processo da seguire per ottenere il cosiddetto 
Authorization Grant, ovvero la prova inoppugnabile che il Resource Owner 
ha autorizzato l'applicazione Client ad accedere ad una risorsa protetta. 
OAuth 2.0 definisce 4 Grant Type: Authorization Code Grant Type, Implicit 
Grant Type, Resource Owner Password Credentials Grant Type e Client 
Credentials Grant Type.

OAuth 2.0 è definito dall’Internet Engineering Task Force nell’:rfc:`6749` [7]_, 
a cui si rimanda per approfondimenti.

Visto che il contesto di interesse è machine-to-machine, dei suddetti 
Grant Type sono applicabili il Resource Owner Password Credentials e 
il Client Credentials. 

Il Grant Type Resource Owner Password Credentials comporta la cessione 
a terzi delle credenziali, quindi NON DEVE essere usato.

.. [1]
   Cf.
   https://martinfowler.com/articles/richardsonMaturityModel.html

.. [2]
   Cf.
   https://tools.ietf.org/html/rfc8259

.. [3]
   Cf.
   https://tools.ietf.org/html/rfc7515

.. [4]
   Cf.
   https://tools.ietf.org/html/rfc7516

.. [5]
   Cf.
   https://tools.ietf.org/html/rfc7519

.. [6]
   Cf.
   https://tools.ietf.org/html/rfc7518

.. [7]
   Cf.
   https://tools.ietf.org/html/rfc6749


.. forum_italia::
   :topic_id: 22260
   :scope: document
