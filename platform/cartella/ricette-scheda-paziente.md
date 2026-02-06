---
title: "Ricette (scheda paziente)"
sidebarTitle: "Ricette (scheda paziente)"
---

### 1. Introduzione

- La sezione Ricette in scheda paziente permette di creare ed elaborare le prescrizioni

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.38.png"
alt="Screenshot 2025-04-16 alle 11.22.38.png"
className="mx-auto"
/>

### 2. Prescrivere un farmaco

- Per prescrivere un farmaco, seleziona "Farmaco".

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.52.png"
alt="Screenshot 2025-04-16 alle 11.22.52.png"
className="mx-auto"
/>

- Inserisci il nome farmaco e selezionalo
  - Compariranno informazioni su allergie e interazioni tra farmaci (le interazioni tra farmaci solo se l'alert è stato abilitato in Gestione servizi)
- Cliccando "Mostra dettagli" potrai accedere a numerose informazioni:
  - Nome commerciale → Cliccando si aprirà una nuova scheda con il bugiardino del farmaco
  - Dosaggio
  - Principio attivo
  - Classe del farmaco
  - Prezzo
- Puoi selezionare:
  - Prescrivi per principio attivo
  - Non sostituibile
  - Continuativo (il farmaco comparirà nel box Farmaci continuativi in scheda paziente, se non selezionato sarà in Farmaci ordinari)
- Cliccando Farmaci equivalenti in commercio uscirà una lista di farmaci equivalenti da poter selezionare
- Inserisci le informazione di confezione e posologia:
- Numero confezioni
- Unità
- Ogni (ogni quanto prendere il farmaco)
- Durata
- Via di somministrazione
- Modalità di assunzione (facoltativa)
- È impostata in automatico la posologia strutturata così da poter avere il calcolo delle scorte (il fulmine delle scorte indica la quantità di farmaco che il paziente ha ancora a disposizione)
- Clicca "passa a posologia libera" per inserire una posologia testuale (questa posologia non permetterà però il calcolo delle scorte)

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.24.09.png"
alt="Screenshot 2025-04-16 alle 11.24.09.png"
className="mx-auto"
/>

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.43.21.png"
alt="Screenshot 2025-04-16 alle 11.43.21.png"
className="mx-auto"
/>

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.43.29.png"
alt="Screenshot 2025-04-16 alle 11.43.29.png"
className="mx-auto"
/>

- Aggiungi l'esenzione e note in ricetta (a volte obbligatorie sulla base delle regole prescrittive del farmaco).
  - Le esenzioni suggerite compariranno in automatico
  - Selezionando il campo esenzione potrai scegliere l'esenzione del paziente:
  - Suggerite
  - A discrezione del medico
  - Non suggerite (permettiamo comunque la possibilità di selezionarle, la ricetta potrebbe però andare in errore a seguito della verifica del sistema regionale)

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.24.21.png"
alt="Screenshot 2025-04-16 alle 11.24.21.png"
className="mx-auto"
/>

- Dopo aver cliccato prescrivi si creerà la bozza di ricetta
- Sul fondo della pagina "Ricette" (della scheda paziente) ci sarà la bozza di **ricetta pronta per essere elaborata** (_subito o più tardi_).
- L'elabora più tardi permette al medico di creare delle bozze di ricetta quando ci sono dei problemi con il sistema regionale, in questo modo quando il sistema regionale torna a funzionare il medico potrà elaborare massivamente le ricette dalla sezione "Ricette" (in alto a sinistra di "Richieste")
- Dalla bozza di ricetta si potrà modificare la tipologia di ricetta (cliccando la tipologia di ricetta in alto a destra all'interno della bozza di ricetta, a sinistra dei 3 puntini verticali):
  - Rossa dematerializzata → a carico del SSN e dematerializzata (non cartacea, fascia A)
  - Rossa cartacea → a carico del SSN e da stampare (non arriverà tramite FSE, fascia A)
  - Bianca dematerializzata → a carico del paziente e dematerializzata (fascia C)
  - Bianca cartacea → la tipica ricetta libera a carico del paziente (da stampare, fascia C)
- Con l'elaborazione ci sarà la validazione del sistema regionale e la ricetta arriverà via FSE, Email (se impostata l'opzione in Gestione servizi e se inserita all'interno della scheda anagrafica del paziente), via App (se scaricata dal paziente) e via SMS con codice NRE (in alcune regioni)

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-04_alle_14.14.58.png"
alt="Screenshot 2025-04-04 alle 14.14.58.png"
className="mx-auto"
/>

### 3. Prescrivere una prestazione

- Per prescrivere una prestazione, seleziona **_"Prestazione"_**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.52_2.png"
alt="Screenshot 2025-04-16 alle 11.22.52 2.png"
className="mx-auto"
/>

- Si aprirà una schermata, di default sarai su "Aggiungi prestazione singola". Cerca la prestazione che vuoi prescrivere all'interno del box di ricerca.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.24.29.png"
alt="Screenshot 2025-04-16 alle 11.24.29.png"
className="mx-auto"
/>

- Apparirà un'anteprima della visita, clicca su **_"Conferma"_** per salvarla.
  - Se si modifica la quantità/cicli la prestazione sarà continuativa (e nel box Prestazioni continuative)

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.48.28.png"
alt="Screenshot 2025-04-16 alle 11.48.28.png"
className="mx-auto"
/>

- Si creerà la bozza di ricetta, da qui potrai:
- Convertire la ricetta (rossa dem, cartacea, bianca dem, cartacea)
- Inserire l'**esenzione**
- Scrivere il **quesito diagnostico (p**uoi passare a **"Quesito codificato").**

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.48.42.png"
alt="Screenshot 2025-04-16 alle 11.48.42.png"
className="mx-auto"
/>

- Nel quesito codificato devi inserire lo **stato** e **nota quesito**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.48.58.png"
alt="Screenshot 2025-04-16 alle 11.48.58.png"
className="mx-auto"
/>

- Lo stato può essere:
- Attivo
- Cronico
- Intermittente
- Risolto

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.56.29.png"
alt="Screenshot 2025-04-16 alle 11.56.29.png"
className="mx-auto"
/>

- Continuando, bisogna inserire la **classe priorità** e spuntare la casella se è una **visita domiciliare**

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.51.32.png"
alt="Screenshot 2025-04-16 alle 11.51.32.png"
className="mx-auto"
/>

- Le classi di priorità sono:
- U - Prima possibile
- B - Entro 10 giorni
- D - Entro 30 giorni (ambulatoriale) / 60 giorni (laboratorio)
- P - Programmata

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.52.23.png"
alt="Screenshot 2025-04-16 alle 11.52.23.png"
className="mx-auto"
/>

- Si possono aggiungere delle informazioni aggiuntive come:
- Mostra informazioni paziente
- Motivo oscuramento
- Compilato in situazione di urgenza
- Suggerito da uno specialista
  - Per indicare che una prescrizione è suggerita da un altro medico, bisogna selezionare il quadratino "Suggerito da uno specialista" che puoi trovare nella bozza di ricetta nella sezione "Informazioni aggiuntive".

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.49.11.png"
alt="Screenshot 2025-04-16 alle 11.49.11.png"
className="mx-auto"
/>

- Si possono anche prescrivere dei pacchetti di prestazioni personalizzate
  - In questo caso ci saranno più prestazioni che verranno inserite in varie ricette sulla base delle regole prescrittive e la branca delle prestazioni
  - Si può scegliere un quesito diagnostico globale così da non dover riscrivere il quesito su ogni ricetta in bozza

### 4. Trasporto sanitario

- Per prescrivere un trasporto sanitario, seleziona **_"Trasporto Sanitario"_**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.52_3.png"
alt="Screenshot 2025-04-16 alle 11.22.52 3.png"
className="mx-auto"
/>

- Compila i seguenti campi:
- Condizioni cliniche
- Motivo del trasporto
- Tipologia di viaggio (andata e ritorno, ritorno, andata)
- Ripetibilità di trasporto (da 1 a 5)

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_12.28.33.png"
alt="Screenshot 2025-04-16 alle 12.28.33.png"
className="mx-auto"
/>

- Scegli le località di partenza e arrivo:
- Domicilio sanitario
- Cure intermedie / lowcare
- Residenza
- Strutture sanitarie
- Struttura pubblica fuori regione
- Altro indirizzo

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_12.28.42.png"
alt="Screenshot 2025-04-16 alle 12.28.42.png"
className="mx-auto"
/>

- inserisci l'indirizzo completo per partenza e arrivo.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_12.34.01.png"
alt="Screenshot 2025-04-16 alle 12.34.01.png"
className="mx-auto"
/>

- La prescrizione sarà in bozza pronta per essere elaborata.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_12.34.12.png"
alt="Screenshot 2025-04-16 alle 12.34.12.png"
className="mx-auto"
/>

### 5. Ricovero ospedaliero

- Per prescrivere un ricovero ospedaliero, seleziona **_"Ricovero ospedaliero"_**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.52_4.png"
alt="Screenshot 2025-04-16 alle 11.22.52 4.png"
className="mx-auto"
/>

- Inserisci:
- Motivo del ricovero
- Reparto
- Selezionare "Compila scheda di accesso ospedaliero" per inserire i dati per completare la scheda di accesso ospedaliero
- Se cliccato "Compila scheda di accesso ospedaliero" si apriranno le sezioni "Accertamenti e terapie in corso" (Seleziona farmaci o prestazioni tra quelli già inseriti in scheda paziente e/o utilizza il campo libero "Aggiungi altre informazioni"), anamnesi e scheda sanitaria
- Clicca **_"Aggiungi"_** per confermare.

<img
  src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.25.06.png"
  alt="Screenshot 2025-04-16 alle 11.25.06.png"
  className="mx-auto"
/>

### 6. Prescrizione libera

- Seleziona **_"Prescrizione libera" per fare una prescrizione libera "Bianca cartacea" o "Rossa cartacea"_**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-16_alle_11.22.52_5.png"
alt="Screenshot 2025-04-16 alle 11.22.52 5.png"
className="mx-auto"
/>

- Scrivi la prescrizione a mano libera nel campo testuale. Per salvare clicca su **_"Prescrivi"_**.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-18_alle_09.17.11.png"
alt="Screenshot 2025-04-18 alle 09.17.11.png"
className="mx-auto"
/>

- Per fare una prescrizione libera rossa cartacea dovrai inserire anche:
- Esenzione
- Quantità/cicli
- Classe priorità
- Nota AIFA
- Se suggerita

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-18_alle_09.17.26.png"
alt="Screenshot 2025-04-18 alle 09.17.26.png"
className="mx-auto"
/>

### 7. Elaborazione

- Si può **rimandare l'elaborazione della ricetta** a un momento successivo cliccando "**_Elabora più tardi_**".

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-04_alle_14.14.58%201.png"
alt="Screenshot 2025-04-04 alle 14.14.58.png"
className="mx-auto"
/>

- La ricetta verrà automaticamente spostata nella sezione **__"Ricette" → "Da elaborare".__** Per completare l'operazione, clicca **_"Elabora tutte" in alto a destra._**

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-23_alle_10.48.04.png"
alt="Screenshot 2025-04-23 alle 10.48.04.png"
className="mx-auto"
/>

- Cliccando **_"Elabora" all'interno della bozza di ricetta (in basso a destra)_** la ricetta viene validata dal sistema regionale.

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-04_alle_14.14.58_2.png"
alt="Screenshot 2025-04-04 alle 14.14.58 2.png"
className="mx-auto"
/>

- Per vedere lo storico delle ricette elaborate relative al paziente clicca su "**_Vai all'archivio_**".

<img
src="/images/platform/ricette-scheda-paziente/Screenshot_2025-04-23_alle_10.50.45.png"
alt="Screenshot 2025-04-23 alle 10.50.45.png"
className="mx-auto"
/>

- Per tornare alla schermata di creazione delle ricette clicca "Nuove ricette"
- Cliccando "Importa ricetta" sotto a "Nuove ricette" (quindi all'interno dell'archivio delle ricette all'interno della scheda paziente) si potrà importare una ricetta dematerializzata o una bianca dematerializzata:
  - I campi da inserire per la dematerializzata sono
    - **Numero Ricetta Elettronica**
    - **Identificativo univoco (IUP)**
  - **Solo uno dei due campi può essere compilato**
  - Per la bianca dematerializzata:
    - **Pin ricetta bianca elettronica**
    - **Numero ricetta bianca elettronica**
  - **Solo uno dei due campi può essere compilato**

<Warning>
  Quando stampi da Davinci Connector le opzioni sono queste:

  Modulo ssn → rosse cartacee

  Ricettario personale → bianche cartacee

  Promemoria dem → dematerializzate
</Warning>