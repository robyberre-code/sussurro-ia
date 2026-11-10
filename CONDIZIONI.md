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

L'audio viene registrato **solo mentre tieni premuta la combinazione** — o, se
hai attivato le mani libere (spente di preimpostazione), fra il tocco che le apre
e quello che le chiude, per al massimo dieci minuti — e viene inviato al servizio
di trascrizione che configuri tu, con una chiave API tua — di preimpostazione
Groq. Fuori da quei secondi il microfono non registra. Chi realizza Sussurro IA
non riceve il tuo audio, non lo vede e non lo conserva. Se premi Esc mentre
registri, la dettatura viene annullata e non viene trascritta.

Prima dell'invio il programma toglie dal clip i silenzi lunghi, e ne scarta uno
che non contiene voce (è un'impostazione, accesa di preimpostazione). Verso il
servizio cloud l'audio viaggia compresso in FLAC, senza perdita di qualità.

Il rapporto con il servizio di trascrizione è tuo: valgono le condizioni e
l'informativa privacy di quel fornitore, che ti conviene leggere, e il costo delle
trascrizioni è a tuo carico secondo le sue tariffe. Con il motore cloud, senza
collegamento a internet la dettatura registra ma non produce testo.

## Il motore sul computer

In alternativa al cloud puoi scegliere nel cruscotto di trascrivere sul computer:
lo fa il programma stesso, con un modello di riconoscimento vocale che scegli e
scarichi tu. In quel caso **l'audio non esce dal computer**. Il modello si scarica
solo quando premi «scarica», dal repository pubblico di whisper.cpp su Hugging
Face (huggingface.co), e viene verificato con la sua impronta prima di essere
usato; resta in `%LOCALAPPDATA%\com.sussurroia.app\modelli` finché non lo
elimini. Se il modello manca, il programma non ripiega sul cloud e non invia
l'audio a nessun altro: la dettatura fallisce con un errore.

Solo la dettatura semplice funziona così. Traduzione, modo prompt e
perfezionamento del testo usano sempre Groq: gli viene inviato il testo già
trascritto — non l'audio — con la tua chiave API. Senza quella chiave il
programma inserisce il testo trascritto così com'è.

I modelli sono quelli pubblicati dal progetto whisper.cpp: chi realizza Sussurro
IA non li ha addestrati e non risponde del servizio che li ospita.

## La tastiera

Per riconoscere una combinazione fatta di soli tasti modificatori (Ctrl, Shift,
Alt, Win), Windows non offre alternative a un hook di sistema, che per
costruzione riceve ogni tasto premuto sul computer.

Sussurro IA scarta il codice dei tasti che non sono modificatori **nel punto
esatto in cui lo riceve**, prima di qualunque altra operazione: quel codice non
entra nel programma, non viene salvato e non viene trasmesso a nessuno. Di ciò che
digiti resta soltanto il fatto che un tasto è stato premuto, informazione che
serve ad annullare la dettatura quando stai usando un'altra scorciatoia.

C'è una sola eccezione, ed è un'informazione sola: mentre stai registrando, il
programma distingue il tasto Esc dagli altri, perché Esc annulla la dettatura, e
lo assorbe in modo che non arrivi anche all'applicazione che hai sotto. Oltre
allo stato dei modificatori, dunque, nel programma entra un solo dato in più —
«era Esc» — e solo mentre registri. Fuori dalla registrazione Esc è un tasto come
gli altri e non viene identificato. Nessun altro tasto viene mai riconosciuto,
salvato o trasmesso.

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
visibile nel cruscotto vive finché la finestra resta aperta. L'ultima dettatura
viene tenuta solo in memoria, per il comando «Copia l'ultima dettatura», e
sparisce quando chiudi il programma.

## Il registro tecnico

Il cruscotto mostra un registro tecnico con le ultime 500 righe di diagnosi (per
esempio: quale programma ha letto gli appunti, se il fuoco è tornato sulla
finestra giusta, quanti tentativi sono serviti). Vive solo in memoria: non viene
scritto su disco e sparisce quando chiudi il programma. Contiene nomi di programmi
e titoli di finestre — che possono coincidere con il nome di un documento — ma
mai il testo dettato. Non viene inviato a nessuno: lo copi negli appunti tu, e
solo quando premi «copia diagnostica». Rileggilo prima di allegarlo a una
segnalazione.

## Che cosa resta sul tuo computer

Un file di testo (`impostazioni.json`) con le tue preferenze, e nessun segreto: il
modo di uscita, la posizione della pillola e quella del cruscotto; quale coppia di
scorciatoie usi; i modelli scelti a mano; se il perfezionamento del testo, i suoni
di feedback, le mani libere e il taglio dei silenzi sono accesi; il nome del
microfono scelto; il motore di trascrizione (cloud o sul computer) e quale modello
locale hai scelto; il dizionario personalizzato, cioè le parole e le sostituzioni
che hai scritto tu nel cruscotto (testo tuo, non dettato, che nel file resta in
chiaro).

La chiave API di Groq è custodita nel Gestore credenziali di Windows, non nel
file. I modelli scaricati stanno in `%LOCALAPPDATA%\com.sussurroia.app\modelli`.

## Che cosa arriva a chi ha realizzato il programma

Niente. Nessuna telemetria, nessuna statistica d'uso, nessun controllo degli
aggiornamenti. Le uniche connessioni di rete che il programma apre sono quella
verso il servizio che hai configurato — il servizio di trascrizione e, per
traduzione, modo prompt e perfezionamento, Groq — e il download di un modello
locale, solo quando lo chiedi tu.

## Condizioni

Il software è fornito **"così com'è"**, senza garanzie di alcun tipo, esplicite o
implicite, comprese quelle di funzionamento continuo, di idoneità a uno scopo
particolare e di correttezza del testo prodotto. Chi lo realizza non risponde di
eventuali danni derivanti dal suo uso, né della perdita o della destinazione
errata di testo dettato.

Il software non è firmato con un certificato di code signing: durante
l'installazione Windows SmartScreen mostrerà un avviso.

**Tutti i diritti riservati.**
