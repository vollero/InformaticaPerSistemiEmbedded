# Dispense 
# Introduzione agli Automi a Stati Finiti (ASF)

## Indice

1. **Introduzione agli Automi a Stati Finiti**
2. **Definizione Formale**
3. **Modalità di Rappresentazione**
   - 3.1 Diagrammi di Stato
   - 3.2 Tabelle di Transizione
   - 3.3 Rappresentazione Matematica
4. **Modelli di Automa**
   - 4.1 Automa di Moore
   - 4.2 Automa di Mealy
5. **Esempi di Utilizzo**
6. **Applicazioni Avanzate degli Automi**
7. **Attività Pratiche ed Esercizi**
8. **Glossario**
9. **Riferimenti**

---

## 1. Introduzione agli Automata a Stati Finiti

### Cos'è un Automa a Stati Finiti?

Un **Automa a Stati Finiti (ASF)** è un modello matematico utilizzato per descrivere sistemi che possono trovarsi in uno di un numero finito di stati. Gli automi a stati finiti sono fondamentali nell'informatica teorica e trovano applicazioni in vari campi, tra cui:

- **Riconoscimento di pattern**: Come nel caso dei linguaggi formali e dei parser.
- **Design di circuiti digitali**: Modellazione di circuiti sequenziali.
- **Analisi linguistica**: Comprensione delle strutture grammaticali.
- **Verifica di Algoritmi, Sistemi e Protocolli**: Utilizzati per dimostrare la correttezza formale e l'affidabilità di algoritmi, sistemi e protocolli.

### Perché Studiare gli ASF?

- **Comprensione dei Sistemi Sequenziali**: Molti sistemi possono essere modellati come ASF e il loro comportamento può essere descritto attraverso una evoluzione su un insieme di stati discreti di funzionamento.
- **Base per la Teoria dei Linguaggi Formali**: Gli ASF sono fondamentali per la progettazione di compilatori e interpreti.
- **Verifica e Validazione**: Gli ASF sono uno strumento essenziale per l'analisi formale di algoritmi e protocolli, permettendo di verificare e di garantire che si comportino come previsto.
- **Applicazioni Pratiche**: Gli ASF possono essere usati per il controllo dei processi industriali, il design di protocolli di comunicazione, l'intelligenza artificiale.

---

## 2. Definizione Formale

Un **Automa a Stati Finiti (ASF)** è definito come una 5-upla:

$$
M = (Q, \Sigma, \delta, q_0, F)
$$

dove:

- **$Q$**: Insieme finito di stati.
- **$\Sigma$**: Alfabeto finito di simboli di input.
- **$\delta$**: Funzione di transizione $\delta: Q \times \Sigma \rightarrow Q$.
- **$q_0$**: Stato iniziale, dove $q_0 \in Q$.
- **$F$**: Insieme degli stati finali (stati accettanti), dove $F \subseteq Q$.

### Componenti Chiave

- **Stati $Q$**: Rappresentano le possibili configurazioni del sistema.
- **Alfabeto $\Sigma$**: Insieme dei simboli che l'automa può processare.
- **Funzione di Transizione $\delta$**: Definisce come l'automa cambia stato in risposta a un input.
- **Stato Iniziale $q_0$**: Rappresenta la configurazione iniziale del sistema.
- **Stati Finali $F$**: Rappresenta gli stati in cui si considera valida in terminazione una evoluzione del sistema.

---

## 3. Modalità di Rappresentazione

### 3.1 Diagrammi di Stato

- **Stati**: Rappresentati da cerchi.
- **Transizioni**: Frecce etichettate con il simbolo di input.
- **Stato Iniziale**: Indicata da una freccia senza origine che punta verso lo stato iniziale.
- **Stati Finali**: Cerchi doppi per evidenziare gli stati accettanti.

*Esempio di Diagramma di Stato:*

