---
title: "PAI"
sidebarTitle: "PAI"
---

<Warning>
  I PAI riguardano solo la Lombardia
</Warning>

## 1. Introduzione

In Regione Lombardia, la Presa In Carico del paziente cronico (PIC) è un percorso pensato per offrire cure più organizzate, continue e personalizzate.

Il medico di famiglia redige per ogni paziente un **Piano Assistenziale Individuale (PAI)**, che raccoglie al suo interno tutte le prestazioni da effettuare nell'arco di un anno, insieme alle prescrizioni farmacologiche per la cura della patologia.

**Per compilare e pubblicare un PAI** (Piano Assistenziale Individuale) sul Fascicolo Sanitario Elettronico del paziente, un medico di medicina generale deve disporre di un **software** abilitato (es. **Elty**) ed essere socio di una **cooperativa** accreditata come Gestore PAI (es. **Horus Medica**). Un medico singolo, non affiliato a una cooperativa con questo ruolo, non può pubblicare un PAI in autonomia.

Questo perché la cooperativa ricopre anche una funzione fondamentale: quella di **Centro Servizi**, incaricato di supportare i pazienti presi in carico. In particolare, il Centro Servizi ha il compito di contattare i pazienti per organizzare le prestazioni previste nel PAI e fornire loro gli appuntamenti necessari.

Il principale vantaggio di utilizzare lo stesso strumento sia come cartella clinica elettronica sia per la gestione della presa in carico del paziente consiste nell'avere già integrate tutte le informazioni relative a stile di vita, patologie, prestazioni, farmaci e vaccinazioni. In questo modo, la compilazione del PAI risulta in gran parte automatizzata.

### Termini e requisiti per fare PAI con noi

<Info>
  Documento con i termini e requisiti per i medici: https://drive.google.com/file/d/1GQy-8OTWh5mv-lqCdTLhTMVN4zqIJ8pO/view
</Info>

**PAI = Piano Assistenziale Individuale** composto da:

- **Patologia primaria** (+ eventuali **patologie secondarie** → aumenta "livello/complessità" del PAI)
- **Prestazioni** (le **prestazioni ambulatoriali sono quelle che vengono prenotate**)
- **Farmaci**
- **Stile di vita** (obbligatorio)
- **Vaccinazioni** (non obbligatorie)

Ogni **ATS** ha un elenco di patologie ammesse come **primarie** → se esce un errore, spesso questo si risolve cambiando la patologia primaria.

## 2. Sezioni PAI in scheda paziente:

### **Sezione PAI in scheda paziente**

- **Stato del PAI**
  - La % di completamento presente in scheda paziente e nella sezione PAI indica soltanto se è stato inserito almeno un elemento relativo a quell'area specifica, obbligatoria per la creazione e pubblicazione del PAI.
- **Aderenza terapeutica** (per ora intesa come "visite prescritte"/ricette emesse)
- **Lista PAI vecchi** pubblicati/scaricati

Qui si fa il lavoro operativo sul singolo:

- Arruolamento / crea PAI / pubblica / rinnova / modifica / scarica / importa / ricette

**Arruolamento** = presa in carico / "patto di cura" tra medico–paziente–cooperativa–Regione.

- Il sistema fa la **verifica arruolabilità** (PAI già presente in Regione? paziente arruolato con altro medico?).
- In arruolamento: possibilità di scaricare **2 PDF patti di cura** precompilati (medico + paziente).
  - Spesso l'arruolamento è fatto in **asincrono** (firma dei patti dopo).
  - In passato serviva la tessera sanitaria fisica → ora **non più necessario** (arruolamento più facile perché asincrono).

**Ricette**: è cambiata la delibera → le ricette ora sono valide **6 mesi** (non 12)

- Abbiamo introdotto una scelta:
  - Prescrivi primo lotto
  - Prescrivi secondo lotto
  - Prescrivi tutto
- Aiutiamo il medico a ricordare se le ricette sono state già emesse.

## 3. Sezione globale PAI

Nella sezione PAI globale è possibile vedere in modo immediato quanti pazienti cronici arruolabili ha il medico, quanti arruolati ma senza PAI ecc.

- È composta da 3 elementi (sezioni):
  - **Tutti** (i pazienti)
  - **Arruolabili** (mostra pazienti "cronici" arruolabili)
  - **Pubblicati** (con indicatori come "visite prescritte")

