# Attivare Amici Mochipi sul servizio delle segnalazioni

## Crash sleeping all'avvio: Companion v1.294

L'errore `'Mochipi' object has no attribute 'sleeping'` è nel Companion
aggiornato con un pacchetto Games precedente all'API del sonno. Aggiornare
il Companion alla v1.294, poi aprire Moduli e aggiornare Games alla 1.35.
Non eliminare il salvataggio del pet o l'identità Amici. Lo script Google
non può correggere questo crash locale.

Lo script A2Companion.gs espone già visits_live, shared_hygiene, sleep_sync
e farm_bonus. Se il codice dell'editor coincide ma il servizio pubblicato
non espone queste funzioni, pubblicare una nuova versione dello **stesso
deployment**, conservando URL, proprietà e fogli. Non rieseguire setup.

## Aggiornamento v1.283 / Games 1.25: sonno e bonus farm

Aggiornare lo stesso deployment con A2Companion.gs, senza rifare il setup,
senza cambiare URL, proprieta, fogli o token. doGet deve esporre sleep_sync
e farm_bonus in social_features. Entrambi gli utenti devono aggiornare il
Companion alla v1.283 e Games alla 1.25.

Il sonno esplicito del proprietario prevale sulla previsione di energia;
anche risvegli anticipati e incubi si riflettono sul client dell'amico.
La somma dell'EXP farmata da entrambi genera un bonus del 20% per ciascun
Mochipi, consegnato soltanto alla fine e incluso nel resoconto. Report
cumulativi, premio congelato e ACK evitano accrediti ripetuti. Per includere
gli ultimi secondi il server attende la chiusura dei report di entrambi:
massimo 120 secondi dopo la fine se un client non risponde. Dopo il termine
di tolleranza, la farm tardiva non modifica il bonus gia congelato.

## Aggiornamento v1.281 / Games 1.23: sporco condiviso

Aggiornare lo stesso deployment con A2Companion.gs, conservando URL, fogli,
proprieta e token, senza rifare il setup. doGet deve mostrare shared_hygiene
in social_features. Entrambi i Companion devono usare Games 1.23 e v1.281.

Il server raccoglie le nuove macchie della visita (ID, tipo, coordinate
normalizzate e proprietario), le mostra a entrambi e conserva una tombstone
quando sono pulite. Richieste ripetute non fanno ricomparire lo sporco.
In caso di pulizia simultanea vince una sola richiesta: solo quel giocatore
riceve la ricevuta positiva per 50 EXP (cacca) o 75 EXP (vomito). Le ricevute
vengono ritirate solo dopo ACK del salvataggio riuscito sul client.
La sincronizzazione durante una visita passa a circa 5 secondi, con invio
anticipato dopo una nuova macchia o un clic. Il testo EXP+ compare dopo
l'accredito confermato. I client precedenti restano compatibili con le
visite, ma non possono condividere macchie e pulizie.

## Correzione v1.279 / Games 1.21

Aggiornare nuovamente lo stesso deployment con A2Companion.gs. Le visite
gia avviate senza la modalita live vengono abilitate quando sincronizza un
client aggiornato: XP cumulativa viene inviata sia al visitatore sia a chi
ospita. L'app mostra EXP+ con il valore accreditato solo dopo il salvataggio
del credito, e il resoconto include l'intero totale, senza duplicarlo.
Conservare URL, fogli, proprieta e token. Non rifare il setup.

## Aggiornamento v1.278 / Games 1.20

Sostituire il codice dello stesso progetto con **A2Companion.gs** e creare
una nuova versione del deployment web esistente. Conservare URL, proprieta,
token e fogli; non eseguire di nuovo setup e non creare un secondo servizio.
`doGet` deve mostrare `visits_live` in `social_features`.

Le visite iniziate con il client aggiornato restituiscono EXP cumulativa
a ogni sincronizzazione, circa ogni 30 secondi. Il client salva insieme
credito e ricevuta e al termine aggiunge solo la differenza ancora dovuta.
Tornando prima, l'EXP maturata resta al pet; solo le risorse subiscono il 20%
di penalita. Le visite precedenti conservano le regole v2 gia in corso.
Dalla visita successiva a una visita completa di un'ora con lo stesso
amico, entrambi hanno +15% EXP e cuoricini. Gli amici ora includono il livello
del loro Mochipi, aggiornato dal normale sync. I pisolini notturni lunghi
sono supportati nel calcolo EXP doppia del sonno.

