Certificati digitali utilizzabili
=================================

Le tecnologie e standard indicate nei precedenti capitoli trovano 
fondamento sull’utilizzo di certificati digitali. In quanto segue si 
riportano le raccomandazioni in merito alla tipologia dei certificati 
digitali e gli object identifier che caratterizzano gli stessi. In 
quanto segue si assume l’applicazione di quanto indicato nelle linee 
guida “Regole Tecniche e Raccomandazioni afferenti la generazione di 
certificati elettronici qualificati, firme e sigilli elettronici 
qualificati e validazioni temporali elettroniche qualificate” [1]_.

.. _certificate-type:
  
Tipologia certificati digitali
------------------------------

La tipologia di certificati digitali da utilizzare è determinata dal 
livello entro cui gli stessi sono utilizzati, nel dettaglio:

- per l’applicazione della sicurezza di canale si utilizzano *Website 
  Authentication Certificates*, detti anche certificati SSL/TLS, che 
  forniscono un metodo per autenticare i server e client coinvolti ed 
  abilitano i meccanismi per crittografare le comunicazioni;

- per l’applicazione della sicurezza a livello applicativo si utilizzano 
  *Electronic Seal Certificates* che identificano il soggetto giuridico 
  a cui il sigillo è associato, abilitando la determinazione dell'origine, 
  della correttezza e dell'integrità dei messaggi oggetto delle interazioni.

Object identifier per l’identificazione delle pubbliche amministrazioni
-----------------------------------------------------------------------

L’utilizzo dei certificati digitali, quale elemento per l’identificazione 
delle pubbliche amministrazioni, è favorito dalla possibilità di 
automatizzare la verifica della persona giuridica a cui il certificato 
è associato. 

Ricordando che la fonte autoritativa dell’elenco delle pubbliche 
amministrazioni è rappresentato dall’elenco di cui all’articolo 6-ter 
del CAD (di seguito IPA), in quanto segue sono riportate le 
raccomandazioni in merito al popolamento degli OID 2.5.4.97 
organizationIdentifier e OID 2.5.4.11 organizationalUnitName attraverso 
cui la controparte ricevente il certificato X.509 può effettuare il 
riscontro sui dati contenuti in IPA. 

OID 2.5.4.97 organizationIdentifier
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

La pubblica amministrazione al momento della generazione del certificato 
X.509 assicura il popolamento dell’OID 2.5.4.97 organizationIdentifier 
nel rispetto della raccomandazione presente nelle “Linee guida contenenti 
le Regole Tecniche e Raccomandazioni afferenti alla generazione di 
certificati elettronici qualificati, firme e sigilli elettronici qualificati 
e validazioni temporali elettroniche qualificate”  in merito ai certificati 
digitali emessi per soggetti giuridici (legal person). 

Nello specifico le indicate Linee guida, coerentemente a quanto disposto 
dal Regolamento eIDAS e nel dettaglio dalla norma ETSI EN‐319‐412‐1, 
prevedono che l’OID 2.5.4.97 organizationIdentifier sia popolato con 
il codice fiscale della persona giuridica a cui il certificato X.509 è 
associato nel rispetto della seguente sintassi:

- CF:IT‐<codice_fiscale> dove <codice_fiscale> è il codice fiscale della 
  persona giuridica.

OID 2.5.4.11 organizationalUnitName
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Nel caso in cui il certificato X.509 sia riferito ad un’unità organizzativa 
o area organizzativa omogenea di una specifica pubblica amministrazione, 
cosi come registrato nell’IPA, la pubblica amministrazione al momento 
della generazione dello stesso certificato assicura, oltre a quanto indicato 
al paragrafo precedente, il popolamento dell’OID 2.5.4.11 organizationalUnitName, 
e nello specifico:

- nel caso di unità organizzativa, IPAIT‐UO_<codice_UO> dove <codice_UO> 
  è il codice IPA dell’unità organizzativa così come risulta dall’IPA;

- nel caso di area organizzativa omogenea, IPAIT‐AOO_<codice_AOO> dove 
  <codice_AOO> è il codice IPA dell’area organizzativa omogenea così 
  come risulta dall’IPA.

Verifica associazione di certificato X.509 ad una pubblica amministrazione
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Il popolamento dei suddetti OID permette di verificare se la persona 
giuridica è una pubblica amministrazione oppure una unità organizzativa 
o area organizzativa omogenea di una specifica pubblica amministrazione. 

La verifica è realizzata attraverso i seguenti passi:

- consultazione dei dati dell’IPA in una delle modalità previste dalla 
  piattaforma che implementa lo stesso IPA;

- nel caso di certificato X.509 associato a una pubblica amministrazione 
  verifica:

    1. la presenza nell’elenco delle amministrazioni dell’IPA del codice 
       fiscale indicato nell’OID 2.5.4.97 organizationIdentifier;

- nel caso di certificato X.509 associato a una unità organizzativa di 
  una specifica pubblica amministrazione verifica:  

    1. la presenza nell’elenco delle amministrazioni dell’IPA del codice 
       fiscale indicato nell’OID 2.5.4.97 organizationIdentifier e 
       recupera il codice IPA dell’amministrazione;

    2. la presenza nell’elenco delle unità organizzative dell’IPA della 
       coppia codice IPA dell'unità organizzativa indicato nell’OID 
       2.5.4.11 organizationalUnitName e codice IPA dell’amministrazione 
       recuperato al passo precedente;

- nel caso di certificato X.509 associato a una area organizzativa 
  omogenea di una specifica pubblica amministrazione verifica: 

    1. la presenza nell’elenco delle amministrazioni dell’IPA del codice 
       fiscale indicato nell’OID 2.5.4.97 organizationIdentifier e recupera 
       il codice IPA dell’amministrazione;

    2. la presenza nell’elenco delle aree organizzative omogenee dell’IPA 
       della coppia codice IPA dell'area organizzativa omogenea indicato 
       nell’OID 2.5.4.11 organizationalUnitName e codice IPA 
       dell’amministrazione recuperato al passo precedente.
    

.. [1]
   Cf.
   https://www.agid.gov.it/sites/default/files/repository_files/regole_tecniche_e_raccomandazioni_v1.1_0.pdf

   

.. forum_italia::
   :topic_id: 22263
   :scope: document
