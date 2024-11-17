# Prog2@UniMI Handouts

[![License: GPL v3](https://img.shields.io/badge/License-GPL%20v3-blue.svg)](http://www.gnu.org/licenses/gpl-3.0)
[![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC%20BY--SA%204.0-blue.svg)](http://creativecommons.org/licenses/by-sa/4.0/)
[![Workflow results](https://github.com/prog2-unimi/handouts/actions/workflows/gradle.yml/badge.svg)](https://github.com/prog2-unimi/handouts/actions/workflows/gradle.yml)

Questo repository contiene gli *handout* dell'insegnamento di [Programmazione
II](https://prog2.di.unimi.it/) del corso di laurea in
[Informatica](https://informatica.cdl.unimi.it/it) dell'[Università degli Studi
di Milano](http://www.unimi.it/).

Il materiale di questo repository (aggiornato periodicamente) consiste nella
collezione del *materiale didattico* prodotto dal docente sostanzialmente nella
forma in cui si trova al termine di ciascuna lezione. Per questa ragione il suo
contenuto **non è assolutamente inteso come sostituivo dei libri di testo e
della documentazione suggerita** e in nessun caso è da ritenersi *esaustivo* e
*privo di errori*, ma **è provvisto al solo scopo di consentire agli studenti di
ripercorrere i passi visti a lezione e suggerire alcuni esercizi**.

## Organizzazione del materiale

Il contenuto di questo *repository* segue l'organizzazione dei file prevista dal
*build automation tool* scelto per la gestione del codice (si veda la prossima
sezione per maggiori dettagli).

In particolare, i **file sorgenti** sono contenuti nella directory
`src/main/java`, divisi in sottodirectory una per ciascuna lezione; più nel
dettaglio, ad esempio nel caso della *decima lezione*, le directory

```
src/main/java/it/unimi/di/prog2/h10
src/main/java/it/unimi/di/prog2/e10
src/main/java/it/unimi/di/prog2/s10
```

contengono rispettivamente il codice relativo a:

* gli **esempi presentati in classe** (cartella `h10`),
* gli **esercizi assegnati per casa** (cartella `e10`) e
* le **soluzioni di una selezione degli esercizi** assegnati per casa (cartella
  `s10`); si noti che non tutte le lezioni hanno esercizi assegnati e non per
  tutti gli esercizi assegnati viene pubblicata una soluzione.

Il codice Java è corredato dalla **documentazione** che può essere generata in
locale come illustrato di seguito, o [acceduta
direttamente](https://prog2-unimi.github.io/handouts/).

La directory `tests` contiene i file necessari all'esecuzione dei **test
black-box** realizzati secondo le modalità previste dalla libreria
[Jubbiot](https://github.com/prog2-unimi/jubbiot); i test possono essere
eseguiti in locale (tramite il *build automation tool*) come illustrato di
seguito. 

> **NOTA BENE**: il *superamento dell'esame* è subordinato alla **corretta
> esecuzione di tutti i test** associati al progetto, è pertanto *fortemente
> consigliato* che lo studente familiarizzi da subito con il meccanismo di
> testing.

## Come ottenere ed utilizzare questo materiale sul proprio computer

Può scaricare un [archivio
zip](https://github.com/prog2-unimi/handouts/archive/master.zip) del contenuto
di questo repository usando il link in questa frase, oppure il bottone verde
"Clone or download" in altro a destra nella pagina dove sta leggendo questo
`README.md`.

Al fine di consentire l'automazione di alcuni compiti, tra i quali la
**compilazione**, l'**esecuzione dei test** *black-box*  la **generazione della
documentazione**, questo materiale fa uso di un *build automation tool*
denominato [Gradle](https://gradle.org/) unitamente al *testing framework*
[Jubbiot](https://github.com/prog2-unimi/jubbiot) basato su
[JUnit](https://junit.org/junit5/). 

Una *conoscenza approfondita del funzionamento di tali strumenti non è affatto
necessaria per lo svolgimento degli esercizi, o per il superamento dell'esame*,
perché sono completamente predisposti e configurati dal docente, come illustrato
nelle sezioni seguenti.

L'unica cosa che è necessario fare è **installare il *Java Developer Kit*
(JDK)** in una versione sufficientemente recente (la configurazione provvederà
poi ad installre automaticamente sia la versione 21 del JDK che Gradle e
Jubbiot/JUnit).

### Come compilare ed eseguire i test e il codice

Una volta ottenuta una copia locale può procedere a **compilare** il codice con
il comando:

    ./gradlew build

se usa una ragionevole versione di GNU/Linux, oppure se usa Windows (qui e di
seguito) può sostituire `./gradlew` con `gradlew.bat`; questo comando provvederà
anche ad eseguire tutti i **test** specificati nella directory `tests`.

Può eseguire il codice di una specifica classe, ad esempio
`it.unimi.di.prog2.h02.SalveMondo` con il comando

    ./gradlew runClass -PmainClass=it.unimi.di.prog2.h02.SalveMondo

Per maggiori informazioni sul **funzionamento dei test** consulti l'[esempio d'uso di
Jubbiot](https://github.com/prog2-unimi/jubbiot/blob/master/README.md#example);
in particolare presti attenzione alla sezione sulla [generazione degli output
dello studente](https://github.com/prog2-unimi/jubbiot/blob/master/README.md#generating-actual-outputs).

### Come generare la documentazione

Può generare la documentazione in locale con il comando:

    ./gradlew javadoc

tale comando è configurato per riportare un errore in caso di *warning*, al fine
di aiutarla nel comprendere se la documentazione è, almeno dal punto di vista
sintattico, completa.

È possibile accedere direttamente ad una copia già compilata della
[documentazione del codice in questo repository](https://prog2-unimi.github.io/handouts/).

### Approcci alternativi

Chi non intendesse usare il *build automation tool* può comunque compilare ed
eseguire il codice e i test, nonché generare la documentazione, usando la linea
di comando, oppure un IDE a sua scelta.  

> **NOTA BENE**: *nel caso del progetto* non sarà valutato alcun codice che
> presenti *errori* (o *warning*) di compilazione (sia nella parte di *Java* che
> di *Javadoc*).
>
> Per questa ragione si consiglia, qualora si decida di usare gli usuali comandi
> del JDK, di aggiungere sempre le opzioni `-Xlint:all -Werror` al comando
> `javac` e `-Xdoclint:all -Werror` al comando `javadoc` (sia da riga di comando
> che attraverso l'IDE scelto).

È del tutto evidente che **il docente non fornirà alcun supporto per l'uso di
approcci differenti** da quello basato sul *build automation tool*. suggerito e
preconfigurato.

## Il materiale degli scorsi anni accademici

Gli studenti che hanno frequentato nei precedenti anno accademici possono
trovare il materiale nel

* branch dell'[AA 2019/20](../../tree/aa1920),
* branch dell'[AA 2020/21](../../tree/aa2021),
* branch dell'[AA 2021/22](../../tree/aa2122),
* branch dell'[AA 2022/23](../../tree/aa2223),
* branch dell'[AA 2023/24](../../tree/aa2324).

## Un prompt per la simulazione dell'esame orale (basata su AI)

In modo del tutto **sperimentale**, gli studenti possono interagire con un
sistema di AI, come ad esempio [ChatGPT](https://chatgpt.com/) o
[Claude](https://claude.ai/), per svolgere una simulazione dell'esame orale; a
tale fine, dopo aver acceduto al sistema di AI, possono incollare il
[prompt](ai-prompt.md) predisposto e procedere a rispondere alle domande che il
modello genererà.

La valutazione delle risposte fornite dall'AI è **esclusivamente indicativa** e
non è affatto garantito che rispecchi la valutazione finale dell'esame; può ciò
nonostante essere un accettabile punto di partenza per valutare la propria
preparazione e la propria capacita di comunicare in modo chiaro e completo.