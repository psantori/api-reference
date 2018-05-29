
# Il file di reference API in formato swagger:

- è disponibile in formato yaml su un repo github pubblico
- il formato è il 2.0
- è sempre nominato reference.yaml
- è salvato in una cartella indicata nel formato major.minor (es. 1.40/reference.yaml)
- la cartella di cui al punto precedente è sempre collocata nella cartella (un livello sotto la root) denominata con lo short name del modulo (hub, plan, data, etc.) tutto minuscolo
- il titolo riporta il nome short del modulo, con l'iniziale maiuscola (Hub, Plan, Data, etc.)
- la versione è sempre in formato major.minor.build (1.40.0)
- non viene usato il doppio zero


# Il file della reference in formato HTML
- il file in formato html viene prodotto automaticamente con il tool [redoc-cli](https://github.com/Rebilly/ReDoc/blob/master/cli/README.md) (versione corrente: 0.3.9)
- dal folder contentene il file reference.yaml da convertire, eseguire
```shell
redoc-cli bundle ./reference.yaml -o ./reference.html -t ../../assets/redoc-templates/template.hbs --title="Hub 1.40"
```
- il titolo è sempre nel formato:
    - short version del nome del modulo (Hub, Plan, Data, etc.)
    - uno spazio
    - la versione espressa come major.major

# Il symlink alla versione corrente
- in ogni cartella di modulo vi è un oggetto con speciale significat
- è un symlink alla attuale versione in produzione delle API
- è denominato current
- viene creato eseguendo, dal folder che contiene le varie cartelle con versioni:
```shell
ln -s 1.48 current
```
- in questo modo una cartella contiene sempre le varie versioni (che *non vanno elimiate*) ed il symlink alla versione alm momento in produzione

# Il file changelog
- È presente in formato markdown nella cartella del modulo
- E' unico per modulo, e denominato changelog.md
- Viene aggiornato con una nuova entry ogni qualvolta viene depositata una nuova cartella con major.minor
- Unica eccezione è l'aggiornamento in caso di nuova build che corregge bug noti. In questo caso vi è una entry nel changelog necessariamente con la medesima major.minor version e diversa build
- Il formato è il seguente
```markdown

### Version x.x.x

_Published: dd Month YYYY_

- **New features**
    * item 1
    * item 2
 
- **Minor fix and improvements**
    * item 1
    * item 2
```
- le sottosezioni "New features" e "Minor fix and improvements" sono opzionali, ma ve ne sarà sempre almeno una.
- Una volta salvato il changelog viene validato dal tech lead.


# Il processo di aggiornamento
- Al termine del ciclo di sviluppo, ed in preparazione del rilascio, viene avviato il processo di aggiornamento
- Il processo avviene sul modello fork & pull
- Le request vanno fatte sul branch Translations
- Viene creato nuovo folder con major.minor
- Viene salvato il file reference.yaml
- Viene prodotto il file reference.html
- Viene aggiornato il changelog
- Viene modificato il symlink a current
- Viene creata una PR
- La PR viene accettata dal team prodotto
- Il tech writer controlla il lavoro e corregge ove necessario
- Il team prodotto rigenera gli html in caso di modifica agli swagger
- Il branch Translations viene mergiato sul master dal team prodotto
- Le modifiche sono online

