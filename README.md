<h2><span style="text-decoration: underline;"><strong>➕ Somma di entità in Home Assistant</strong></span></h2>

Volevo condividere una scheda che ho creato, grazie a varie guide di esperti trovate online, per gestire il mio TV Samsung Q70 55”.

Istruzioni:

da Hacs, installare:

1. bubble-card
2. vertical-stack
3. button-card

poi...
1. in HA creare l'etichetta: Luci, prese, presenza ecc. (i miei hanno questi nomi in italiano) se li cambiate, nel file sensor dovrete poi cambiarli.
2. nel file HA sensor.yaml, inserire il contenuto di sensor.txt, se non si dispone del file sensor.yaml è necessario creare sensor.yaml nella cartella config/, aprire il file configuration.yaml e inserire questa riga: sensor: !include sensor.yaml
3. creare un nuovo badge in HA (vedi immagine sotto: quadrato verde) e selezionare le entità: sensor.luci_accese (per sommare le luci accese) o prese_accese (per sommare l'accensione) o presenze o altro.

Se osserviamo il codice, possiamo capirlo meglio:
1. “stati.luce” = recupera gli stati delle entità nel dominio luce.
2. “selectattr('state', 'eq', 'on')” = filtra le entità in cui lo stato è uguale a on.
3. “selectattr('entity_id','in',label_entities('Luci'))” = filtra le entità con l'etichetta luce.
4. “list | count” = costruisce un elenco e conta gli elementi. (solo list darebbe l'elenco scritto di tutti gli elementi)

Con il codice scritto nel file sensor.yaml avremo un'entità chiamata lights_on in cui il conteggio di tutte le entità luminose nello stato on (come nell'immagine sotto nel rettangolo giallo) sarà riportato nello stato.
Questo approccio ha il notevole vantaggio di essere completamente dinamico: ogni nuova entità che entra nel dominio della luce e che viene etichettata come luce verrà presa in considerazione senza fare nulla.

Ok, ora che abbiamo capito (vedi immagine sotto, quadrato giallo):

<p><img src="example/sum_entities.jpg" alt="" /></p>

Ora per poter vedere quali luci sono accese dobbiamo fare così:

https://github.com/user-attachments/assets/732f33bd-28df-49fd-9899-c3f87ad6aefe

Seconda parte per avere un popup che mostra quali delle nostre entità sono accese:

1. creare una nuova card in fondo alla vista (nella stessa vista dove abbiamo i badge), incolliamo il codice del file popup_card.txt e andiamo a modificare le entità in base alle vostre, nel mio codice ne ho inserite 2 come esempio, il codice della prima entità va dalla riga 23 alla riga 57, in questa sezione andate a sostituire light.bagno con la vostra entità luce, in ogni blocco l'entità è ripetuta 2 volte (es. riga 24 e 56) e così via per le altre entità
2. se avete più luci da sommare copiate il blocco da 23 a 57 in coda e modificate le entità

Risultato finale:

<p><img src="example/popup.gif" alt="" /></p>

<p>Enjoy!</p>


----------------------------------------
<p>Would you like to give me a hand?<br />The content of this page is completely free of charge and the purpose is certainly not to make money.<br />If you would like to lend me a hand to help with expenses and lost time, you have the following ways:</p>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/C0C713VTGJ)

[![PayPal](https://github.com/Simonz82/desktop-tutorial/blob/main/paypal.svg)](https://www.paypal.com/paypalme/simongmail)

Make your Amazon purchases from this link:

[![Amazon](https://github.com/Simonz82/desktop-tutorial/blob/main/Amazon_logo.jpg)](https://amzn.to/3XWWTgz)

Join our Telegram channel dedicated to Home Assistant news:

[![Home_Assistant_News](https://github.com/Simonz82/desktop-tutorial/blob/main/home_assistant_news.jpg)](https://t.me/Home_Assistant_News)

Join our Telegram channel dedicated to home automation products, there are lots of offers:

[![Offerte Domotica](https://github.com/Simonz82/desktop-tutorial/blob/main/offerte_domotica.jpg)](https://t.me/offerte_domotica_ita)

