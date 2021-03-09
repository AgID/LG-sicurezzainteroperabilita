Costituzione trust tra soggetti interessati
===========================================

Le tecnologie da utilizzare indicate in precedenza fanno uso della 
crittografia asimmetrica.

Nel contesto della crittografia asimmetrica lo standard di riferimento 
è rappresentato dall’ITU-T X.509 che definisce il formato dei certificati 
a chiave pubblica (di seguito certificati digitali) e delle autorità di 
certificazione.

La fiducia delle interazioni erogatore-fruitore è assicurata dalla 
costituzione di un trust tra essi al fine di riconoscere la validità 
dei certificati digitali utilizzati per assicurare la sicurezza delle 
comunicazioni realizzate tramite API.

In quanto segue si individuano le tipologie e le caratteristiche dei 
certificati digitali per applicare le tecnologie indicate in precedenza 
e, non di meno, i possibili modelli di emissione e distribuzione degli 
stessi certificati raccomandati per la costituzione dei trust tra 
erogatori e fruitori.

.. list-table:: 
   :widths: 15 40
   :header-rows: 0

   * - **[SIC_API_03]** 
     - I soggetti destinatari DOVREBBERO utilizzare le tipologie dei 
       certificati digitali e, per essi, assicurare il popolamento degli 
       object identifier indicati al paragrafo :ref:`certificate-type`.

   * - **[SIC_API_04.a]** 
     - I soggetti destinatari DOVREBBERO utilizzare le modalità di 
       emissione e distribuzione dei certificati digitali indicati ai 
       paragrafi :ref:`Certificati digitali emessi da CAQ eIDAS` e 
       :ref:`Certificati digitali emessi all’interno di domini di interoperabilità specifici`.

   * - **[SIC_API_04.b]** 
     - I soggetti destinatari DEVONO considerare i principi indicati 
       al paragrafo :ref:`Principi per la scelta delle modalità di emissione dei certificati digitali` 
       per la determinazione delle modalità di emissione e distribuzione 
       dei certificati digitali.

|

.. toctree::
   :maxdepth: 4

   07_construzione-trust/01_certificati_digitali_utilizzabili.rst
   07_construzione-trust/02_emissione_distribuzione_certificati_digitali.rst

   

.. forum_italia::
  :topic_id: 22262
  :scope: document
