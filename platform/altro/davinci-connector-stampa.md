---
title: "Davinci Connector e stampa"
sidebarTitle: "Davinci Connector e stampa"
---

## Download del Davinci Connector

Il Davinci Connector permette la stampa delle ricette e il collegamento tramite Smart card.

Il Davinci Connector si può scaricare a questi link:

- Windows:
  - https://siss-connector-updater-tokbtpbwoa-ey.a.run.app/download
- Link Windows alternativo (nel caso in cui il precedente non funzionasse):
  - https://drive.google.com/file/d/1TWLGRZq6db3zRF3Jg2SmeET8rrtf9so-/view?usp=drive_link
- Mac Arm
  - https://drive.google.com/file/d/1fNSlHXcLbTqOZItGHuwGY6OGodwCbPwG/view?usp=drive_link
- Mac Intel
  - https://drive.google.com/file/d/1hrCbtYWVlFst72WVi4IjiHZclVv_DW94/view?usp=drive_link
- Link Mac alternativo (nel caso in cui i precedenti non funzionassero):
  - https://tinyurl.com/puy36948

Elty DaVinci utilizza l'app Connector per dare la possibilità di configurare al meglio la stampa delle varie ricette. Ogni tipologia ha la propria configurazione, che di base prevede:

- Formato di carta (A4, A5, etc.);
- Cassetto stampante, per le stampanti con più di un cassetto d'alimentazione carta;
- Orientamento, verticale o orizzontale.

<img
  src="/images/platform/davinci-connector/Screenshot_2026-02-03_alle_16.36.00.png"
  alt="Screenshot 2026-02-03 alle 16.36.00.png"
  className="mx-auto"
/>

## "Errore di stampa" - Accesso alla rete locale

**"Errore nella stampa"**

<img
  src="/images/platform/davinci-connector/Screenshot_2026-02-03_alle_16.21.09.png"
  alt="Screenshot 2026-02-03 alle 16.21.09.png"
  className="mx-auto"
/>

Dalla versione 142 di Chrome per accedere al Davinci Connector viene richiesto il consenso  per accedere alla rete locale (di cui il Connector fa parte). Alla comparsa del popup "davinci.elty.it vorrebbe - Cerca e connettiti a qualsiasi dispositivo sulla rete locale" va necessariamente dato consenso cliccando su "Consenti"

<img
  src="/images/platform/davinci-connector/image.png"
  alt="image.png"
  className="mx-auto"
/>

Se questo non dovesse avvenire, anche semplicemente ignorando quel popup o cliccando volontariamente su Blocca, il Connector smetterà di essere raggiungibile dando l'errore "Errore nella stampa". Per risolvere la questione bisogna:

- Cliccare sull'icona che si trova a sinistra dell'indirizzo web.

<img
  src="/images/platform/davinci-connector/image%201.png"
  alt="image.png"
  className="mx-auto"
/>

- Cliccare "Impostazioni sito"

<img
  src="/images/platform/davinci-connector/Screenshot_2026-02-03_alle_16.25.37.png"
  alt="Screenshot 2026-02-03 alle 16.25.37.png"
  className="mx-auto"
/>

- Tra le varie opzioni (solitamente ultime in lista) troverete "Accesso alla rete locale" impostato su "Blocca". Va modificato in "Consenti"

<img
  src="/images/platform/davinci-connector/image%202.png"
  alt="image.png"
  className="mx-auto"
/>

## Impostazioni per Mac

Per permettere l'utilizzo del Davinci Connector ogni volta che si accende il dispositivo ricordiamo che il software non deve essere tolto dagli "Elementi login ed estensioni"

<img
  src="/images/platform/davinci-connector/Screenshot_2026-02-03_alle_16.34.56.png"
  alt="Screenshot 2026-02-03 alle 16.34.56.png"
  className="mx-auto"
/>

Su Mac dopo l'installazione il software sarà in background, per visualizzare la schermata di Imposta e Configura bisognerà cliccare l'icona a forma di cuore in alto a destra e selezionare "Mostra"

<img
  src="/images/platform/davinci-connector/Screenshot_2026-02-03_alle_16.35.42.png"
  alt="Screenshot 2026-02-03 alle 16.35.42.png"
  className="mx-auto"
/>

## Imposta (seleziona la stampante)

Come selezionare la stampante dal Davinci Connector:

- Clicca su "Imposta" e seleziona la tua stampante dall'elenco.
- Se non trovi la tua stampante assicurati di averla configurata tramite i suoi driver ufficiali (li troverai nel sito web della tua stampante)
- Se sei certo di averla già configurata perché la utilizzi abitualmente ma non la trovi nell'elenco del Davinci Connector consigliamo di provare a vedere come si chiama:
  - Lanciando una stampa dal software di visualizzazione dei documenti del tuo pc (es. Adobe Reader, MS Word, Anteprima di Apple ecc.) vedrai il nome della stampante configurata all'interno del tuo sistema operativo
  - Quando avrai trovato il nome della tua stampante potrai selezionarla all'interno di "Imposta" del Davinci Connector

## Configura (modifica le impostazioni di stampa)

### Stampante per Rosse Cartacee (Modulo SSN)

- Permette di modificare le impostazioni relative alle Rosse Cartacee (Classe A)
- Oltre la configurazione base, le ricette rosse (modulo SSN) hanno la possibilità di configurare i margini di stampa, ovvero la distanza della stampa rispetto al bordo carta. Esse possono essere sia positive (per allontanarsi dal bordo) che negative (per avvicinarsi al bordo o oltre).
- Le ricette rosse vengono di default generate in formato A5 con orientamento verticale: si lascia la possibilità di selezionare comunque il formato di carta e l'orientamento di stampa solo in caso la stampante non riesca a posizionare la ricetta nell'orientamento giusto dettato dal PDF.

