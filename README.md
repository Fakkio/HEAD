# HEAD

Un elenco di tutto ciò che potrebbe esseci nel `<head>` del tuo documento

## Indice

- [Minimo consigliato](#minimo-consigliato)
- [Elementi](#elementi)
- [Meta](#meta)
  - [Meta: Non raccomandato](#meta-non-raccomandato)
- [Link](#link)
  - [Link: Non raccomandato](#link-non-raccomandato)
  - [Favicon](#favicon)
- [Social](#social)
  - [Facebook / Open Graph](#facebook--open-graph)
  - [Facebook / Articoli interattivi](#facebook--articoli-interattivi)
  - [Twitter](#twitter)
  - [Google+ / Schema.org](#google--schemaorg)
  - [OEmbed](#oembed)
- [Browser / Piattaforme](#browser--piattaforme)
  - [Apple iOS](#apple-ios)
  - [Apple Safari](#apple-safari)
  - [Google Android](#google-android)
  - [Google Chrome](#google-chrome)
  - [Microsoft Internet Explorer](#microsoft-internet-explorer)
  - [Microsoft Internet Explorer: Legacy, non usare!](#microsoft-internet-explorer-legacy-non-usare)
- [Browser (Cinesi)](#browser-cinesi)
  - [360 Browser](#360-browser)
  - [QQ Browser mobile](#qq-browser-mobile)
  - [UC Browser mobile](#uc-browser-mobile)
- [Link app](#link-app)
- [Note](#note)
  - [Performance](#performance)
- [Altre risorse](#altre-risorse)
- [Progetti correlati](#progetti-correlati)
- [Altri formati](#altri-formati)
- [Traduzioni](#traduzioni)
- [Contribuire](#contribuire)
- [Autore](#autore)
- [Traduzione](#traduzione)
- [Licenza](#licenza)

## Minimo consigliato

Qui sotto sono riportati i tag essenziali per un sito base, minimalista:

```html
<meta charset="utf-8">
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!-- I tre meta tag qui sopra *devono* essere i primi nel head; tutti gli altri contenuti del head devono venire *dopo* questi tag -->
<title>Titolo della pagina</title>
```

## Elementi

``` html
<!-- Titolo del documento -->
<title>Titolo della pagina</title>

<!-- URL base da usare per tutti gli URL relativi contenuti nel documento -->
<base href="https://example.com/page.html">

<!-- CSS esterni -->
<link rel="stylesheet" href="styles.css">

<!-- CSS nel documento -->
<style>
  /* ... */
</style>

<!-- JavaScript -->
<script src="script.js"></script>
<noscript><!-- Codice alternativo no JS --></noscript>
```

## Meta

``` html
<meta charset="utf-8"> <!-- set di codifica dei caratteri per il documento -->
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
<!-- I tre meta tag qui sopra *devono* essere i primi nel head; tutti gli altri contenuti del head devono venire *dopo* questi tag -->

<!-- Permette di controllare da dove vengono caricate le risorse -->
<meta http-equiv="Content-Security-Policy" content="default-src 'self'">
<!-- Inserirlo nel documento il prima possibile -->
<!-- Si applica solamente ai contenuti sotto questo tag -->

<!-- Nome della web application (dovrebbe essere usato solo nel caso il sito sia usato come un'app) -->
<meta name="application-name" content="Nome dell'applicazione">

<!-- Breve descrizione della pagina (Massimo 150 caratteri) -->
<!-- In *alcune* situazioni questa descrizione è usata come parte dello snippet mostrato nei risultati di ricerca. -->
<meta name="description" content="Descrizione della pagina">

<!-- Controlla il comportamento di scansione e indicizzazione dei motori di ricerca -->
<meta name="robots" content="index,follow,noodp"><!-- Tutti i motori di ricerca -->
<meta name="googlebot" content="index,follow"><!-- Specifico per Google -->

<!-- Dice a Google di non mostrare i sitelink nei risultati di ricerca -->
<meta name="google" content="nositelinkssearchbox">

<!-- Dice a Google di non fornire una traduzione per questa pagina -->
<meta name="google" content="notranslate">

<!-- Verifica del possesso per la Google Search Console -->
<meta name="google-site-verification" content="token_di_verifica">

<!-- Usato per indicare il nome del programma utilizzato per costruire il sito web (cioè - WordPress, Dreamweaver) -->
<meta name="generator" content="programma">

<!-- Breve descrizione dell'argomento del tuo sito -->
<meta name="subject" content="argomento del tuo sito">

<!-- Brevissima (10 parole o meno) descrizione. Principalmente per articoli accademici -->
<meta name="abstract" content="">

<!-- Nome completo del dominio o dell'indirizzo web -->
<meta name="url" content="https://example.com/">

<meta name="directory" content="submission">

<!-- Dà un limite generale di età basata sui contenuti del sito -->
<meta name="rating" content="General">

<!-- Permette il controllo di come sono passate le informazioni del referrer -->
<meta name="referrer" content="never">

<!-- Disattiva il rilevamento automatico e la formattazione dei possibili numeri di telefono -->
<meta name="format-detection" content="telephone=no">

<!-- Disattiva completamente il prefetching DNS impostando questo tag su 'off' -->
<meta http-equiv="x-dns-prefetch-control" content="off">

<!-- Salva un cookie sul browser per l'identificazione del client -->
<meta http-equiv="set-cookie" content="name=value; expires=date; path=url">

<!-- Indica alla pagina di caricarsi in un frame specifico -->
<meta http-equiv="Window-Target" content="_valore">

<!-- Tag geo -->
<meta name="ICBM" content="latitudine, longitudine">
<meta name="geo.position" content="latitudine;longitudine">
<meta name="geo.region" content="nazione[-stato|zona]"><!-- Codice nazione (ISO 3166-1): obbligatorio, il codice dello stato (ISO 3166-2): opzionale; es. content="IT" / content="IT-MI" -->
<meta name="geo.placename" content="città"><!-- es. content="Milano" -->
```

- [Meta tag riconosciuti da Google](https://support.google.com/webmasters/answer/79812?hl=it)
- [WHATWG Wiki: MetaExtensions (inglese)](https://wiki.whatwg.org/wiki/MetaExtensions)
- [ICBM su Wikipedia (inglese)](https://en.wikipedia.org/wiki/ICBM_address#Modern_use)
- [Geotagging su Wikipedia (inglese)](https://en.wikipedia.org/wiki/Geotagging#HTML_pages)

### Meta: Non raccomandato
Di seguito sono elencati gli attributi *meta* che non sono raccomandati per l'uso a causa del fatto che hanno un basso tasso di adozione, o sono stati deprecati:

```html
<!-- Usato per indicare la lingua del documento, ma non ben supportato. Meglio usare <html lang="it"> -->
<meta name="language" content="it">

<!-- Google lo ignora e Bing lo considera come indicatore di spam -->
<meta name="keywords" content="metti,qui,le,tue,keywords,separate,da,virgola,senza,spazi">
<!-- Nessuna prova di utilizzo recente in nessun morore di ricerca -->
<meta name="revised" content="Sunday, July 18th, 2010, 5:15 pm">

<!-- Fornisce un modo semplice agli *spam bot* per la raccolta di indirizzi e-mail -->
<meta name="reply-to" content="email@example.com">

<!-- Meglio usare <link rel="author"> o il file humans.txt -->
<meta name="author" content="name, email@example.com">
<meta name="designer" content="">
<meta name="owner" content="">

<!-- Dice ai motori di ricerca di rivisitare la pagina dopo uno specifico periodo di tempo. Non è supportato poiché la maggior parte dei motori di ricerca usano intervalli casuali per scansionare nuovamente la pagina -->
<meta name="revisit-after" content="7 days">

<!-- Manda l'utente ad una nuova URL dopo un dato periodo di tempo -->
<!-- Il W3C consiglia di non usare questo tag. Google consiglia di usare un redirect 301 lato server al suo posto. -->
<meta http-equiv="refresh" content="300; url=https://example.com/">

<!-- Descrive l'argomento del sito -->
<meta name="topic" content="">

<!-- Breve sommario dell'azienda o lo scopo del sito -->
<meta name="summary" content="">

<!-- Un tag deprecato che fa la stessa cosa del meta tag keywords -->
<meta name="classification" content="business">

<!-- Fa la stessa cosa di URL, più vechio e non supportato -->
<meta name="identifier-URL" content="https://example.com/">

<!-- Funzione simile al tag keyword -->
<meta name="category" content="">

<!-- Si assicura che il tuo sito sia visibile in tutte le nazioni e in tutte le lingue -->
<meta name="coverage" content="Worldwide">

<!-- Uguale al tag coverage -->
<meta name="distribution" content="Global">

<!-- COntrolla a cosa può accedere l'utente via internet -->
<meta http-equiv="Pics-label" content="value">

<!-- Controllo della cache -->
<!-- Meglio configurare il controllo della cache lato server -->
<meta http-equiv="Expires" content="0">
<meta http-equiv="Pragma" content="no-cache">
<meta http-equiv="Cache-Control" content="no-cache">
```

## Link

``` html
<!-- Aiuta a evitare i problemi dovuti ai contenuti duplicati -->
<link rel="canonical" href="https://example.com/2010/06/9-things-to-do-before-entering-social-media.html">

<!-- Era usato prima del link icon, ma è deprecato e non più usato -->
<link rel="shortlink" href="https://example.com/?p=42">

<!-- Link alla versione AMP HTML del documento corrente -->
<link rel="amphtml" href="https://example.com/path/to/amp-version.html">

<!-- Punta ad un foglio di stile CSS -->
<link rel="stylesheet" href="https://example.com/styles.css">

<!-- Collegamento ad un file JSON che specifica le credenziali di "installazione" per l'applicazione web -->
<link rel="manifest" href="manifest.json">

<!-- Link all'autore del documento -->
<link rel="author" href="humans.txt">

<!-- Fa riferimento a una dichiarazione di copyright applicata al contesto del link -->
<link rel="copyright" href="copyright.html">

<!-- Fa riferimento ad una posizione nel documento che potrebbe essere in un altra lingua -->
<link rel="alternate" href="https://es.example.com/" hreflang="es">

<!-- Fornisce informazioni su un autore o un altra persona -->
<link rel="me" href="https://google.com/profiles/thenextweb" type="text/html">
<link rel="me" href="mailto:name@example.com">
<link rel="me" href="sms:+15035550125">

<!-- Collegamento ad un documento che contiene un archivio di link al documento corrente -->
<link rel="archives" href="https://example.com/2003/05/" title="May 2003">

<!-- Collegamento alla risorsa di livello più alto nella struttura gerarchica -->
<link rel="index" href="https://example.com/" title="DeWitt Clinton">

<!-- Fornisce il punto di partenza del documento -->
<link rel="start" href="https://example.com/photos/pattern_recognition_1_about/" title="Pattern Recognition 1">

<!-- Conduce alla risorsa precedente della sequenza nella quale è inserito il documento corrente -->
<link rel="prev" href="https://example.com/opensearch/opensearch-and-openid-a-sure-way-to-get-my-attention/" title="OpenSearch and OpenID? A sure way to get my attention.">

<!-- Dà un riferimento al documento stesso - utile quando il documento ha più di un possibile riferimento -->
<link rel="self" type="application/atom+xml" href="https://example.com/atomFeed.php?page=3">

<!-- Rispettivamente il primo (first), il prossimo (next), il precedente (previous) e l'ultimo (last) documento in una serie. -->
<link rel="first" href="https://example.com/atomFeed.php">
<link rel="next" href="https://example.com/atomFeed.php?page=4">
<link rel="previous" href="https://example.com/atomFeed.php?page=2">
<link rel="last" href="https://example.com/atomFeed.php?page=147">

<!-- Usato quando si usufruisce di un servizio di terze parti per mantenere un blog -->
<link rel="EditURI" href="https://example.com/xmlrpc.php?rsd" type="application/rsd+xml" title="RSD">

<!-- Crea un commento automatico quando un altro blog WordPress inserisce un link al tuo blog o ad un tuo post -->
<link rel="pingback" href="https://example.com/xmlrpc.php">

<!-- Notifica un URL quando fai riferimento a quella risorsa sul tuo sito -->
<link rel="webmention" href="https://example.com/webmention">

<!-- Carica un file HTML esterno nel documento HTML corrente. -->
<link rel="import" href="component.html">

<!-- Open Search -->
<link rel="search" href="/open-search.xml" type="application/opensearchdescription+xml" title="Search Title">

<!-- Feed -->
<link rel="alternate" href="https://feeds.feedburner.com/example" type="application/rss+xml" title="RSS">
<link rel="alternate" href="https://example.com/feed.atom" type="application/atom+xml" title="Atom 0.3">

<!-- Prefetching, precaricamento, prebrowsing -->
<link rel="dns-prefetch" href="//example.com/">
<link rel="preconnect" href="https://www.example.com/">
<link rel="prefetch" href="https://www.example.com/">
<link rel="prerender" href="https://example.com/">
<link rel="preload" href="image.png" as="image">
<!-- Maggiori informazioni (inglese): https://css-tricks.com/prefetching-preloading-prebrowsing/ -->
```

### Link: Non raccomandato
Qui di seguito ci sono i tag *link* dei quali non è raccomandato l'uso:

```html
<link rel="shortcut icon" href="path/to/favicon.ico">

<!-- Nessuna utilità, proprietario e pieno di errori, vedi (inglese): https://groups.google.com/a/chromium.org/forum/#!msg/blink-dev/Y_2eFRh9BOs/gULYapoRBwAJ -->
<link rel="subresource" href="styles.css">
```

### Favicon

``` html
<!-- Per IE 10 e precedenti -->
<!-- Nessun link, carica semplicemente un file chiamato favicon.ico nella directory principale del sito -->

<!-- Per IE 11, Chrome, Firefox, Safari, Opera -->
<link rel="icon" href="path/to/favicon-16.png" sizes="16x16" type="image/png">
<link rel="icon" href="path/to/favicon-32.png" sizes="32x32" type="image/png">
<link rel="icon" href="path/to/favicon-48.png" sizes="48x48" type="image/png">
<link rel="icon" href="path/to/favicon-62.png" sizes="62x62" type="image/png">
<link rel="icon" href="path/to/favicon-192.png" sizes="192x192" type="image/png">
<!-- Maggiori informazioni (inglese): https://bitsofco.de/all-about-favicons-and-touch-icons/ -->
```

- [Tutto sulle favicon (e touch icon) (inglese)](https://bitsofco.de/all-about-favicons-and-touch-icons/)
- [Favicon Cheat Sheet (inglese)](https://github.com/audreyr/favicon-cheat-sheet)

## Social

### Facebook / Open Graph

``` html
<meta property="fb:app_id" content="123456789">
<meta property="og:url" content="https://example.com/page.html">
<meta property="og:type" content="website">
<meta property="og:title" content="Titolo del contenuto">
<meta property="og:image" content="https://example.com/image.jpg">
<meta property="og:description" content="Qui la descrizione">
<meta property="og:site_name" content="Nome del sito">
<meta property="og:locale" content="it_IT">
<meta property="article:author" content="Nome dell'autore">
<!-- Facebook: https://developers.facebook.com/docs/sharing/webmasters#markup -->
<!-- Open Graph (inglese): http://ogp.me/ -->
```

- [Markup Open Graph](https://developers.facebook.com/docs/sharing/webmasters#markup)
- [Protocollo Open Graph (inglese)](http://ogp.me/)

### Facebook / Articoli interattivi

``` html
<meta charset="utf-8">
<meta property="op:markup_version" content="v1.0">

<!-- L'URL della versione web del tuo articolo -->
<link rel="canonical" href="http://example.com/article.html">

<!-- Lo stile da utilizzare per questo articolo -->
<meta property="fb:article_style" content="myarticlestyle">
```

- [Creazione di un articolo interattivo](https://developers.facebook.com/docs/instant-articles/guides/articlecreate)
- [Esempi di codice degli articoli interattivi](https://developers.facebook.com/docs/instant-articles/reference)

### Twitter

``` html
<meta name="twitter:card" content="sommario">
<meta name="twitter:site" content="@account_sito">
<meta name="twitter:creator" content="@account_individuale">
<meta name="twitter:url" content="https://example.com/pagina.html">
<meta name="twitter:title" content="Titolo del contenuto">
<meta name="twitter:description" content="Descrizione del contenuto, meno di 200 caratteri">
<meta name="twitter:image" content="https://example.com/immagine.jpg">
<!-- Maggiori informazioni (inglese): https://dev.twitter.com/cards/getting-started -->
<!-- Validazione (inglese): https://dev.twitter.com/docs/cards/validation/validator -->
```

- [Twitter Cards: Guida introduttiva (inglese)](https://dev.twitter.com/cards/getting-started)
- [Validatore per Twitter Card (inglese)](https://dev.twitter.com/docs/cards/validation/validator)

### Google+ / Schema.org

``` html
<link href="https://plus.google.com/+YourPage" rel="publisher">
<meta itemprop="name" content="Titolo del contenuto">
<meta itemprop="description" content="Descrizione del contenuto, meno di 200 caratteri">
<meta itemprop="image" content="https://example.com/immagine.jpg">
```

### OEmbed

``` html
<link rel="alternate" type="application/json+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=json"
  title="oEmbed Profile: JSON">
<link rel="alternate" type="text/xml+oembed"
  href="http://example.com/services/oembed?url=http%3A%2F%2Fexample.com%2Ffoo%2F&amp;format=xml"
  title="oEmbed Profile: XML">
```

- [Formato oEmbed (inglese)](http://oembed.com/)

## Browser / Piattaforme

### Apple iOS

``` html
<!-- Smart App Banner -->
<meta name="apple-itunes-app" content="app-id=APP_ID,affiliate-data=AFFILIATE_ID,app-argument=SOME_TEXT">

<!-- Disattiva il rilevamento automatico e la formattazione dei possibili numeri di telefono -->
<meta name="format-detection" content="telephone=no">

<!-- Aggiungi alla schermata home -->
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black">
<meta name="apple-mobile-web-app-title" content="App Title">

<!-- Icone Touch -->
<link rel="apple-touch-icon" href="path/to/apple-touch-icon.png">
<link rel="apple-touch-icon-precomposed" href="path/to/apple-touch-icon-precomposed.png">
<!-- iOS 8+ non supporta più le icone precomposed, è richiesta solo la apple-touch-icon -->

<!-- Nella maggior parte dei casi, è sufficiente una icona touch da 180×180px nel head -->
<!-- Utilizzare le diverse dimensioni delle icone solo se si vogliono avere icone diverse -->
<!-- in base al dispositivo. -->
<link rel="apple-touch-icon" sizes="57x57" href="path/to/icon@57.png">
<link rel="apple-touch-icon" sizes="72x72" href="path/to/icon@72.png">
<link rel="apple-touch-icon" sizes="114x114" href="path/to/icon@114.png">
<link rel="apple-touch-icon" sizes="144x144" href="path/to/icon@144.png">

<!-- Immagine Startup (Deprecato) -->
<link rel="apple-touch-startup-image" href="path/to/startup.png">

<!-- iOS app deep linking -->
<meta name="apple-itunes-app" content="app-id=APP-ID, app-argument=http/url-sample.com">
<link rel="alternate" href="ios-app://APP-ID/http/url-sample.com">
```

- [Meta Tag Apple (inglese)](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariHTMLRef/Articles/MetaTags.html)

### Apple Safari

```html
<!-- Siti preferiti -->
<link rel="mask-icon" href="path/to/icon.svg" color="red">
```

### Google Android

``` html
<meta name="theme-color" content="#E64545">

<!-- Aggiugni alla home -->
<meta name="mobile-web-app-capable" content="yes">
<!-- Maggiori informazioni (inglese): https://developer.chrome.com/multidevice/android/installtohomescreen -->

<!-- Android app deep linking -->
<meta name="google-play-app" content="app-id=package-name">
<link rel="alternate" href="android-app://package-name/http/url-sample.com">
```

### Google Chrome

``` html
<link rel="chrome-webstore-item" href="https://chrome.google.com/webstore/detail/APP_ID">

<!-- Disattiva l'avviso di traduzione -->
<meta name="google" value="notranslate">
```
### Google Chrome Mobile (Solo Android)

Da Chrome 31, puoi impostare la tua web app in "app mode" come Safari.

``` html
<!-- Collegamento ad un manifest e definisce i metadata. -->
<!-- Un esempio di manifest.json può essere trovato nel link sottostante. -->
<link rel="manifest" href="manifest.json">

<!-- Imposta la tua pagina come "web app" -->
<meta name="mobile-web-app-capable" content="yes">

<!-- Il primo è il formato ufficiale e raccomandato.  -->
<link rel="icon" sizes="192x192" href="nice-highres.png">
<link rel="icon" sizes="128x128" href="niceicon.png">
<!-- I formati con il prefisso Apple saranno deprecati. -->
<link rel="apple-touch-icon" sizes="128x128" href="niceicon.png">
<link rel="apple-touch-icon-precomposed" sizes="128x128" href="niceicon.png">
```

[Google Developer (inglese)](https://developer.chrome.com/multidevice/android/installtohomescreen)

### Microsoft Internet Explorer

``` html
<meta http-equiv="x-ua-compatible" content="ie=edge">
<meta http-equiv="cleartype" content="on">
<meta name="skype_toolbar" content="skype_toolbar_parser_compatible">

<!-- Disattiva l'evidenziazione dei link in IE 10 su Windows Phone (inglese) (https://blogs.windows.com/buildingapps/2012/11/15/adapting-your-webkit-optimized-site-for-internet-explorer-10/) -->
<meta name="msapplication-tap-highlight" content="no">

<!-- Siti aggiunti (inglese) (https://msdn.microsoft.com/en-us/library/dn255024(v=vs.85).aspx) -->
<meta name="application-name" content="Etichetta del sito aggiunto">
<meta name="msapplication-tooltip" content="Esempio di testo tooltip">
<meta name="msapplication-starturl" content="/">

<meta name="msapplication-config" content="http://example.com/browserconfig.xml">

<meta name="msapplication-allowDomainApiCalls" content="true">
<meta name="msapplication-allowDomainMetaTags" content="true">
<meta name="msapplication-badge" content="frequency=30; polling-uri=http://example.com/id45453245/polling.xml">
<meta name="msapplication-navbutton-color" content="#FF3300">
<meta name="msapplication-notification" content="frequency=60;polling-uri=http://example.com/livetile">
<meta name="msapplication-square150x150logo" content="path/to/logo.png">
<meta name="msapplication-square310x310logo" content="path/to/largelogo.png">
<meta name="msapplication-square70x70logo" content="path/to/tinylogo.png">
<meta name="msapplication-wide310x150logo" content="path/to/widelogo.png">
<meta name="msapplication-task" content="name=Check Order Status;action-uri=./orderStatus.aspx?src=IE9;icon-uri=./favicon.ico">
<meta name="msapplication-task-separator" content="1">
<meta name="msapplication-TileColor" content="#FF3300">
<meta name="msapplication-TileImage" content="path/to/tileimage.jpg">
<meta name="msapplication-window" content="width=1024;height=768">
```

### Microsoft Internet Explorer: Legacy, non usare!

``` html
<!-- Disattiva la toolbar per le immagini al mouseover in IE 6 (inglese) (https://msdn.microsoft.com/en-us/library/ms532986(v=vs.85).aspx) -->
<meta http-equiv="imagetoolbar" content="no">

<!-- Disattiva il tema di windows agli input e bottoni nei form (inglese) (https://support.microsoft.com/en-us/kb/322240) -->
<meta name="MSThemeCompatible" content="no">

<!-- Disattiva una funzione che era presente solo in IE 6 beta (inglese) (https://stackoverflow.com/q/2167301) -->
<meta name="MSSmartTagsPreventParsing" content="true">

<!-- Transizioni tra le pagine (inglese) (https://msdn.microsoft.com/en-us/library/ms532847(v=vs.85).aspx) -->
<meta http-equiv="Page-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Page-Exit" content="revealtrans(duration=3,transition=12)">
<meta http-equiv="Site-Enter" content="revealtrans(duration=2,transition=2)">
<meta http-equiv="Site-Exit" content="revealtrans(duration=3,transition=12)">
```

## Link app

``` html
<!-- iOS -->
<meta property="al:ios:url" content="applinks://docs">
<meta property="al:ios:app_store_id" content="12345">
<meta property="al:ios:app_name" content="App Links">
<!-- Android -->
<meta property="al:android:url" content="applinks://docs">
<meta property="al:android:app_name" content="App Links">
<meta property="al:android:package" content="org.applinks">
<!-- Web Fallback -->
<meta property="al:web:url" content="http://applinks.org/documentation">
<!-- Maggiori informazioni (inglese): http://applinks.org/documentation/ -->
```

- [Documentazione *App Links* (inglese)](http://applinks.org/documentation/)

## Browser (Cinesi)

### 360 Browser

``` html
<!-- Selezione il motore di rendering, in ordine -->
<meta name="renderer" content="webkit|ie-comp|ie-stand">
```

### QQ Browser mobile

``` html
<!-- Blocca lo schermo in un orientamento specifico -->
<meta name="x5-orientation" content="landscape/portrait">
<!-- Visualizza la pagina a schermo intero -->
<meta name="x5-fullscreen" content="true">
<!-- La pagina sarà Visualizzata in "application mode"(fullscreen,ecc.) -->
<meta name="x5-page-mode" content="app">
```

### UC Browser mobile

``` html
<!-- Blocca lo schermo in un orientamento specifico -->
<meta name="screen-orientation" content="landscape/portrait">
<!-- Visualizza la pagina a schermo intero -->
<meta name="full-screen" content="yes">
<!-- Il browser UC visualizzerà le immagini anche se è in "modalità testuale" -->
<meta name="imagemode" content="force">
<!-- La pagina sarà Visualizzata in "application mode"(fullscreen,forbiding gesture, etc.) -->
<meta name="browsermode" content="application">
<!-- Disattiva la "modalità notturna" del browser UC in questa pagina -->
<meta name="nightmode" content="disable">
<!-- Semplifica la pagina per ridurre il trasferimento dati -->
<meta name="layoutmode" content="fitscreen">
<!-- Disattiva la funzione del browser UC che "aumenta la dimensione del testo quando ci sono troppe parole in questa pagina" -->
<meta name="wap-font-scale" content="no">
```

- [Documentazione del browser UC (cinese)](http://www.uc.cn/download/UCBrowser_U3_API.doc)

## Note

### Performance
Spostare l'attributo `href` all'inizio degli elementi aumenta la compressione quando è attiva la compressione GZIP, perchè l'attributo `href` è utilizzato nei tag `a`, `base` e `link`

Esempio:

``` html
<link href="https://fonts.googleapis.com/css?family=Open+Sans:400,700" rel="stylesheet">
```

## Altre risorse

- [Documentazione di HTML5 Boilerplate: l'HTML (inglese)](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/html.md)
- [Documentazione di HTML5 Boilerplate: estensione e personalizzazione (inglese)](https://github.com/h5bp/html5-boilerplate/blob/master/dist/doc/extend.md)

## Progetti correlati

- [Head Snippets per Atom](https://github.com/joshbuchea/atom-html-head-snippets) - Pacchetto Atom per gli snippet per il tag `HEAD`
- [Head Snippets per Sublime Text](https://github.com/marcobiedermann/sublime-head-snippets) - Pacchetto Sublime Text per gli snippet per il tag `HEAD`
- [head-it](https://github.com/hemanth/head-it) - Interfaccia CLI per gli snippet per il tag `HEAD`
- [vue-head](https://github.com/ktquez/vue-head) - Manipola le meta informazioni del tag `HEAD` per Vue.js

## Altri formati

- [PDF (inglese)](https://gitprint.com/joshbuchea/HEAD/blob/master/README.md)

## Traduzioni

- [Cinese (Semplificato)](https://github.com/Amery2010/HEAD)
- [Giapponese](http://coliss.com/articles/build-websites/operation/work/collection-of-html-head-elements.html)
- [Italiano](https://github.com/Fakkio/HEAD)
- [Portoghese Brasiliano](https://github.com/Webschool-io/HEAD)
- [Russo/Русский](https://github.com/Konfuze/HEAD)

## Contribuire

Apri un *issue* o fai una *pull request* per suggerire modifiche o aggiunte.

Per favore, segui questi passi per una *pull request*:

- Modifica solo un tag o un insieme di tag collegati alla volta
- Usa gli apici doppi per gli attributi
- Non inserire lo slash finale negli elementi *self-closing* — le specifiche HTML5 dicono che è opzionale
- Considera di inserire un link alla documentazine che supporti le tue modifiche

### Contributori

Dà un'occhiata al magnifico [Contributori](https://github.com/joshbuchea/HEAD/graphs/contributors).

## Autore

**[Josh Buchea](http://joshbuchea.com/)**

## Traduzione

**[Fakkio](http://jeflab.it)**

## Licenza

[CC0 Licenza](LICENSE)

![CC0](http://i.creativecommons.org/p/zero/1.0/88x31.png "CC0")
