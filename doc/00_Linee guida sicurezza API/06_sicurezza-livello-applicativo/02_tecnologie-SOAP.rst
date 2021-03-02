Tecnologia SOAP
===============

il Simple Object Access Protocol (SOAP) è un protocollo basato su XML 
che consente a due applicazioni di comunicare tra loro sul Web. 
Pubblicato come Working Draft dal W3C, SOAP definisce il formato dei 
messaggi che due applicazioni possono scambiarsi utilizzando i protocolli 
Internet, come ad esempio HTTP, per fornire dati e richiedere elaborazioni. 
Il protocollo è indipendente dalla piattaforma hardware e software ed 
è indipendente dal linguaggio di programmazione utilizzato per sviluppare 
le applicazioni comunicanti.

Nel contesto delle tecnologie SOAP, in relazione ai temi oggetto delle 
Linee Guida, si evidenziano le specifiche XML (eXtensible Markup Language), 
XML-canonicalization, XML-signature e WS-security per assicurare la 
sicurezza dei messaggi scambiati.

XML - eXtensible Markup Language
--------------------------------

XML è un linguaggio di markup creato dal World Wide Web Consortium (W3C) 
per definire una sintassi per la codifica dei documenti che sia gli umani 
che le macchine potrebbero leggere. XML si fonda sull’uso di tag che 
definiscono la struttura del documento, nonché il modo in cui il documento 
deve essere memorizzato e trasportato.

XML è definito dal World Wide Web Consortium (W3C) nella raccomandazione 
Extensible Markup Language (XML) 1.0 [1]_, a cui si rimanda per 
approfondimenti.

XML-canonicalization
--------------------

La canonicalizzazione è un metodo per generare una rappresentazione fisica, 
la forma canonica, di un documento XML che tiene conto delle modifiche 
sintattiche consentite dalla specifica XML. In altre parole, indipendentemente 
dalle modifiche che potrebbero essere apportate a un dato documento XML 
in trasmissione, la forma canonica sarà sempre identica, byte per byte. 
Questa sequenza di byte è fondamentale quando si firma un documento XML 
o si verifica la sua firma.

XML-canonicalization è definito dal World Wide Web Consortium (W3C) 
nella raccomandazione Canonical XML Version 1.1 [2]_, a cui si rimanda per 
approfondimenti.

Le Linee Guida include, quale strumento operativo, l’allegato 
“Raccomandazioni in merito agli algoritmi per XML Canonicalization, 
Digest and signature public key SOAP e Digest and signature public key 
REST” in cui sono tabellati anche gli algoritmi di XML-canonicalization. 
In merito al citato all’allegato si ricorda che, cosi come indicato al 
paragrafo 2.2., l’aggiornamento è assicurato attraverso Circolari emanate 
dall’AgID.

XML-signature
-------------

Lo standard XML-signature fornisce un insieme di tecniche per il calcolo 
della firma digitale specifiche per l’utilizzo di documenti XML. 
XML-signature definisce uno schema per la rappresentazione in formato 
XML del risultato di un’operazione di firma digitale. XML Signature è 
stato progettato tenendo in considerazione le caratteristiche peculiari 
del linguaggio XML e le modalità con cui i documenti XML vengono distribuiti 
e recuperati sulla rete Internet.

XML-signature è definito dal World Wide Web Consortium (W3C) nella 
raccomandazione XML Signature Syntax and Processing Version 1.1 , a cui 
si rimanda per approfondimenti.

La Linea Guida include, quale strumento operativo, l’allegato 
“Raccomandazioni in merito agli algoritmi per XML Canonicalization, 
Digest and signature public key SOAP e Digest and signature public key 
REST” in cui sono tabellati anche gli algoritmi di XML-signature. 
In merito al citato all’allegato si ricorda che, cosi come indicato al 
paragrafo 2.2., l’aggiornamento è assicurato attraverso Circolari emanate 
dall’AgID.

XML-encryption
--------------

Insieme a XML-signature, XML-encryption rappresenta la principale 
specifica nell’ambito della sicurezza XML. Lo standard consiste in una 
metodologia flessibile per la cifratura e per la rappresentazione dei 
dati cifrati in formato XML. 

XML-encryption è definito dal World Wide Web Consortium (W3C) nella 
raccomandazione XML Encryption Syntax and Processing Version 1.1 [4]_, 
a cui si rimanda per approfondimenti.

La Linea Guida include, quale strumento operativo, l’allegato 
“Raccomandazioni in merito agli algoritmi per XML Canonicalization, 
Digest and signature public key SOAP e Digest and signature public key 
REST” in cui sono tabellati anche gli algoritmi di XML-encryption. 
In merito al citato all’allegato si ricorda che, cosi come indicato al 
paragrafo 2.2., l’aggiornamento è assicurato attraverso Circolari emanate 
dall’AgID.

WS-security
-----------

Web Services Security (WS-Security) è una suite di standard che 
descrivono i meccanismi per fornire la protezione dei messaggi SOAP 
attraverso l'integrità dei messaggi, la riservatezza dei messaggi e 
l'autenticazione di un singolo messaggio.  WS-Security è uno standard 
a livello di messaggio basato sulla protezione dei messaggi SOAP tramite 
XML-signature, riservatezza tramite XML-encryption e propagazione delle 
credenziali tramite token di sicurezza. WS-Security descrive come 
codificare i token di sicurezza binari e allegarli ai messaggi SOAP, 
in particolare, le specifiche relative ai profili WS-Security descrivono 
come codificare i seguenti token: 

- certificati X.509;
- asserzioni SAML. 

La suite WS-security è definito dalla Organization for the Advancement 
of Structured Information Standards (OASIS) tra cui segnaliamo: 

- WS-Security SOAP Message Security 1.1 [5]_;
- X.509 Token Profile 1.1 [6]_; 
- SAML Token Profile 1.1 [7]_.


.. [1]
   Cf.
   https://www.w3.org/TR/xml/

.. [2]
   Cf.
   https://www.w3.org/TR/xml-c14n11/

.. [3]
   Cf.
   https://www.w3.org/TR/xmldsig-core1/

.. [4]
   Cf.
   https://www.w3.org/TR/xmlenc-core1/

.. [5]
   Cf.
   https://www.oasis-open.org/committees/download.php/16790/wss-v1.1-spec-os-SOAPMessageSecurity.pdf

.. [6]
   Cf.
   https://www.oasis-open.org/committees/download.php/16785/wss-v1.1-spec-os-x509TokenProfile.pdf

.. [7]
   Cf.
   https://www.oasis-open.org/committees/download.php/16768/wss-v1.1-spec-os-SAMLTokenProfile.pdf