<Note>
  **_Si raccomanda di iniziare la configurazione con un formato di carta A5 e orientamento verticale._**

  _In caso la stampa risulti ruotata rispetto al foglio, per determinare la giusta configurazione, si può tentare selezionando il formato di carta A4 e facendo due test, sia con orientamento orizzontale che verticale._

  _Una volta sistemato l'orientamento si può passare a correggere lo scostamento rispetto ai margini._
</Note>

### Come stampare in A5

- Oltre a scegliere la configurazione corretta sul nostro Connector, vanno tenuti a mente una serie di accorgimenti da utilizzare fisicamente sulla stampante quando si vuole stampare in A5.
- ****_Il consiglio è di mantenere nella configurazione del Connector un orientamento verticale del foglio, oltre a selezionare A5 come formato di stampa. Solo in caso le varie combinazioni sotto riportate non dovessero dare l'effetto desiderato si consiglia di tentare anche selezionando l'orientamento orizzontale._****
- La prassi migliore vorrebbe che ci attenessimo alle **istruzioni del manuale** della stampante su come posizionare l'A5 nel cassetto della stampante. In alternativa possiamo seguire le **indicazioni riportate sulle guide** del cassetto

<img
  src="/images/platform/davinci-connector/Untitled.png"
  alt="Untitled"
  className="mx-auto"
/>

- Guide laterali ridotte: alcune stampanti vedono lo spazio delle guide laterali ridursi per accogliere l'A5.

<img
  src="/images/platform/davinci-connector/Untitled%201.png"
  alt="Untitled"
  className="mx-auto"
/>

- Guide laterali larghe: in altre stampanti le guide non vanno ridotte, e l'A5 va introdotto con il lato più lungo verso il lato di raccolta del foglio.

<img
  src="/images/platform/davinci-connector/Untitled%202.png"
  alt="Untitled"
  className="mx-auto"
/>
  - Nel caso le guide laterali non vadano ridotte per accogliere l'A5, può essere il cassetto a scivolare verso il lato di raccolta del foglio.

<img
  src="/images/platform/davinci-connector/Untitled%203.png"
  alt="Untitled"
  className="mx-auto"
/>

<img
  src="/images/platform/davinci-connector/Untitled%204.png"
  alt="Untitled"
  className="mx-auto"
/>

### Stampante per Bianche Cartacee (Ricettario Personale)

- Le ricette bianche (ricettario personale) prevedono le opzioni di configurazione base.
- Il PDF generato varia in base all'impostazioni del formato di carta selezionato se lo stesso è A4 o A5, altrimenti verranno generati in A4 e sarà poi compito della stampante riportarle al formato richiesto.
- In caso di A5 le ricette verranno generate con orientamento orizzontale, altrimenti verticale.

<Note>
  **_Si raccomanda di iniziare la configurazione con un formato di carta A4/verticale o A5/verticale._**

  _Il formato di carta deve necessariamente corrispondere al formato utilizzato._

  _Si può variare l'orientamento in caso la stampa risulti ruotata rispetto al foglio._
</Note>

<img
  src="/images/platform/davinci-connector/Untitled%205.png"
  alt="Untitled"
  className="mx-auto"
/>

### Stampante per Rosse e Bianche Dematerializzate (Promemoria Dematerializzata)

- Le ricette dematerializzate prevedono le opzioni di configurazione base.
- Il PDF generato varia in base all'impostazioni del formato di carta selezionato se lo stesso è A4 o A5, altrimenti verranno generati in A4 e sarà poi compito della stampante riportarle al formato richiesto.
- In caso di A5 le ricette verranno generate con orientamento orizzontale, altrimenti verticale.

<Note>
  **_Si raccomanda di iniziare la configurazione con un formato di carta A4/verticale o A5/verticale._**

  _Il formato di carta deve necessariamente corrispondere al formato utilizzato._

  _Si può variare l'orientamento in caso la stampa risulti ruotata rispetto al foglio._
</Note>

- **_NOTA BENE: l'orientamento del PDF generato non è direttamente correlato all'orientamento di stampa_**

## Problemi legati a come esce la stampa (orientamento, tagli, misura, testo piccolo ecc.)

- Cosa fare se la **stampa è ruotata** rispetto al foglio?
  - Se la stampa è ruotata di +/- 90° rispetto al foglio, provare ad invertire l'orientamento di stampa nella relativa configurazione.
  - Quindi da orizzontale a verticale o da verticale ad orizzontale
- Cosa fare se la **stampa è lontana da bordo e/o tagliata**?
  - In caso di ricetta rossa si può procedere ad impostare i margini di stampa. In caso di margine positivo la stampa si allontanerà dal relativo bordo, in caso di margine negativo invece si avvicinerà.
- Cosa fare se nella ricetta rossa cartacea il **codice fiscale viene tagliato**?
  - Probabilmente il foglio non è posizionato in maniera corretta nella stampante. Si consiglia di seguire i passaggi per stampare in A5
- Cosa fare se la stampa sembra **troppo grande/piccola**?
  - Se la stampa sembra troppo grande o piccola rispetto al foglio si può procedere nel controllare che per la relativa configurazione sia impostato il corretto formato di carta (A4, A5, etc.)
  - Si può procedere con un nuovo formato di carta e vedere se il risultato migliora