Le Sfide su visite totali/amici diversi usano ricevute server: contano solo
le visite iniziate dal giocatore e durate almeno 5 minuti. Sfide, inventario
e uso degli articoli sono locali. Senza aggiornare lo script, la vecchia
sincronizzazione resta compatibile ma non fornisce EXP in corso, bonus
legame, livelli amici o i metadati necessari alle nuove Sfide sociali.

## Aggiornamento v1.270 / Games 1.15: Kit medico condiviso

Lo script aggiunge kit_medico agli articoli condivisibili durante una visita.
Sostituisci il codice con A2Companion.gs e pubblica una nuova versione dello
stesso deployment, mantenendo URL, fogli e proprieta. Non rieseguire setup.
Il Kit medico funziona localmente anche con lo script precedente; per farlo
ricevere anche all'amico serve questo aggiornamento e Games 1.15 su entrambi.

## Aggiornamento v1.269 / Games 1.14: servizio occupato

Sostituisci il codice con A2Companion.gs e pubblica una nuova versione del
deployment esistente, mantenendo lo stesso URL. Non rieseguire setup e non
cancellare fogli o proprieta: le amicizie esistenti vengono mantenute.
Le scritture sono raggruppate, le righe invariate non vengono riscritte e il
lock attende fino a 5 secondi. Il client conserva l'ultimo elenco valido e
scagliona i tentativi quando il servizio e occupato.

## Aggiornamento v1.267 / Games 1.12: visite e sonno

Sostituisci il codice con A2Companion.gs e pubblica una nuova versione del
deployment esistente. Non rieseguire setup e non cambiare URL, proprieta o fogli.
`doGet.social_features` deve contenere `visits_v2`.

La nuova versione gestisce cancel_visit con premio proporzionale ridotto del
20%, pasti condivisi con ID univoci e ACK, e bonus EXP per il tempo dormito in
visita. La durata dipende dai timestamp, anche quando entrambi i client sono
spenti. Il primo sync dopo la scadenza calcola il premio; ACK e retry non
possono accreditarlo due volte. Il protocollo segnalazioni resta invariato.
Il client conserva gli eventi di acquisto finche il server li conferma.

## Aggiornamento per Companion v1.263: Amici solo con Games

Sostituisci il codice con **A2Companion.gs** e pubblica una nuova versione del
deployment esistente. Non rifare il setup e non cancellare il foglio.
`doGet` deve indicare `games_only` fra le `social_features`.

Il Companion comunica `games_installed` separatamente dalla forma del pet:
anche gli utenti che hanno Games e un uovo possono fare amicizia. Il server
filtra elenco, amici e richieste in base a questa presenza e rifiuta nuove
richieste da o verso chi non ha Games. Il client disattiva subito le notifiche
se Games viene rimosso; l’elenco remoto si aggiorna alla sincronizzazione.
Le relazioni e i premi esistenti non vengono cancellati disinstallando Games:
si ritrovano reinstallandolo. I vecchi client con un pet già nato sono
riconosciuti dal pet; per annunciare un uovo serve il Companion aggiornato.

Prima dell’aggiornamento del server il nuovo client non mostra utenti di cui
non può verificare Games e segnala di aggiornare il servizio prima di inviare
o accettare nuove richieste. Le visite e la rimozione di amicizie restano
compatibili con le capacità eventualmente già installate sul server.

## Aggiornamento per Companion v1.261 / Games 1.9

Per eliminare le amicizie e cercare giocatori in tutto l’elenco online,
sostituisci il codice con il nuovo **A2Companion.gs** e aggiorna il deployment
esistente (nuova versione). Non rieseguire il setup se Amici era già attivo:
utenti, richieste, amicizie e premi restano nel foglio esistente. Il nuovo
`doGet` indica `social_features: ["unfriend", "search"]`.

L’eliminazione dell’amicizia è reciproca e richiede conferma nel client.
Interrompe un incontro eventualmente in corso fra i due utenti, senza
assegnare il premio dell’incontro interrotto. I premi di incontri già terminati
restano disponibili. È possibile inviare successivamente una nuova richiesta.

Con il vecchio server continuano a funzionare richieste, accettazione e visite;
il client segnala che occorre aggiornare il servizio prima di eliminare amici.
La ricerca negli amici e nelle richieste già ricevute funziona subito nel client;
la ricerca globale dei giocatori richiede il nuovo script.

