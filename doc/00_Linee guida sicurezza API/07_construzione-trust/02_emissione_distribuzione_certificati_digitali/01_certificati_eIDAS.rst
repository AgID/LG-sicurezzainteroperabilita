Certificati digitali emessi da CAQ eIDAS
========================================

L’utilizzo di certificati qualificati emessi da Certification Authority 
qualificati ai sensi del Regolamento UE n° 910/2014 del Parlamento 
europeo e del Consiglio del 23 luglio 2014 (di seguito Regolamento 
eIDAS) rappresenta la modalità di emissione dei certificati nell’unione 
europea con prefissati requisiti sicurezza e di interoperabilità.

In tale ipotesi le garanzie e le regole da adottare per l’utilizzo dei 
certificati qualificati emessi sono conformi alle disposizioni del 
Regolamento eIDAS.

Premesso che ai sensi del Regolamento eIDAS, vige il mutuo riconoscimento 
dei certificati qualificati: 

.. list-table:: 
   :widths: 15 40
   :header-rows: 0

   * - **[SIC_API_05]** 
     - Gli Erogatori DEVONO accettare i certificati qualificati emessi 
       da una CAQ eIDAS per autenticare i Fruitori.

   * - **[SIC_API_06]** 
     - Gli Erogatori DEVONO verificare la validità dei certificati 
       qualificati emessi da una CAQ, compresa l’eventuale revoca degli 
       stessi, ad ogni utilizzo da parte dei Fruitori
       (ad esempio per stabilire una sessione TLS).

.. forum_italia::
  :topic_id: 22265
  :scope: document
