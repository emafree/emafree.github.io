# emafree.github.io

Sito web portfolio fotografico personale creato con Hugo e pubblicato su GitHub Pages.

## 🎯 Cos'è questo progetto

Questo è un sito statico generato con [Hugo](https://gohugo.io/), un generatore di siti web statici veloce e moderno. Il sito è hostato gratuitamente su GitHub Pages ed è accessibile all'indirizzo https://emafree.github.io/

## 📁 Struttura del progetto

```
emafree.github.io/
├── content/               # Contenuto del sito
│   ├── about.md          # Pagina "Chi sono"
│   └── photos/           # Cartelle delle gallerie fotografiche
│       ├── cover.jpg     # Immagine di copertina homepage
│       ├── paesaggi/     # Esempio: galleria paesaggi
│       ├── persone/      # Esempio: galleria persone
│       ├── street/       # Esempio: galleria street photography
│       ├── VIP/          # Esempio: galleria VIP
│       └── mohai/        # Esempio: galleria mohai
├── themes/               # Tema personalizzato del sito
│   └── emafree/         # Tema Hugo personalizzato
├── hugo.toml            # File di configurazione di Hugo
└── agg_sito.sh          # Script per aggiornare il sito rapidamente
```

## 🚀 Come funziona

1. **Hugo** legge i file dalla cartella `content/` e genera pagine HTML statiche
2. Ogni sottocartella in `content/photos/` diventa automaticamente una **galleria fotografica** sul sito
3. Le foto vengono caricate semplicemente copiandole nelle relative cartelle
4. Il tema personalizzato `emafree` gestisce la visualizzazione delle gallerie e del layout
5. GitHub Actions (configurato in `.github/workflows/`) **compila automaticamente** il sito e lo pubblica su GitHub Pages ogni volta che fai un push

## 📸 Come aggiungere foto

### Metodo 1: Aggiungere foto a una galleria esistente

1. Vai nella cartella della galleria desiderata, ad esempio: `content/photos/paesaggi/`
2. Copia le tue foto (formato JPG, PNG, ecc.) dentro la cartella
3. Le foto verranno automaticamente incluse nella galleria

**Esempio:**
```bash
# Copia una nuova foto nella galleria paesaggi
cp mia-foto.jpg content/photos/paesaggi/
```

### Metodo 2: Creare una nuova galleria

1. Crea una **nuova cartella** dentro `content/photos/` con il nome della tua galleria
   ```bash
   mkdir content/photos/nome-nuova-galleria
   ```

2. Crea un file chiamato `index.md` dentro la nuova cartella con questo contenuto:
   ```markdown
   ---
   title: "Nome della Galleria"
   ---

   # Descrizione della Galleria

   Qui puoi scrivere una breve descrizione della galleria.
   ```

3. Aggiungi le tue **foto** dentro la cartella:
   ```bash
   cp foto1.jpg foto2.jpg content/photos/nome-nuova-galleria/
   ```

**Struttura finale della nuova galleria:**
```
content/photos/nome-nuova-galleria/
├── index.md       # Informazioni e titolo della galleria
├── foto1.jpg      # Prima foto
├── foto2.jpg      # Seconda foto
└── foto3.jpg      # Terza foto
```

## 🔄 Come pubblicare gli aggiornamenti

Dopo aver aggiunto foto o creato nuove gallerie:

### Metodo rapido (usando lo script)
```bash
./agg_sito.sh
```

### Metodo manuale
```bash
git add .
git commit -m "Aggiunte nuove foto"
git push
```

Dopo il push, **GitHub Actions** compilerà automaticamente il sito e lo pubblicherà online in pochi minuti.

## 🎨 Personalizzazione

- **Titolo del sito**: modifica il file `hugo.toml` alla riga `title = "emafree"`
- **Tema**: il tema personalizzato si trova in `themes/emafree/`
- **Pagina About**: modifica `content/about.md`
- **Immagine di copertina**: sostituisci `content/photos/cover.jpg`

## 🛠️ Requisiti (solo per sviluppo locale)

Se vuoi testare il sito in locale prima di pubblicarlo:

1. Installa [Hugo](https://gohugo.io/installation/)
2. Clona il repository
3. Esegui:
   ```bash
   hugo server
   ```
4. Apri il browser su `http://localhost:1313`

## 📝 Note importanti

- **Formati supportati**: JPG, JPEG, PNG, GIF
- **Nome file**: usa nomi descrittivi per le foto (es: `20260126_Sentina_P1260604.jpg`)
- **Dimensioni**: le foto grandi verranno ottimizzate automaticamente dal tema
- **Organizzazione**: ogni galleria è indipendente, puoi averne quante ne vuoi

## 📄 Licenza

Questo è un portfolio personale. Tutte le fotografie sono © emafree.
