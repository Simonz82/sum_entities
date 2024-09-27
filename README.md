<div class="markdown-heading" dir="auto">
<h2 class="heading-element" dir="auto" tabindex="-1"><span class="x19la9d6 x1fc57z9 x6ikm8r x10wlt62 x19co3pv x1g5zs5t xfibh0p xiy17q3 x1xsqp64 x1lkfr7t xexx8yu x4uap5 x18d9i69 xkhd6sd"><span class="xrtxmta x1bhl96m">➕ </span></span>Sum of Entities for home assistant</h2>
<a id="user-content--samsung-remote-control-for-home-assistant" class="anchor" href="https://github.com/Simonz82/ha_tv_samsung#-samsung-remote-control-for-home-assistant" aria-label="Permalink: 📺 Samsung Remote Control for home assistant"></a></div>
<p dir="auto">I wanted to share a board I created, thanks to various expert guides found online, to manage my Samsung Q70 55&rsquo; TV</p>
<p dir="auto">Instructions:</p>
<ol dir="auto">
<li>in HA create the label: Luci, prese, presenza ecc. (mine have these names in Italian) if you change them, in the sensor file where you then adapt them</li>
<li>from Hacs, install:<br />a. bubble-card</li>
<li>in the HA file sensor.yaml, insert the contents of sensor.txt (READ the first line), if you do not have the file:<br />a. you must create sensor.yaml in the config/ folder<br />b. open the file configuration.yaml and insert this line: sensor: !include sensor.yaml</li>
<li>create a new badge in HA (see image below, green square) and select entities: sensor.luci_accese (to sum up the lights on) or prese_accese (to sum up the switch on) or presences</li>
</ol>
<p>ok! now we got that (see image below, Yellow square):</p>
<p><img src="example/sum_entities.jpg" alt="Sum_entities" /></p>
<p><img src="example/sum_entities.mp4" alt="sum_entities" /></p>
<p>Now to be able to see which lights are on we have to do this:</p>
<ol dir="auto">
<li>a</li>
<li>b</li>
<li>c</li>
</ol>
----------------------------------------
<p>Would you like to give me a hand?<br />The content of this page is completely free of charge and the purpose is certainly not to make money.<br />If you would like to lend me a hand to help with expenses and lost time, you have the following ways:</p>

[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/C0C713VTGJ)

[![PayPal](https://github.com/Simonz82/desktop-tutorial/blob/main/paypal.svg)](https://www.paypal.com/paypalme/simongmail)

<p>Make your Amazon purchases from <a href="https://amzn.to/3XWWTgz" target="_blank">THIS LINK</a><br /><br />Join our Telegram channel dedicated to Home Assistant news:<br /><a title="Home Assistant News" href="https://t.me/Home_Assistant_News" target="_blank">Home Assistant News</a><br /><br />Join our Telegram channel dedicated to home automation products, there are lots of offers:<br /><a title="offerte_domotica" href="https://t.me/offerte_domotica_ita" target="_blank">Offerte_domotica</a></p>
