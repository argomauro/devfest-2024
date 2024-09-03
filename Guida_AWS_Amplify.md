
# Guida alla Configurazione e Deploy su AWS Amplify

Questa guida ti aiuterà a configurare e distribuire il progetto su AWS Amplify a partire da un fork del repository originale.

## 1. Fork del Repository
- Vai al repository originale su GitHub.
- Clicca su **Fork** in alto a destra per creare un fork del repository sul tuo account GitHub.

## 2. Clona il Repository Forkato
- Clona il repository forkato sulla tua macchina locale utilizzando il comando:
  ```bash
  git clone https://github.com/tuo-account/repo-forkato.git
  ```
- Sostituisci `tuo-account` e `repo-forkato` con i tuoi dettagli specifici.

## 3. Configurazione dell'Ambiente Locale
- Accedi alla directory del progetto:
  ```bash
  cd repo-forkato
  ```
- Assicurati di avere Node.js v20 o superiore installato sulla tua macchina.
- Installa le dipendenze del progetto:
  ```bash
  npm install
  ```
- Avvia il server di sviluppo per verificare che tutto funzioni correttamente:
  ```bash
  npm run dev
  ```

## 4. Personalizzazione del Contenuto
- Aggiorna i file JSON nella directory `/data` e `/public/` secondo le tue esigenze.
- Carica le immagini relative a Speakers, Team e Sponsors nelle rispettive directory all'interno di `/public/speakers/` e `/public/team/`. Assicurati che le immagini siano in un formato 1:1.

## 5. Generazione della Build per la Produzione
- Genera una build ottimizzata per la produzione:
  ```bash
  npm run generate
  ```
- Verrà creata una directory `.output/public` pronta per l'hosting statico.

## 6. Configurazione su AWS Amplify
- Accedi alla console AWS e vai su **AWS Amplify**.
- Seleziona "New app" e poi "Host web app".
- Connettiti al repository GitHub e seleziona il tuo fork.
- Amplify configurerà automaticamente le build e le distribuzioni. Configura la pipeline di build aggiungendo i seguenti comandi alla fase di build:
  ```bash
  npm install
  npm run generate
  ```
- Specifica la directory di output `.output/public` come directory di output della build.

## 7. Configurazione del Dominio (Opzionale)
- Se desideri usare un dominio personalizzato, puoi collegarlo dalla console di AWS Amplify, seguendo le istruzioni per la configurazione DNS.

## 8. Distribuzione
- Ogni volta che esegui un commit e push nel tuo repository forkato, Amplify rileverà automaticamente le modifiche e avvierà una nuova build e distribuzione del sito.

## 9. Monitoraggio e Manutenzione
- Monitora la distribuzione attraverso la console di AWS Amplify.
- Puoi configurare degli alert e gestire le versioni direttamente da Amplify, consentendo anche il rollback delle versioni in caso di problemi.

## Note
- Questa guida è specifica per l'integrazione con AWS Amplify. Se in futuro decidi di utilizzare Firebase, puoi seguire le istruzioni fornite nella documentazione originale del progetto.
