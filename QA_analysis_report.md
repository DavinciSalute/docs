# Analisi Q&A Elty Davinci — Report

**Data analisi:** 13 aprile 2026
**File analizzato:** Q&A.txt (473 entry, 9177 righe)
**Metodo:** Analisi AI per contraddizioni interne + confronto con documentazione .mdx attuale

---

## Sezione 1: Contraddizioni interne tra entry Q&A

Entry che si contraddicono tra loro all'interno dello stesso gruppo tematico.

---

### 1.1 Ricette/Prescrizioni

- **Entry 60 (riga ~958) / Entry 84 (riga ~1343) vs Entry 457 (riga ~8202)**
  - Entry 60/84 dicono: per farmaci senza Piano Terapeutico, prescrivere **senza nota**, cambiare da **Bianca dem a Rossa dem**, ricreare la ricetta **senza selezionare alcun PT** (svuotare il campo se proposto automaticamente), e selezionare il PTE **solo se all'invio viene ancora richiesto**.
  - Entry 457 dice: «Ricrea la ricetta da zero. Vai in Ricette e crea una nuova prescrizione e **seleziona il PTE**» — senza il percorso «senza nota» + Bianca→Rossa, senza «prima senza PT / svuota campo», e senza la condizione «solo se richiesto».
  - **Motivo:** procedure incompatibili per lo stesso scenario (Nota 100, PT non più obbligatorio salvo PTE). Due risposte danno una sequenza graduata, la terza salta direttamente a «seleziona il PTE».

- **Entry 58 (riga ~926) vs Entry 457 (riga ~8202)**
  - Entry 58 dice: «Ricrea la ricetta da zero **senza selezionare alcun PT**. Se Elty propone automaticamente un PT, **svuota il campo PT** prima dell'invio» e «Se compare un errore, indica il PTE attivo».
  - Entry 457 dice: «crea una nuova prescrizione e **seleziona il PTE**» come azione diretta.
  - **Motivo:** ordine e condizioni diversi per lo stesso tipo di blocco prescrittivo.

---

### 1.2 Pazienti/Anagrafica

- **Entry 3 (riga ~45) vs Entry 40 (riga ~649)**
  - Entry 3 dice: «Quando inserisci un nuovo paziente, compila i **campi richiesti** (numero di telefono ed email).»
  - Entry 40 dice: «Puoi salvare i pazienti con il **solo numero di cellulare**» e «L'email rimane **facoltativa** [...] ma non è obbligatoria per proseguire.»
  - **Motivo:** in un caso email e telefono sono presentati come campi richiesti insieme; nell'altro l'email è esplicitamente facoltativa.

- **Entry 443 (riga ~7954) vs Entry 100 (riga ~1565) / Entry 102 (riga ~1596)**
  - Entry 443 dice: l'errore sull'indirizzo in ricetta si risolve con l'**icona della sincronizzazione** in scheda paziente.
  - Entry 100/102 dicono: l'indirizzo "ufficiale" viene riallineato al regionale e tende a sovrascrivere; la soluzione stabile è **l'indirizzo alternativo** con «Utilizza indirizzo alternativo come predefinito».
  - **Motivo:** procedure non compatibili per lo stesso scenario (indirizzo errato in prescrizione).

- **Entry 276 (riga ~4611) vs Entry 422 (riga ~7579) / Entry 423 (riga ~7598)**
  - Entry 276 dice: invio certificati via email «non è attualmente prevista» / «riporto agli sviluppatori per valutazione».
  - Entry 422/423 dicono: la funzionalità è stata «rilasciata da poco» e procedono ad attivarla.
  - **Motivo:** conflitto fattuale sullo stato della funzionalità (assente vs già rilasciata). Entry 276 ha anche un problema di dati (due conversazioni fuse in una sola risposta).

---

### 1.3 Impostazioni/Profilo

- **Entry 382 (riga ~6806) vs Entry 422 (riga ~7579) / Entry 447 (riga ~8025)**
  - Entry 382 dice: invio certificati via email è un «feedback da riportare agli sviluppatori per valutazione».
  - Entry 422 dice: la funzionalità è stata «rilasciata da poco» e viene attivata.
  - Entry 447 cita «Invio PDF delle ricette e certificati tramite e-mail» in Gestione servizi.
  - **Motivo:** stesso tema trattato come feature inesistente, feature nuova, e feature attiva, senza coerenza.

---

### 1.4 Agenda/Appuntamenti

- **Entry 132 (riga ~2188) vs Entry 113/114 (righe ~1422–1800)**
  - Entry 132 dice: per l'infermiera, gli orari devono essere **«Visibile ai pazienti della medicina di gruppo»**.
  - Entry 113/114 dicono: attivare **«Visibile ai pazienti»**.
  - **Motivo:** denominazioni diverse dell'opzione per lo stesso obiettivo (autoprenotazione vaccini sull'agenda infermieristica).

