Certificati digitali emessi all’interno di domini di interoperabilità specifici
-------------------------------------------------------------------------------

Nell'ambito di un dominio di interoperabilità i soggetti afferenti in 
alternativa a quanto indicato al [5.2.1. Certificati digitali emessi da 
CAQ eIDAS] possono individuare tra essi uno o più soggetti abilitati 
all’emissione di certificati digitali (di seguito CA del dominio di 
interoperabilità).

La costituzione del trust è formalizza dalle regole del dominio di 
interoperabilità in cui sono definite:

- Il dettaglio implementativo dei processi indicati ai successivi 
  paragrafi [5.1.2.1. OID 2.5.4.97 organizationIdentifier], 
  [5.1.2.2. OID 2.5.4.11 organizationalUnitName] e 
  [5.1.2.3. Verifica associazione di certificato X.509 ad una pubblica amministrazione];
- Le modalità con cui i soggetti afferenti al dominio di interoperabilità 
  (di seguito soggetto richiedente) inoltrano alla CA del dominio di 
  interoperabilità la richiesta di emissione di un certificato;
- Le verifiche che la CA del dominio di interoperabilità per 
  l’identificazione del soggetto richiedente;
- Le modalità con cui la CA del dominio di interoperabilità inoltra il 
  certificato firmato al soggetto richiedente e, più in generale, le 
  modalità con cui i certificati digitali emessi sono distribuiti ai 
  soggetti afferenti il dominio di interoperabilità.

  .. list-table:: 
   :widths: 15 40
   :header-rows: 0

   * - **[API_SIC_07]** 
     - I soggetti afferenti ad un dominio di interoperabilità che rendono 
       disponibili API DEVONO accettare i certificati digitali emessi 
       da una CA del dominio di interoperabilità per autenticare gli 
       altri soggetti utilizzatori delle stesse API.

   * - **[API_SIC_08]** 
     - I soggetti che rendono disponibili API DEVONO verificare la 
       validità dei certificati digitali emessi da una CA del dominio 
       di interoperabilità, compreso l’eventuale revoca degli stessi, 
       per ogni invocazione da parte di soggetti delle stesse API per 
       cui è abilitato l’accesso.