(Disegnare un diagramma corrispondente all'automa in questione)

### 3.2 Tabelle di Transizione

La tabella di transizione può essere rappresentata mettendo gli **stati attuali** per riga e gli **input** per colonna. Ogni cella indica lo **stato successivo**.

*Esempio di Tabella di Transizione:*

| Stato \ Input | a           | b           |
|---------------|-------------|-------------|
| $q_0$         | $q_1$       | $q_0$       |
| $q_1$         | $q_1$       | $q_0$       |

### 3.3 Rappresentazione Matematica

Definizione della funzione di transizione come un insieme di coppie ordinate o una funzione.

---

## 4. Modelli di Automa

Esistono due modelli principali di automi a stati finiti:

### 4.1 Automa di Moore

- **Caratteristica**: L'output dipende solo dallo **stato attuale**.
- **Definizione**: Un automa di Moore è una 6-upla $(Q, \Sigma, \Delta, \delta, \lambda, q_0)$, dove:
  - $Q$: Insieme finito di stati.
  - $\Sigma$: Alfabeto finito di input.
  - $\Delta$: Alfabeto finito di output.
  - $\delta$: Funzione di transizione $\delta: Q \times \Sigma \rightarrow Q$.
  - $\lambda$: Funzione di output $\lambda: Q \rightarrow \Delta$.
  - $q_0$: Stato iniziale.

### 4.2 Automa di Mealy

- **Caratteristica**: L'output dipende sia dallo **stato attuale** che dall'**input corrente**.
- **Definizione**: Un automa di Mealy è una 6-upla $(Q, \Sigma, \Delta, \delta, \lambda, q_0)$, dove:
  - $Q$, $\Sigma$, $\Delta$, $q_0$ come sopra.
  - $\delta$: Funzione di transizione $\delta: Q \times \Sigma \rightarrow Q$.
  - $\lambda$: Funzione di output $\lambda: Q \times \Sigma \rightarrow \Delta$.

### Differenze Chiave

- **Moore**: L'output è associato agli stati.
- **Mealy**: L'output è associato alle transizioni.

---

## 5. Esempi di Utilizzo

### Esempio 1: Riconoscimento di Parole che Terminano con 'a'

**Problema**: Costruire un automa che riconosce parole sull'alfabeto $\Sigma = \{a, b\}$ che terminano con 'a'.

**Automa di Moore**

- **Stati**: $Q = \{q_0, q_1\}$
- **Output**: $\Delta = \{0, 1\}$
- **Funzione di Output**:
  - $\lambda(q_0) = 0$
  - $\lambda(q_1) = 1$
  
*Il valore di output indica se la stringa corrente termina con 'a' (1) o no (0).*

**Funzione di Transizione**:

| Stato \ Input | a           | b           |
|---------------|-------------|-------------|
| $q_0$         | $q_1$       | $q_0$       |
| $q_1$         | $q_1$       | $q_0$       |

**Interpretazione**:

- **$q_0$**: Ultimo carattere non è 'a'.
- **$q_1$**: Ultimo carattere è 'a'.

### Esempio 2: Parità di Bit in una Stringa Binaria

**Problema**: Progettare un automa che calcola la parità (pari o dispari) del numero di '1' in una stringa binaria.

**Automa di Mealy**

- **Stati**: $Q = \{q_{\text{pari}}, q_{\text{dispari}}\}$
- **Output**: $\Delta = \{0, 1\}$
- **Funzione di Output**:

| Stato \ Input | 0       | 1       |
|---------------|---------|---------|
| $q_{\text{pari}}$    | 0       | 1       |
| $q_{\text{dispari}}$ | 1       | 0       |

**Funzione di Transizione**:

| Stato \ Input | 0                     | 1                     |
|---------------|-----------------------|-----------------------|
| $q_{\text{pari}}$    | $q_{\text{pari}}$    | $q_{\text{dispari}}$ |
| $q_{\text{dispari}}$ | $q_{\text{dispari}}$ | $q_{\text{pari}}$    |

---

## 6. Applicazioni Avanzate degli Automata

### Verifica di Algoritmi e Protocolli

Gli automi sono utilizzati per modellare e verificare il comportamento di algoritmi e protocolli di comunicazione. Questo permette di:

- **Analizzare la Correttezza**: Garantire che l'algoritmo o il protocollo si comporti come previsto in tutte le possibili condizioni.
- **Individuare Deadlock e Starvation**: Identificare situazioni in cui il sistema potrebbe bloccarsi o non progredire.
- **Formal Verification**: Usare strumenti formali per dimostrare proprietà del sistema.

*Esempio*: Modellare un protocollo di comunicazione come un automa per verificare che i messaggi vengano scambiati correttamente e che non si verifichino *race condition*.

---

## 7. Attività Pratiche ed Esercizi

### Esercizio 1: Riconoscimento di Numeri Divisibili per 3

**Obiettivo**: Progettare un automa che riconosce stringhe di cifre binarie che rappresentano numeri divisibili per 3.

**Istruzioni**:

1. Definire gli stati che rappresentano il resto della divisione per 3.
2. Costruire la tabella di transizione.
3. Disegnare il diagramma di stato.

### Esercizio 2: Controllo di Accesso con Sequenza PIN

**Problema**: Un sistema permette l'accesso dopo l'inserimento di una sequenza corretta di cifre (ad esempio, "1234").

**Compiti**:

1. Modellare il sistema come un automa di Mealy.
2. Definire gli stati, la funzione di transizione e la funzione di output.
3. Verificare che l'automa accetti solo la sequenza corretta.

### Esercizio 3: Conversione tra Automata di Moore e Mealy

**Obiettivo**: Dato un automa di Moore, convertirlo in un automa di Mealy equivalente, e viceversa.

**Istruzioni**:

1. Prendere un automa di Moore fornito.
2. Definire l'automa di Mealy equivalente.
3. Dimostrare che entrambi gli automi producono lo stesso output per ogni input.

---

## 8. Glossario

- **Automa**: Modello matematico per la computazione di sequenze di input.
- **Stato**: Rappresenta una condizione o configurazione in cui l'automa può trovarsi.
- **Transizione**: Il passaggio da uno stato a un altro in risposta a un input.
- **Alfabeto**: Insieme finito di simboli utilizzati come input.
- **Funzione di Transizione**: Regola che determina le transizioni tra stati.
- **Stato Iniziale**: Stato in cui l'automa inizia l'elaborazione.
- **Stato Finale**: Stato che determina se l'automa termina la sua evoluzione in condizione corretta.
- **Automa di Moore**: Modello in cui l'output dipende solo dallo stato attuale.
- **Automa di Mealy**: Modello in cui l'output dipende dallo stato attuale e dall'input corrente.

---

## 9. Riferimenti

- **Libri Consigliati**:

  - Hopcroft, J. E., Motwani, R., & Ullman, J. D. (2006). *Introduction to Automata Theory, Languages, and Computation*. Addison-Wesley.
  - Sipser, M. (2012). *Introduction to the Theory of Computation*. Cengage Learning.

- **Risorse Online**:

  - [Tutorial sugli Automata a Stati Finiti](https://www.geeksforgeeks.org/introduction-of-finite-automata/)
  - [Video Lezioni corso MIT *Mathematics for Computer Science*](https://www.youtube.com/playlist?list=PLB7540DEDD482705B)

---

## Note Aggiuntive

- **Pratica**: La comprensione degli automi migliora con la pratica. Si consiglia di provare a modellare diversi sistemi reali.
- **Conversione tra Modelli**: Gli automi di Moore e Mealy possono essere convertiti l'uno nell'altro, anche se potrebbero differire nel numero di stati.
- **Applicazioni Avanzate**: Oltre alla teoria, gli automi sono utilizzati in strumenti di verifica formale come i model checker.

---
