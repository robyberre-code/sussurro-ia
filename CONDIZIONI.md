# Sussurro IA — condizioni d'uso e informativa

Questo è il testo che viene mostrato e accettato durante l'installazione. È
riportato qui perché si possa leggere prima di scaricare.

Descrive due cose che è giusto sapere in anticipo: che questa è una versione
beta, e come il programma tratta i tuoi dati.

## Che cosa fa

Sussurro IA trascrive quello che detti e lo inserisce nel campo in cui stavi già
scrivendo. Tieni premuta una combinazione di tasti, parli, rilasci.

## Questa è una versione beta

Il programma è in prova. Può contenere difetti, può comportarsi diversamente da
come è descritto qui, e può cambiare da una versione alla successiva senza
preavviso.

Non affidarti a Sussurro IA per lavoro critico o per testo che non puoi
permetterti di perdere o di veder finire nel posto sbagliato. La dettatura scrive
nella finestra che aveva il fuoco: se il fuoco cambia nel momento sbagliato, il
testo può arrivare altrove.

La trascrizione è prodotta da un modello automatico. Può contenere errori, parole
che non hai detto e punteggiatura arbitraria, e da un audio silenzioso o
disturbato può produrre frasi inventate di sana pianta. **Rileggi sempre quello
che esce prima di usarlo.**

Chi realizza Sussurro IA non si impegna a correggere i difetti, a pubblicare
aggiornamenti, né a garantire la continuità del funzionamento. Usando il
programma accetti che sia così.

## L'audio

L'audio viene registrato **solo mentre tieni premuta la combinazione**, e viene
inviato al servizio di trascrizione che configuri tu, con una chiave API tua — di
preimpostazione Groq. Fuori da quei secondi il microfono non registra. Chi
realizza Sussurro IA non riceve il tuo audio, non lo vede e non lo conserva.

Il rapporto con il servizio di trascrizione è tuo: valgono le condizioni e
l'informativa privacy di quel fornitore, che ti conviene leggere, e il costo delle
trascrizioni è a tuo carico secondo le sue tariffe. Senza collegamento a internet
la dettatura registra ma non produce testo.

## La tastiera

Per riconoscere una combinazione fatta di soli tasti modificatori (Ctrl, Shift,
Win), Windows non offre alternative a un hook di sistema, che per costruzione
riceve ogni tasto premuto sul computer.

Sussurro IA scarta il codice dei tasti che non sono modificatori **nel punto
esatto in cui lo riceve**, prima di qualunque altra operazione: quel codice non
entra nel programma, non viene salvato e non viene trasmesso a nessuno. Di ciò che
digiti resta soltanto il fatto che un tasto è stato premuto, informazione che
serve ad annullare la dettatura quando stai usando un'altra scorciatoia.

Conseguenza pratica: un antivirus può segnalare l'installazione delle API di hook,
perché è lo stesso meccanismo usato dai keylogger.

## Gli appunti

Il testo viene incollato, non digitato: è l'unico modo affidabile di scrivere in
tutte le applicazioni. Sussurro IA legge quindi gli appunti per conservarne il
contenuto, incolla, e ripristina subito quello che c'era prima.

Un'eccezione: se l'inserimento non riesce — per esempio perché la finestra di
destinazione non c'è più — il testo dettato viene lasciato negli appunti, così
puoi incollarlo tu con Ctrl+V invece di perderlo. In quel caso il contenuto
precedente degli appunti non viene ripristinato.

## Il testo dettato

Non viene mai scritto su disco e non compare nei file di diagnostica. Il registro
visibile nel cruscotto vive finché la finestra resta aperta.

## Che cosa resta sul tuo computer

Due preferenze in un file di testo — il modo di uscita e la posizione della
pillola — e la chiave API, custodita nel Gestore credenziali di Windows.

## Che cosa arriva a chi ha realizzato il programma

Niente. Nessuna telemetria, nessuna statistica d'uso, nessun controllo degli
aggiornamenti. L'unica connessione di rete che il programma apre è quella verso
l'endpoint di trascrizione che hai configurato.

## Condizioni

Il software è fornito **"così com'è"**, senza garanzie di alcun tipo, esplicite o
implicite, comprese quelle di funzionamento continuo, di idoneità a uno scopo
particolare e di correttezza del testo prodotto. Chi lo realizza non risponde di
eventuali danni derivanti dal suo uso, né della perdita o della destinazione
errata di testo dettato.

Il software non è firmato con un certificato di code signing: durante
l'installazione Windows SmartScreen mostrerà un avviso.

**Tutti i diritti riservati.**