- **Entry 199/386 (righe ~3301, ~6876) vs Entry 217/427 (righe ~3563, ~7684)**
  - Entry 199/386 dicono: Agenda → **Pianifica** → **Nuovo evento** → titolo, orari, struttura, salva.
  - Entry 217/427 dicono: Agenda → **clic sul giorno** → **Crea evento**.
  - **Motivo:** percorsi e nomi di comando diversi per creare un evento di blocco (chiusura ambulatorio).

- **Posizione di «Imposta disponibilità»** (molteplici entry)
  - Alcune entry indicano «a sinistra, sotto Pianifica», altre «in basso a sinistra», altre «sulla sinistra» senza ulteriori specifiche.
  - **Motivo:** istruzioni di navigazione non uniformi per la stessa azione.

---

### 1.5 Chat/Messaggi

- **Entry 5 (riga ~82) vs Entry 116 (riga ~1845)**
  - Entry 5 dice: per le immagini in chat «cliccare con il **tasto destro** e selezionare "Salva immagine con nome"»; per altri allegati il click apre lo scaricamento.
  - Entry 116 dice: per i file dalla chat «clicca sull'allegato e seleziona "Salva con nome"».
  - **Motivo:** procedure diverse per salvare allegati dalla chat.

- **Entry 198 (riga ~3276) vs Entry 317/380 (righe ~5412, ~6773)**
  - Entry 198 dà per scontata un'«app per i medici» senza reindirizzare al web.
  - Entry 317/380 chiariscono: per Elty lato medico si usa il **browser** con `davinci.elty.it`.
  - **Motivo:** indicazioni incoerenti sull'accesso medico (app vs webapp).

- **Entry 142 (riga ~2383) vs Entry 306 (riga ~5210)**
  - Entry 142 su «qualcosa è andato storto»: sequenza **Profilo/regione → cache → portale regionale**.
  - Entry 306 sullo stesso messaggio: sequenza **logout/login cloud regionale → Connector → portale regionale → Profilo/regione → cache**.
  - **Motivo:** ordine e priorità dei passaggi diagnostici non allineati.

---

### 1.6 Referti

- **Entry 320 (riga ~5460) vs Entry 283 (riga ~4747)**
  - Entry 320 dice: trascrizione automatica «funziona solo con i referti in formato CDA2».
  - Entry 283 dice: la trascrizione automatica su CDA2 è possibile «in Lombardia e in Toscana ma non nelle altre regioni».
  - **Motivo:** 320 riduce il requisito al solo formato; 283 aggiunge un vincolo regionale.

- **Entry 320 (riga ~5460) vs Entry 335 (riga ~5775)**
  - Entry 320 implica che basti il formato CDA2 per la trascrizione automatica.
  - Entry 335 spiega che anche con CDA2 può comparire «Trascrizione non riuscita» se manca la transcodifica.
  - **Motivo:** conflitto su cosa sia sufficiente per la trascrizione automatica.

---

### 1.7 Connessione/Tecnico

- **Entry 80 (riga ~1273) vs Entry 168 (riga ~2772)**
  - Entry 80 (Connector Windows): `https://siss-connector-updater-tokbtpbwoa-ey.a.run.app/download`
  - Entry 168 (Connector Windows): `https://drive.google.com/file/d/1TWLGRZq6db3zRF3Jg2SmeET8rrtf9so-/view?usp=drive_link`
  - **Motivo:** due URL di download diversi per lo stesso software senza chiarire quale sia quello corretto.

- **Entry 142 (riga ~2383) vs Entry 267 (riga ~4421) vs Entry 384 (riga ~6834)**
  - Entry 142: «qualcosa è andato storto» → causa tipica: **comunicazione col sistema regionale**; passi: profilo/regione, cache, portale.
  - Entry 267: «potrebbero esserci **varie motivazioni**»; passi: cache, URL davinci.elty.it, screenshot, altro browser.
  - Entry 384: se in Chrome normale c'è l'errore ma in incognito/Edge funziona → problema **dati locali/cookie/cache**.
  - **Motivo:** tre spiegazioni diverse e workflow diagnostici non allineati per lo stesso messaggio di errore.

---

### 1.8 Stampa

- **Entry 138 (riga ~2304) vs Entry 424 (riga ~7613)**
  - Entry 138 dice: ricette cartacee da spostare in **«Elabora più tardi»** per stampa massiva.
  - Entry 424 dice: mettere le cartacee in **«Da elaborare»** per stampa massiva.
  - **Motivo:** nomi diversi per la stessa sezione («Elabora più tardi» vs «Da elaborare»).

