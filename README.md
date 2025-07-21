# progetto-architettura-dati-with-ml

## Obiettivo del progetto:
- Valutare la robustezza di diversi modelli di machine learning (es. Decision Tree, Random Forest, SVM, MLP) in presenza di scenari di degradazione dei dati.

- Analizzare separatamente e in combinazione gli effetti di vari tipi di “sporco” sui dati (noise, missing, duplicati, outlier).

- Confrontare le prestazioni con la baseline (Fase 1) per evidenziare le variazioni causate dai diversi tipi di rumore.
  
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

## Scelta dei tipi di errori testati:

- **Label Noise**, perchè spesso citato come causa frequente di degrado nei modelli ML supervisionati. Non sempre facilmente rilevabile.

- **Feature Noise**, perchè spesso presente in contesti reali con sensori o inserimenti manuali. Impatta le distribuzioni e le correlazioni.

- **Missing Values**, perchè sono molto comuni nel mondo reale- Possono alterare il comportamento dei modelli se non gestiti correttamente.

- **Feature Outliers**, perchè pochi valori estremi possono compromettere l’efficacia di modelli non robusti. Vanno identificati e analizzati.

- **Duplicates Features**, perchè introducono bias nel training se non riconosciuti.

- **Label Noise** + **Feature Noise**, perché introduce incertezza sia nell’input che nell’output atteso, compromettendo l’apprendimento del modello.

- **Label Noise** + **Missing Values**, perché riflette scenari reali di raccolta dati in ambito sanitario, dove i dati clinici possono essere parziali e annotati in modo impreciso.

- **Feature Noise** + **Feature Outliers**, perché aiuta di valutare la capacità del modello di discriminare tra deviazioni tollerabili e anomalie significative.

- **Feature Noise** + **Duplicates Features**, perché unisce due distorsioni tipiche della fase di acquisizione dati: ridondanza strutturale (duplicazioni non rilevate) e rumore numerico.
