QgisODK
===

FOSS4G Italia 2018 - ROMA

Raccolta in loco di informazioni a contenuto geospaziale con Open Data Kit (ODK) e QGIS 

Enrico Ferreguti – enricofer@gmail.com

https://opendatakit.org/
https://github.com/enricofer/QgisODK/

---

## ODK

- E’ sviluppato dall’università di Seattle
- E’ completamente basato su strumenti e tecnologie opensource
- E’ finalizzato a:
  - Raccogliere informazioni in modo semplice con l’ausilio di dispositivi mobili, anche in mancanza di connessioni stabili di rete
  - Aggregare le informazioni raccolte da molti utenti e pubblicarle

---

## Come si utilizza

- Un indagine ODK è tipicamente basata sulle seguenti attività:
  - Progetto delle informazioni da raccogliere  (build)
  - Raccolta dei dati sul campo (collect)
  - Aggregazione dei dati raccolti (aggregate)
- ODK non è un applicazione, ma un ecosistema di applicazioni orientare a queste attività

---

## Il Flusso ODK

![flusso](https://camo.githubusercontent.com/76d406ed2647972ef7b84bfc1f344db2c3b0287e/687474703a2f2f70726f6772616d732e676f6f6472657475726e2e6f72672e61752f77702d636f6e74656e742f75706c6f6164732f73697465732f31352f323031352f30352f4f444b2d50726f636573732d4e65772d31303234783537362e706e67)

---


## Progetto delle informazioni  (build)

- Le informazioni da raccogliere sono organizzate in moduli secondo lo standard Xform (XML)
- Per la progettazione della form, ODK mette a disposizione lo strumento build: https://build.opendatakit.org/
- In alternativa il contenuto informativo può essere definito con un XlsForm, ovvero un foglio di excel opportunamente compilato traducibile in Xform. http://xlsform.org/

---

## Xform con ODK build

![odk build](./doc/odk_build.png)

---

## Xform da XlsForm

- Foglio di excel ha dei contenuti minimi obbligatori ed altri opzionali
- Contenuti minimi obbligatori:
  - Foglio survey con almeno 3 colonne: type, name, label
- Altri contenuti:
  - Foglio choices per campi categorizzati
  - Foglio settings per settaggio personalizzati del foglio
  - Altre colonne opzionali nel foglio survey (constraint, appearance, etc) con cui guidare l’inserimento delle informazioni
  
  ---
  
## Xform da XlsForm

![odk build](./doc/xls_form_example1.png)

---

## Raccolta dati (collect)

- La raccolta dati viene effettuato con un dispositivo mobile senza la necessità di connessione di rete
- La raccolta avviene in tre fasi:
 - Scelta del modulo dati da compilare
 - Compilazione delle rilevazioni (entries)
 - Sincronizzazione delle rilevazioni sul server di aggregazione
- Gli strumenti ad disposizione sono:
 - ODK collect (android app) google play store
 - Enketo webapp https://enketo.org/