- **Entry 80 (riga ~1273) vs Entry 251 (riga ~4125)**
  - Entry 80 (firma remota): «clicca sul tuo nome → **Login Cloud Regionale**» (solo login).
  - Entry 251: «clicca sul tuo nome → **Logout Cloud Regionale** → poi Login Cloud Regionale» (logout prima, poi login).
  - **Motivo:** procedure diverse per lo stesso flusso di riconnessione firma remota.

---

### 1.9 Fatturazione

- **Entry 235 (riga ~3867) / Entry 244 (riga ~4014) vs Entry 435 (riga ~7820)**
  - Entry 235/244 dicono: «Attualmente **non abbiamo ancora integrato** un sistema di fatturazione [...] sarà una miglioria futura».
  - Entry 435 dice: «**sì**, le fatture verranno trasmesse automaticamente al sistema TS e all'Agenzia delle Entrate».
  - **Motivo:** conflitto fattuale sullo stato del prodotto (fatturazione non integrata vs funzionalità operativa).

---

### 1.10 SISS

Nessuna contraddizione interna trovata.

### 1.11 Esenzioni

Nessuna contraddizione interna trovata.

---

## Sezione 2: Risposte potenzialmente obsolete (vs documentazione .mdx attuale)

Entry le cui risposte non corrispondono a quanto descritto nella documentazione ufficiale.

---

### 2.1 Fatturazione

- **Entry 235 (riga ~3867) e Entry 244 (riga ~4014)**
  - La risposta dice: «Attualmente non abbiamo ancora integrato un sistema di fatturazione.»
  - La documentazione (`fatturazione.mdx`) descrive un modulo completo: creazione, gestione e trasmissione fatture verso il Sistema TS, con libreria prestazioni, bozza, trasmissione, stati, rettifica/annullamento, esportazione.
  - **Obsoleta:** la fatturazione esiste ed è documentata.

- **Entry 435 (riga ~7820)**
  - La risposta dice: «le fatture verranno trasmesse automaticamente al sistema TS e all'Agenzia delle Entrate.»
  - La documentazione descrive un flusso guidato (bozza → azione «Trasmetti fattura»), configurazione credenziali ADE, e opzione per non inviare ai fini della precompilata.
  - **Imprecisa:** non è automatico, richiede azione manuale e configurazione.

---

### 2.2 Pazienti/Anagrafica

- **Entry 205 (riga ~3390) e Entry 209 (riga ~3444) e Entry 233 (riga ~3840)**
  - La risposta dice: «Attualmente non è integrata la ricerca per Codice Fiscale.»
  - La documentazione (`ricerca-paziente.mdx`, `panoramica.mdx`) conferma che la ricerca supporta **nome, cognome e codice fiscale**.
  - **Obsoleta:** la ricerca per CF esiste.

- **Entry 254 (riga ~4204)**
  - La risposta dice: per passare da regime privato a SSN, usare Archivio → **Cambia stato → SSN**.
  - La documentazione (`panoramica.mdx`, §4) dice: in regime privato **non si può** usare «Cambia stato»; bisogna spostare in archivio → cestino e **reinserire** con «Aggiungi paziente» come SSN.
  - **Obsoleta/errata:** procedura diversa da quella ufficiale.

- **Entry 8 (riga ~136)**
  - La risposta dice: usare **«Lista pazienti»** e un **menù a tendina** per navigare alla scheda.
  - La documentazione dice: la sezione si chiama **«Pazienti»** (in alto a sinistra); la ricerca è la **lente in alto a destra**.
  - **Obsoleta:** etichette di navigazione non allineate.

---

### 2.3 Impostazioni/Profilo

- **Entry 2 (riga ~23)**
  - La risposta dice: «su gestione servizi troverai un **cestino** accanto ad ogni nome per eliminare un membro del gruppo.»
  - La documentazione (`gestione-servizi.mdx`) dice: per modificare i membri del gruppo di lavoro occorre **«Contattaci»** (ticket assistenza).
  - **Obsoleta/errata:** rimozione autonoma non descritta nei docs.

- **Entry 276 (riga ~4611), Entry 382 (riga ~6806)**
  - La risposta dice: invio certificati via email è un feedback da riportare agli sviluppatori / miglioria futura.
  - La documentazione (`gestione-servizi.mdx`, § 7b): l'invio dei certificati in PDF via e-mail è **sempre abilitato**.
  - **Obsoleta:** la funzionalità esiste ed è sempre attiva.

