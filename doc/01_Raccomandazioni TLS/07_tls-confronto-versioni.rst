TLS 1.2 vs TLS 1.3 versioni a confronto
=======================================

Il protocollo TLS 1.3 è stato definito in RFC 8446 [1]_ nell'agosto 2018 ed 
è più sicuro e veloce rispetto a TLS 1.2 RFC 5246 [2]_. Le principali 
differenze includono:

- L'elenco degli algoritmi simmetrici supportati è stato epurato da 
  tutti gli algoritmi legacy. Gli algoritmi rimanenti utilizzano 
  algoritmi di crittografia autenticata con dati associati (AEAD) 
  come ad esempio ChaCha20, Poly1305, Ed25519, x25519 e x448.

- È stata aggiunta una modalità zero-RTT (0-RTT) che elimina un 
  round-trip durante la fase di configurazione della connessione.

- Le suite di cifratura statiche RSA e Diffie-Hellman sono state 
  rimosse.

- Tutti i messaggi di handshake dopo “ServerHello” sono ora cifrati.

- Le funzioni di derivazione delle chiavi sono state ri-progettate, con 
  la funzione di derivazione delle chiavi di estrazione ed espansione 
  basata su HMAC (HKDF) utilizzata come primitiva.

- Gli stati dell’handshake sono stati ristrutturati per essere più 
  coerenti e sono stati rimossi i messaggi superflui. 

- ECC è ora nelle specifiche di base del TLS 1.3 e include nuovi 
  algoritmi di firma. 

- Sono stati inoltre apportati altri miglioramenti crittografici, tra cui:
  
    - la modifica del Padding RSA al fine di utilizzare lo schema RSA 
      Probabilistic Signature Scheme (RSASSA-PSS) definito da RFC 8017;

    - la rimozione della compressione, dell'algoritmo di firma digitale 
      (DSA) e dei gruppi Ephemeral Diffie Hellman (DHE) personalizzati.

- Il meccanismo di verifica della negoziazione della versione di TLS 
  1.2 è stato deprecato a favore di una lista di versioni gestite 
  attraverso l’utilizzo di estensioni.

- La ripresa della sessione con e senza stato lato server e le 
  ciphersuite basate su PSK delle versioni precedenti di TLS sono state 
  sostituite da un unico nuovo scambio di chiavi PSK.

- In generale la direzione adottata da TLS 1.3 è verso algoritmi che 
  garantiscano la PFS.

Come rappresentato nella seguente figura, per il TLS 1.2 sono necessari 
due round trip per completare l’handshake del TLS. La versione TLS 1.3 
richiede un solo round-trip, che a sua volta diminuisce la latenza della 
crittografia. Si ottiene quindi un risparmio medio di tempo 
sull’handshake consentendo connessioni cifrate più veloci. 

Inoltre, i meccanismi come TLS False Start e Zero Round Trip Time (0-RTT) 
del TLS 1.3 consentono di ridurre ulteriormente il tempo richiesto per 
l’handshake con gli host ai quali il client si è già collegato in 
precedenti sessioni. 

Infine, TLS 1.3 offre una maggiore protezione contro i cosiddetti 
“downgrade attacks” ovvero i tentativi posti in essere da parte di un 
attaccante per indurre il server all'utilizzo di una vecchia versione 
del protocollo TLS soggetta a vulnerabilità note.



.. [1]
   Cf.
   https://tools.ietf.org/html/rfc8446

.. [2]
   Cf.
   https://tools.ietf.org/html/rfc5246
