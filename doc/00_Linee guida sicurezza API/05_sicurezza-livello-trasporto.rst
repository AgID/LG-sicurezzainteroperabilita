Sicurezza a livello di trasporto
================================

Al fine di garantire autenticazione, integrità dei dati e confidenzialità 
tra ente fruitore, le comunicazioni DEVONO avvenire utilizzando il 
protocollo di comunicazione HTTPS (HTTP over TLS). 

Il Transport Layer Security (TLS) è un protocollo che permette di 
stabilire un canale con le proprietà di integrità e riservatezza in senso 
crittografico tra un client e un server. Dopo aver stabilito una 
connessione sicura tramite il protocollo TLS, le applicazioni possono 
utilizzarla per scambiare dati. TLS viene utilizzato in molteplici 
contesti applicativi come ad esempio HTTPS, SMTPS, e altri ancora.

I requisiti crittografici minimi per stabilire una connessione sicura, 
riguardanti la versione del protocollo TLS e le cipher suite da utilizzare 
sono contenuti nell’allegato “Raccomandazioni in merito allo standard 
Transport Layer Security (TLS)”.

Data la continua evoluzione tecnologica e la possibile scoperta di nuove 
vulnerabilità, l’allegato “Raccomandazioni in merito allo standard 
Transport Layer Security (TLS)” verrà aggiornato periodicamente nei 
modi indicati al paragrafo :ref:`structure`. 

In caso di evidenza di vulnerabilità di nuova scoperta che richiedano 
un intervento immediato in merito alle indicazioni fornite nell’allegato 
“Raccomandazioni in merito allo standard Transport Layer Security (TLS)” 
verranno emanati specifici avvisi di sicurezza. 

.. list-table:: 
   :widths: 15 40
   :header-rows: 0

   * - **[SIC_ API_01]** 
     - I soggetti destinatari DEVONO utilizzare la versione TLS e le 
       cipher suite indicate nell’allegato “Raccomandazioni AgID in 
       merito allo standard Transport Layer Security (TLS)”.


.. forum_italia::
       :topic_id: 22258
       :scope: document