Tramite i pulsanti d'azione è possibile visualizzare e modificare il PAI selezionato.

Nella gestione PAI sarà possibile anche verificare:

- Se è presente un PAI per quel paziente sul fascicolo sanitario elettronico e importarlo in Elty direttamente dalla sezione PAI
- Se il paziente risulta in carico ad un altro medico o un altra cooperativa e deve essere disarruolato.

## 4. Arruolamento (presa in carico)

1. Medico entra in **Sezione PAI** del paziente (o da globale).
2. Clicca **"Arruola"**.
3. Si apre un **pop-up di verifica arruolamento**:
   - Controllo su sistemi Regione: paziente già con PAI? già arruolato altrove?
4. Se OK → conferma arruolamento.

**Output dell'arruolamento:**

- Il medico può scaricare i **patti di cura (2 PDF)**:
  - Precompilati con **nome/cognome medico** e **nome/cognome paziente**.
- Anche dopo, i patti di cura dovrebbero essere recuperabili dai **"tre puntini"** (menu azioni).

**"Crea PAI" e precompilazione**

- Dopo l'arruolamento, il sistema mostra **"Crea PAI"** e un indicatore come **CREA PAI 100%**
  - La percentuale è calcolata in base a presenza in cartella di:
    - patologie croniche
    - farmaci
    - prestazioni
    - stile di vita
    - vaccinazioni
  - Basta anche solo 1 per far salire la %

> Importante: è una completezza di dati, non è una verifica clinica (non può sapere se le prestazioni sono "tutte quelle giuste" per patologia).

**Schermata "Epilogo PAI"**

Quando clicchi **Crea PAI** arrivi a una schermata di review con:

- **Patologia primaria + secondarie**
  - Puoi modificare, aggiungere, rimuovere
  - Più patologie → aumenta livello/complessità → maggiore remunerazione
- **Esenzioni / allergie**
- **Vaccinazioni** (visiona + aggiungi eventuali da fare)
- **Stile di vita** (obbligatorio)
- **Prestazioni**
- **Farmaci**

**Prestazioni:**

- Campo fondamentale: **periodicità** (ogni quanto va fatta la prestazione).
- Il sistema mette una periodicità di default ma:
  - si può modificare singolarmente
  - si possono fare **modifiche massive** (periodicità + note)

**Regola "\>12 mesi"**

- Le prestazioni con periodicità **maggiore di 12 mesi**:
  - Vengono inserite nei **PAI successivi** (non sempre nello stesso anno)
  - Il sistema "si ricorda" la cadenza (esempio: un anno sì / un anno no)

**Pacchetti prestazioni**

- Consiglio: usare i **pacchetti prestazioni** (pensati anche "principalmente per i PAI", oltre che per ricette).

## 5. Pubblicazione PAI (FSE) e cosa succede subito dopo

### **Pubblicazione**

- Pubblicando il PAI:
  - viene creato un **PDF**
  - viene pubblicato come **referto su Fascicolo Sanitario Elettronico (FSE)**
  - può essere scaricato
  - (in app) il paziente vede "**Il mio piano di cura**" con prestazioni del PAI

**Email automatica al paziente**

- Dopo pubblicazione (o rinnovo) parte:
  - **email al paziente** con **PDF allegato**
  - testo: la cooperativa (**Horus Medica**) gestirà prenotazioni e ricontatterà
