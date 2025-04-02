# BMS Logistics

Sistema gestionale per la logistica, con funzionalità di tracciamento transazioni, gestione clienti, preventivi, e pagamenti.

## Funzionalità

- Dashboard con analisi finanziarie
- Gestione aziende clienti
- Gestione transazioni (entrate/uscite)
- Sistema di preventivi con calcolo percorsi
- Gestione pagamenti e scadenze
- Esportazione preventivi in PDF

## Requisiti di Sistema

- Node.js 18.x o superiore
- MongoDB (locale o remoto)
- NPM 9.x o superiore

## Istruzioni per il Deployment

### Deployment su Vercel

1. **Crea un account su Vercel** (se non ne hai già uno): https://vercel.com/signup

2. **Installa Vercel CLI**:
   ```
   npm install -g vercel
   ```

3. **Configura il database MongoDB**:
   - Crea un cluster MongoDB su [MongoDB Atlas](https://www.mongodb.com/cloud/atlas)
   - Ottieni la stringa di connessione

4. **Modifica il file vercel.json**:
   - Aggiorna l'URL di connessione MongoDB con le tue credenziali
   ```json
   "env": {
     "DATABASE_URL": "mongodb+srv://tuousername:tuapassword@tuocluster.mongodb.net/bms-logistics?retryWrites=true&w=majority"
   }
   ```

5. **Esegui il deploy**:
   ```
   vercel
   ```
   
6. **Per aggiornamenti successivi**:
   ```
   vercel --prod
   ```

### Deployment su Hosting Tradizionale

1. **Crea la build di produzione**:
   ```
   npm run build
   ```

2. **Configura il file .env**:
   - Crea un file `.env` nella radice del progetto
   - Aggiungi la connessione MongoDB:
   ```
   DATABASE_URL="mongodb://username:password@host:port/bms-logistics?retryWrites=true&w=majority"
   ```

3. **Avvia l'applicazione**:
   ```
   npm start
   ```
   
4. **Configurazione del web server**:
   - Configura Nginx o Apache per fare proxy verso l'applicazione Node.js
   - Esempio di configurazione Nginx:
   ```
   server {
     listen 80;
     server_name tuodominio.com;
     
     location / {
       proxy_pass http://localhost:3000;
       proxy_http_version 1.1;
       proxy_set_header Upgrade $http_upgrade;
       proxy_set_header Connection 'upgrade';
       proxy_set_header Host $host;
       proxy_cache_bypass $http_upgrade;
     }
   }
   ```

## Contatti

Per assistenza contattare: gustavo@bmslogistics.it o +39 3493306316

## Licenza

Tutti i diritti riservati © BMS Logistics 2023 

## Passo 1: Correggiamo gli errori

Esegui questi comandi per pulire la cache e installare correttamente le dipendenze:

```
cd "C:\Users\henri\Desktop\bms logistics"
rmdir /s /q .next
rmdir /s /q node_modules
npm install
npm install jspdf jspdf-autotable
```

Una volta fatto questo, puoi verificare che l'applicazione funzioni localmente:

```
set PORT=3333 && npm run dev 
```

## Aggiunta:

### Aggiunta per Vercel

1. **Accedi a Vercel**:
   ```
   vercel login
   ```

2. **Segui le istruzioni a schermo per collegare il tuo dominio**

3. **Dopo aver collegato il dominio, esegui il deploy**:
   ```
   vercel
   ```

4. **Per aggiornamenti successivi**:
   ```
   vercel --prod
   