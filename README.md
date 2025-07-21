# progetto-architettura-dati-with-ml

## Struttura del progetto:

### Fase 1 – codice base (senza rumore): 
- **AD_fase_1.ipynb** contiene il codice di riferimento, dove i dati di training sono puliti, ovvero non sono presenti errori, rumore, outlier, valori mancanti o duplicazioni. Questo esperimento serve come baseline per confrontare tutte le versioni successive del progetto.

### Fase 2 – introduzione di rumore nei dati di training: 

Parte I: si introduce il rumore singolo ovvero gli effetti isolati di un solo tipo di errore
- **label_noise.ipynb** introduce il rumore nelle etichette (label noise) -> sono le modifiche casuali in y_train
- **feature_noise.ipynb** introduce il rumore numerico sulle feature (feature noise) -> si aggiunge di rumore gaussiano alle feature
- **missing_values.ipynb** introduce valori mancanti nelle feature
- **feature_outliers.ipynb** introduce outlier numerici (valori anomali) nelle feature
- **duplicates_features.ipynb** introduce la duplicazione artificiale di righe nel training set –> simula dati ridondanti


Parte II: si introduce il rumore combinato ovvero gli effetti di più errori simultanei
- **label_noise_with_feature_noise.ipynb** introduce il rumore nelle etichette + rumore numerico nelle feature
- **label_noise_with_missing_values.ipynb** introduce il rumore nelle etichette + valori mancanti nelle feature
- **feature_noise_with_feature_outliers.ipynb** introduce il rumore numerico nelle feature + outlier artificiali
- **duplicates_features_with_feature_noise.ipynb** introduce il duplicazioni di righe + rumore numerico nelle feature

## Obiettivo del progetto:
- Valutare la robustezza di diversi modelli ML (es. DT, RF, SVM, MLP) a differenti scenari di degradazione dei dati.

- Analizzare separatamente e in combinazione gli effetti di vari tipi di “sporco” sui dati (noise, missing, duplicati, outlier).

- Confrontare con la baseline (Fase 1) per evidenziare le variazioni nelle performance.