- **Situazione attuale**:
  - Se manca email/contatti paziente → non viene inviato nulla
  - Verrà introdotto un **popup per inserire email/contatto** se mancante (chiedere al medico al momento dell'invio)

### Ricette dal PAI (post-pubblicazione)

Dopo pubblicazione:

- Appare popup "pubblicazione su FSE"
- Poi popup "elaborazione ricette": **vuoi elaborare già le ricette del PAI?**
- Puoi sempre farlo dopo da:
  - sezione PAI / azioni del PAI / pulsante "Prescrivi ricette"

### Scelta lotti (6 mesi)

Quando clicchi "prescrivi ricette":

- popup con scelta:
  - **primo lotto**
  - **secondo lotto**
  - **tutto**
    - Motivo: le ricette ora sono di 6 mesi → serve la gestione in due tranche.
- "Aderenza" (come viene mostrata oggi)
  - È chiamata "aderenza", ma oggi significa:
    - **Quante prestazioni hanno ricetta emessa** (visite prescritte)

### Alert di modifiche post-pubblicazione

Se dopo la pubblicazione cambi dati in scheda paziente:

- Compare un **banner/alert**:
  - Sono state apportate modifiche dopo la pubblicazione… clicca modifica per aggiornare
- Aggiornando e ripubblicando:
  - È un **aggiornamento** su FSE (non "succede niente di rischioso", è un refresh)

**Regole sui farmaci (dettaglio)**

- Se cambia **posologia** di un farmaco già esistente → **NON appare** il banner.
- Se **aggiungi un nuovo farmaco** → **appare** il banner.

**Email in caso di modifica**

- Oggi: email paziente inviata **solo** su pubblicazione/rinnovo, **non** su modifica.
- In app: si aggiorna, ma il paziente potrebbe non accorgersene.

## 6. Scarica PAI da FSE (singolo) + Azioni (tre puntini)

Da scheda paziente → sezione PAI:

- **Scarica PAI** (come scaricare un referto)
- poi nel menu azioni (tre puntini) puoi vedere:
  - **Visualizza PAI**
  - **Compila aderenza terapeutica**
  - **Importa dati in scheda paziente**
  - **Prescrivi ricette**
  - Recupero **patti di cura** (se arruolato)

### Importa dati in scheda paziente (strutturato)

Dopo "Importa dati":

- Schermata lista dati PAI con possibilità di:
  - **Includere/escludere** (icona cestino per eliminare ciò che non vuoi importare)
- Cosa importiamo:
  - **Prestazioni** (strutturate)
  - **Patologie** (strutturate)
- Farmaci:
  - Da Regione arrivano come **principi attivi** (non nome commerciale/posologia)
  - Quindi import farmaci è meno utile → se serve, va fatto manualmente.

## 7. Funzioni massive (solo con firma in cloud)

**Prerequisito chiave**

- I pulsanti "massivi" sono **abilitati solo se loggato in cloud** (firma in cloud).
- Con **smart card**: alcune azioni massive non funzionano.

### A) Verifica PAI da FSE (massivo)

Pulsante: **"Verifica PAI da FSE"**

- Fa una scansione sui pazienti e:
  - controlla chi ha già un PAI
  - scarica **l'ultima versione disponibile**
  - marca il paziente come cronico
  - importa patologie in cartella
- Non ci sono ancora tempi certi per grandi volumi → Potrebbe volerci un po' di tempo

### B) Pubblica tutto (massivo)

- Selezioni più pazienti → **"Pubblica tutto"**
- Limite: **firma uno a uno** (non può essere "un click unico" per vincoli di firma).

### C) Rinnovo massivo

- Non "rinnova e pubblica tutto"
- Crea **bozze di rinnovo** per velocizzare:
  - apri bozza → eventuale modifica → pubblichi → passi alla successiva

## 8. Ruoli cooperativa / attivazione medici (**Horus Medica** vs IML)

- Alcune sezioni PAI sono visibili **solo ai medici Horus Medica**.
- Flusso per passare da **IML → Horus Medica**:
  1. Medico ex **IML**: fa **disarruolamento massivo** (banner dedicato per il disarruolamento massivo)
     - Quando li disarruoli, vai ad annullare il PAI
       - Questo anche ad esempio se il PAI è stato fatto il 31 dicembre e si li disarruola a gennaio
       - Quindi vanno riarruolati e rifatti i PAI da pubblicare
  2. Dopo disarruolamenti: si attiva lato **Horus Medica**/ATS
  3. In Elty va cambiata la **cooperativa di riferimento** (lo fanno i componenti del team di Elty)
  4. **Horus Medica** comunica ad **ATS** che il medico va agganciato a **Horus Medica** (tipicamente rapido, 1–2 giorni a Milano; varia per ATS)
  5. Vanno rifatti i PAI annullati e pubblicati i nuovi

Casi e relative situazioni:

- IML: può disarruolare massivamente in Elty ma poi dovrà rifare i PAI annullati
- Altre cooperative: devono disarruolare i PAI dagli altri gestionali e poi rifare i PAI annullati in Elty
- Nessuna cooperativa precedete ad **Horus Medica**: non bisogna disarruolare nessun paziente, si può procedere direttamente in Elty

## 9. Portale prenotazioni **Horus Medica**

- Esiste portale regionale per prenotazioni lato cooperativa:
  - accesso con **firma remota + OTP telefono**
  - Ci pensano i componenti di **Horus Medica**