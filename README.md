# Simulatore Macchina Enigma (M3)
### Progetto di Gruppo - Sviluppo in JavaFX

[cite_start]Questo repository contiene il progetto per la simulazione della macchina Enigma (versione M3 a 3 rotori)[cite: 4]. [cite_start]Il software è diviso in una componente logica (Model) e un'interfaccia grafica (View)[cite: 5].

---

## Architettura del Progetto
[cite_start]Il lavoro è strutturato seguendo il pattern MVC per separare la logica dalla visualizzazione[cite: 5, 8].

| Classe | Responsabilità | Dipendenze | Fase |
| :--- | :--- | :--- | :--- |
| **Rotore** | Cifra andata/ritorno e gestisce la rotazione | --- | 1 - Model |
| **Riflettore** | Rimappa le lettere in modo simmetrico | --- | 1 - Model |
| **Plugboard** | Scambia coppie di lettere (scambio iniziale/finale) | --- | 1 - Model |
| **EnigmaMachine** | Assembla i componenti e cifra messaggi | Rotore, Riflettore, Plugboard | 1 - Model |
| **EnigmaApp** | Entry point dell'applicazione JavaFX | EnigmaMachine | 2 - View |
| **EnigmaController** | Gestisce gli eventi UI e i tasti | EnigmaMachine | 2 - View |

---

##  Caratteristiche del Modello (Fase 1)
[cite_start]La logica di cifratura segue rigorosamente i parametri storici[cite: 9, 89]:

* [cite_start]**Rotazione**: Avviene **PRIMA** della cifratura di ogni lettera[cite: 67].
* [cite_start]**Meccanismo di scatto**: Il rotore di destra ruota sempre; gli altri scattano solo quando il precedente raggiunge la posizione di notch[cite: 68, 69, 70].
* [cite_start]**Cablaggio Storico**: Sono inclusi i rotori originali I, II, III, IV e V con i relativi punti di scatto (es. Rotore I scatta su 'Q')[cite: 90, 92, 96].



---

##  Interfaccia Grafica (Fase 2)
[cite_start]L'interfaccia JavaFX è progettata per replicare l'esperienza d'uso reale[cite: 75, 76]:
1.  [cite_start]**Tastiera**: 26 tasti cliccabili per l'input[cite: 77].
2.  [cite_start]**Lampboard**: Visualizzazione della lettera cifrata tramite "accensione" luminosa[cite: 78].
3.  [cite_start]**Rotori**: Display per monitorare la posizione corrente delle lettere[cite: 79].
4.  [cite_start]**Configurazione**: Pannelli dedicati per la scelta dei rotori e il setup della plugboard[cite: 80, 81].

---

##  Test e Validazione
[cite_start]Per garantire la fedeltà della simulazione, i risultati sono stati verificati rispetto al simulatore online di riferimento[cite: 72, 101].

**Esempio di validazione standard:**
* [cite_start]**Configurazione**: Rotori I-II-III, Riflettore B, Posizione iniziale AAA, Plugboard vuota[cite: 104, 105, 106, 107].
* **Input**: `AAAAA`
* [cite_start]**Output atteso**: `BDZGO` 

---

##  Requisiti Tecnici
* Java 17 o superiore
* Libreria JavaFX
* [cite_start]FXML per il layout grafico [cite: 75]

---

Membri del gruppo:
Bianolini Daniele,
Boglioni Gabriele,
Bussi Lorenzo,
Grossi Andrea,
