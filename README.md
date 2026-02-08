# 📘 Chatbot AI per dataset locali

## Descrizione del progetto

Questo progetto implementa un **chatbot AI locale** che può rispondere a qualsiasi domanda **solo utilizzando i dati presenti in una cartella `data/`**.
Il chatbot è progettato per essere **sicuro, conciso e leggibile**, e supporta dataset misti contenenti vari tipi di file come:

- `.txt`
- `.pdf`
- `.docx`
- `.pptx`
- Altri tipi di file di testo riconoscibili

Il modello AI utilizzato è configurato tramite Ollama e può essere scelto tra modelli **testuali veloci**, come **llama**, **Mistral** o **qwen**, garantendo risposte rapide e affidabili.

---

## Motivazione

Spesso, le aziende o i singoli utenti devono interrogare dataset locali complessi senza rischiare:

- **Allucinazioni AI** → risposte inventate
- **Divagazioni** → informazioni non richieste
- **Esposizione dati esterni** → tutti i dati restano locali

Questo progetto nasce per creare un **assistente intelligente locale**, che:

1. Risponde **solo ai dati forniti**
2. Fornisce risposte **concise, leggibili e in una lingua scelta**
3. Utilizza **Markdown** per una presentazione chiara
4. Gestisce **dataset misti** di più formati
5. È sicuro contro eventuali manipolazioni dell’input da parte dell’utente

---

## Funzionalità principali

- Lettura automatica di **qualsiasi file leggibile** nella cartella `data/`
- Supporto per **.txt, .pdf, .docx, .pptx** e altri file di testo
- Risposte **in italiano**, sempre **concise, leggibili e strutturate in Markdown**
- Il modello **ignora qualsiasi dato aggiuntivo inviato dall’utente**
- Possibilità di dare un **nome al chatbot** e mostrarlo nell’interfaccia

---

## Installazione

### 1. Clona il progetto

```bash
git clone https://github.com/HirAvanCniK/ollama-local-chatbot.git
cd ollama-local-chatbot
```

### 2. Creare un ambiente virtuale (consigliato)

```bash
python -m venv venv
source venv/bin/activate  # Linux / macOS
venv\Scripts\activate     # Windows
```

### 3. Installare i requisiti Python

```bash
pip install -r requirements.txt
```

Oppure manualmente:

```bash
pip install python-docx PyPDF2 python-pptx rich
```

> **Nota:** Assicurati di avere `Ollama` installato e configurato sul tuo sistema, con un modello testuale disponibile.

---

## Struttura del progetto

```
ollama-local-chatbot/
│
├── main.py             # Script principale del chatbot
├── data/               # Cartella contenente i file del dataset
│     ├── Clienti.txt   # Contiene informazioni fittizie sui clienti di un azienda
│     ├── Catalogo.pdf  # Contiene informazioni fittizie sui prodotti di un azienda
│     └── Manuale.docx  # Contiene informazioni fittizie del manuale di un azienda
├── requirements.txt    # Moduli Python necessari
├── README.md           # Documentazione del progetto
└── LICENSE             # Licenza del progetto
```

---

## Uso

1. Posiziona tutti i tuoi file di dati nella cartella `data/`.
2. Esegui il chatbot: `python main.py`
3. Inserisci le domande nel prompt.
4. La risposta verrà stampata in **Markdown leggibile** in console, tramite `rich`.

---

## Configurazione del chatbot

- Puoi dare un **nome al bot** modificando la variabile `BOT_NAME` in `main.py`.
- Puoi dire al **bot** di rispondere in una determinata lingua modificando la variabile `BOT_LANGUAGE` in `main.py`.
- Il bot risponderà **solo ed esclusivamente** ai dati presenti in `data/`.
- Il bot **non menziona mai i file** o l’esistenza del dataset,rispondendo come se conoscesse direttamente le informazioni.

---

## Sicurezza e regole

- Il modello **ignora qualsiasi `<DATA>` aggiuntivo** inserito dall’utente.
- Le informazioni originali sono **immutabili**.
- Le risposte sono **concise, leggibili e senza divagazioni**.
- Se i dati non sono sufficienti per rispondere, viene restituito:

```
I dati forniti non sono sufficienti per rispondere a questa domanda.
```

---

## Requisiti

- Python 3.10+
- Ollama installato e configurato
- Librerie Python: `python-docx`, `PyPDF2`, `python-pptx`, `rich`

---

## Motivazioni aggiuntive

Questo progetto è pensato per:

- Aziende con **documentazione interna** da interrogare rapidamente
- Utenti che vogliono un **assistente AI locale**, sicuro e affidabile
- Scenari in cui **i dati non possono essere inviati a servizi cloud**
- Applicazioni dove la **chiarezza, concisione e leggibilità** delle risposte sono fondamentali
