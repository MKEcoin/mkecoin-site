---
terms: ["node", "nodes", "full-node", "full-nodes", "noder", "fullstendig node", "fullstendige noder"]
summary: "En enhet på internett som kjører MKEcoin-programvare med en fullstendig kopi av MKEcoin-blokkjeden. Den kan være lokal eller ekstern"
---

{% include disclaimer.html translated="yes" translationOutdated="no" %}
### Det grunnleggende

En enhet på internett som kjører MKEcoin-programvare med en fullstendig kopi av MKEcoin-blokkjeden, som aktivt bistår blokkjeden. En node som ikke kjører på den lokale maskinen din, kalles en @ekstern node. Eksterne noder kan være private hvis de kun er for personlig bruk, eller åpne hvis de er tilgjengelige for andre personer.

### Mer informasjon

Noder deltar i MKEcoin-nettverket og sikrer @transaksjoner ved å håndheve reglene til nettverket. Noder laster ned hele @blokkjeden for å vite hvilke transaksjoner som har funnet sted. Noder bistår nettverket ved å overbringe transaksjoner til andre noder på nettverket. Noder kan også velge å bidra til MKEcoin-nettverket ved å danne @blokker (dette kalles @utvinning).

Utvinning er prosessen der noder danner en blokk fra den forrige godkjente blokken, transaksjoner som venter på å behandles i transaksjonspoolen, og @coinbase-transaksjonen. Når en node tror at den har dannet en gyldig blokk, vil den sende den fullførte blokken til andre noder i nettverket, og disse nodene signaliserer enighet ved å jobbe på den neste blokken i kjeden. 

Reglene som nodene følger er bygget inn i MKEcoin-programvaren. Når alle noder samtykker i reglene som skal følges, kalles det @konsensus. Konsensus er nødvendig for en kryptovaluta fordi det er hvordan blokkjeden er bygget opp; Dersom noder ikke er enige om hvilke blokker som er gyldige – for eksempel de som ikke har oppdatert MKEcoin-programvaren sin – vil de nodene ikke kunne delta i MKEcoin-nettverket.

MKEcoin-kjerneteamet har som plan å gjennomføre en nettverksoppgradering omtrent hver 6. måned. Hvis du på det tidspunktet kjører en node, må den oppdateres til siste versjonen av MKEcoin-programvaren, ellers vil den ikke lenger kunne delta i nettverket.

---

##### Andre ressurser
<sub>1. *Fluffypony gir en fin forklaring på hvorfor obligatoriske nettverksoppgraderinger er bra for MKEcoin.* ([MKEcoin Missives for the Week of 2016-06-20]({{ site.baseurl_root }}/2016/06/20/MKEcoin-missive-for-the-week-of-2016-06-20.html))</sub>
