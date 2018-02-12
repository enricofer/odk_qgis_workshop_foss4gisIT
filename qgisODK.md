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

---

## ODK collect app

![odk collect app](./doc/15-odk-collect0.png)

---

## Enketo webapp

![Enketo webapp](./doc/enketo01.png)

---

## Aggregazione delle informazioni (aggregate)

- Le informazioni raccolte nei dispositivi mobili vengono trasferiti al server di aggregazione in presenza di connesione di rete
- Ad ogni modulo corrisponde un record nel server di aggregazione
- Nel server di aggregazione risiedono anche i modelli Xform dei moduli di compilare e viene mantenuta la relazione tra modulo e database

---

## Server di aggregazione

Applicazioni:
- Odk aggregate: https://opendatakit.org/use/aggregate/
- Formhub: https://github.com/SEL-Columbia/formhub
Servizi:
- Google Drive
- Ona.io
- Formhub (American Red Cross)
- surveyCTO

---

## Funzionalità di QgisODK

- Generare il modulo da inserire nel flusso ODK direttamente da un layer sorgente di QGIS adattando i tipi di dati di QGIS ai tipi ODK
- Riorganizzare i campi per la raccolta in loco
- Trasferire i moduli  ad una piattaforma ODK
- Sincronizzare i dati raccolti con il layer sorgente

---

## I  “field widget” di QGIS

![Enketo webapp](./doc/0-qgis-props-fields.png)

---

## I tipi ODK

![Enketo webapp](./doc/enketo01.png)

---

## I tipi ODK 1

| Question type  | Answer input  |
| -------------- | ------------- |
| integer        | Integer (i.e., whole number) input. |
| decimal        | Decimal input. |
| text | Free text response.</td> |
| select_one [options] | Multiple choice question; only one answer can be selected. | 
| select_multiple [options] | Not supported by QgisODK plugin. |
| note | Not supported by QGISODK plugin | 
| geopoint | Collect a single GPS coordinates. |
| geotrace | Record a line of two or more GPS coordinates. |
| geoshape | Record a polygon of multiple GPS coordinates; the last point is the same as the first point.|

---

## I tipi ODK 2

| Question type  | Answer input  |
| -------------- | ------------- |
| date | Date input. | 
| time | Time input. | 
| dateTime | Accepts a date and a time input. |
| image | Take a picture. | 
| audio | Take an audio recording. | 
| video | Take a video recording. | 
| barcode | Scan a barcode, requires the barcode scanner app to be installed. | 
| calculate | Not supported by QGISODK plugin | 
| acknowledge| Not supported by QGISODK plugin | 