- **Entry 422 (riga ~7579)**
  - La risposta dice: «l'abbiamo rilasciata da poco e provvediamo subito ad **attivartela**».
  - La documentazione dice: per i certificati **non è necessaria** un'attivazione manuale; sono **sempre abilitati**.
  - **Obsoleta:** il modello di attivazione manuale non corrisponde allo stato attuale.

- **Entry 447 (riga ~8025)**
  - La risposta dice: abilitare «Invio PDF delle **ricette e certificati** tramite e-mail».
  - La documentazione dice: invio ricette (§ 7) e invio certificati (§ 7b) sono **regole diverse**; i certificati non dipendono dallo stesso toggle delle ricette.
  - **Obsoleta/errata:** percorso e naming non corrispondono.

---

### 2.4 Chat/Messaggi

- **Entry 7 (riga ~115), Entry 39 (riga ~559)**
  - La risposta dice: limite avvisi **318 caratteri**.
  - La documentazione (`avvisi-pazienti.mdx`) dice: 318 caratteri nella modalità SMS, ma con **«Invia solo email e notifica in app»** non ci sono limiti di caratteri.
  - **Incompleta:** non menziona la modalità senza limiti.

- **Entry 116 (riga ~1845)**
  - La risposta dice: non si può disattivare solo l'invio di allegati in chat; si può disabilitare l'intera chat.
  - La documentazione (`gestione-servizi.mdx`) descrive la voce **«Chat con allegati»**, attivabile/disattivabile con interruttore dedicato.
  - **Obsoleta:** esiste un controllo specifico per gli allegati in chat.

---

### 2.5 Referti

- **Entry 82 (riga ~1328), Entry 83 (riga ~1335), Entry 91 (riga ~1459)**
  - La risposta dice: **non è possibile** cancellare i referti scaricati dal FSE.
  - La documentazione (`cartella/referti.mdx`) dice: i referti da FSE **si possono eliminare su richiesta**, ma a ogni nuovo scarico massivo da FSE possono ricomparire.
  - **Obsoleta:** eliminazione possibile su richiesta.

---

### 2.6 Stampa

- **Entry 107 (riga ~1679)**
  - La risposta dice: rimando a una guida su **Notion** per configurazione stampante.
  - La documentazione (`davinci-connector-stampa.mdx`) descrive la procedura ufficiale nel repo.
  - **Obsoleta:** il link Notion non è la fonte ufficiale; la guida è in documentazione.

---

### 2.7 SISS

- **Entry 260 (riga ~4315)**
  - La risposta dice: cercare la voce **«Medboard - Bacheca medici»** nel portale SISS.
  - La documentazione (`bacheca-siss.mdx`) non menziona questa voce; la Bacheca SISS si accede dal nome in alto a destra.
  - **Potenzialmente obsoleta:** terminologia non presente nei docs.

---

### 2.8 Ricette/Prescrizioni

- **Entry 53 (riga ~2281)**
  - La risposta dice: la sezione Ricette è «a **sinistra** di Richieste e a **destra** di Referti».
  - La documentazione descrive l'ordine: Richieste → Ricette → Referti (quindi Ricette è a **destra** di Richieste e a **sinistra** di Referti).
  - **Errata:** posizione relativa invertita.

---

### 2.9 Agenda/Appuntamenti

- **Entry 141 (riga ~2366)**
  - La risposta dice: pulsante Esporta «**in alto a destra**».
  - La documentazione indica il pulsante Esporta **a sinistra di «Pianifica»**.
  - **Potenzialmente obsoleta:** posizione del pulsante non allineata.

---

### 2.10 Altro

- **Entry 26 (riga ~457)**
  - La risposta dice: riporto agli sviluppatori il feedback per un comando «continua» per riprendere i dati del certificato iniziale.
  - La documentazione (`certificati.mdx`) descrive già l'opzione **«Duplica e modifica»** dal menu a tre puntini, che crea una copia con dati precompilati.
  - **Obsoleta:** la funzionalità esiste già.

---

### 2.11 Esenzioni

Nessuna discrepanza trovata.

---

## Riepilogo

| Area | Contraddizioni | Obsolete vs docs |
|------|:--------------:|:----------------:|
| Ricette/Prescrizioni | 2 | 1 |
| Pazienti/Anagrafica | 3 | 4 |
| Impostazioni/Profilo | 1 | 5 |
| Agenda/Appuntamenti | 3 | 1 |
| Chat/Messaggi | 3 | 2 |
| Referti | 2 | 1 |
| Connessione/Tecnico | 2 | — |
| Stampa | 2 | 1 |
| Fatturazione | 1 | 3 |
| SISS | — | 1 |
| Altro | — | 1 |
| Esenzioni | — | — |
| **Totale** | **19** | **20** |

**Totale problemi trovati: 39** (19 contraddizioni interne + 20 discrepanze vs documentazione)