Usa il progetto Apps Script esistente: mantiene lo stesso URL `/exec`, la cartella
dei report, il foglio e le proprietà già configurate. Non serve un secondo servizio.

1. Sostituisci il contenuto di `Code.gs` con **A2Companion.gs** (il file completo
   generato in questa cartella). Non aggiungerlo accanto al vecchio codice: contiene
   già `doPost`, `doGet`, `setup` e tutte le funzioni delle segnalazioni.
2. Esegui **setupMochipiSocial** dall’editor e autorizza l’accesso a Sheets.
   Crea un foglio separato “A2Companion - Amici Mochipi” con Users, Requests e Visits.
   Non occorre rieseguire `setup` delle segnalazioni.
3. **Esegui il deployment → Gestisci deployment → Modifica → Nuova versione →
   Esegui il deployment** sul deployment Web app esistente. Mantieni “Esegui come:
   me” e l’accesso pubblico già necessario all’API del Companion. L’URL rimane uguale.
4. Apri l’URL `/exec`: la risposta deve contenere `social_ready: true` e
   `social_protocol: "mochipi-social-v1"`. Dopo il relog, due Companion aggiornati
   si registrano con il nome rilevato e appaiono nel pannello Amici.

In alternativa conserva il tuo file Reports e aggiungi **MochipiSocial.gs** come
nuovo file. In `doPost`, dopo il blocco `JSON.parse(raw)` e prima del controllo
`data.protocol !== 1`, inserisci:

```js
if (data && data.protocol === 'mochipi-social-v1') return mochipiSocial_(data);
```

Esegui comunque i passaggi 2–3. In questa variante il vecchio `doGet` continua a
mostrare solo lo stato Reports; il funzionamento Amici è identico.

## Contratto e conservazione

L’ID UUID e una credenziale casuale rimangono in
`companion-social-identity.json` nella cartella dati del Companion. Il server
memorizza soltanto l’hash della credenziale. I nomi, il server del personaggio e
la forma/stadio/livello del pet sono visibili agli utenti dell’app. Non vengono
inviati log, inventario reale, email, statistiche di combattimento o wallet.
L’identità rappresenta l’installazione, e conserva gli amici cambiando character.
Conservare il file permette di mantenere l’identità anche spostando l’app.

Il client sincronizza ogni 30 secondi e immediatamente dopo un’azione o relog.
Le richieste ricevute producono una notifica cliccabile anche a rifugio chiuso.
Le visite richiedono amicizia accettata, entrambi i pet nati e presenza recente
(entro 180 secondi). Una sola visita contemporanea per ciascun Mochipi.
La visita è reciproca e dura 3.600 secondi misurati dal server. Le forme dei pet
vengono fotografate all’inizio; cambiare character o resettare durante l’incontro
non cambia il premio. La chiusura dell’app non interrompe la visita: i regali
vengono recuperati alla riconnessione. La visualizzazione segue l’orologio server.

I premi sono generati una volta sul server, separatamente per i due partecipanti,
in base al Mochipi dell’amico (stadio e livello). Un pet avanzato offre più EXP,
Kinah, Soul e materiali migliori; da stadio 2 si aggiungono AP. Il client salva
premio e ricevuta insieme prima di confermare al server: retry e riavvii non
duplicano i premi. EXP sempre limitata dal cap dello stadio; il reset conserva
le ricevute. Un premio non completato resta disponibile offline finché confermato.

I limiti di livello, i contatori e il wallet rimangono quelli di un gioco locale:
il server autentica l’installazione, ma non certifica il farming né verifica
che il nome rilevato appartenga a un account del gioco. Non è un sistema di scambio
di oggetti reali o valuta reale. Il foglio e i token hash non devono essere pubblicati.
Il servizio usa le quote Apps Script e Sheets del proprietario: è adatto a una
comunità piccola; con molti utenti simultanei occorrerà un backend dedicato.

La copia pronta **A2Companion.gs** si ricostruisce concatenando Reports.gs,
una riga vuota e MochipiSocial.gs. Il test `tests/mochipi_social_server.cjs`
esegue le regole reali in una simulazione delle API Sheets/Lock/Properties.

Documentazione deployment: https://developers.google.com/apps-script/guides/web
