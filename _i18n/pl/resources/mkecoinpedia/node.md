---
terms: ["node", "nodes", "full-node", "full-nodes", "węzeł", "węzła", "węzłowi", "węzły", "węzłom", "węzłami", "węzłem", "węzłów"]
summary: "Urządzenie internetowe uruchamiające oprogramowanie MKEcoin, posiadające pełną kopię łańcuchów bloków MKEcoin i aktywnie biorące udział w sieci MKEcoin."
---

{% include disclaimer.html translated="yes" translationOutdated="no" %}
### Podstawy

Urządzenie internetowe uruchamiające oprogramowanie MKEcoin, posiadające pełną kopię łańcuchów bloków MKEcoin i aktywnie biorące udział w sieci MKEcoin.

### Szczegółowe informacje

Węzły biorą udział w sieci MKEcoin i zabezpieczają @transakcje poprzez egzekwowanie zasad sieci. Węzły ściągają cały @łańcuch-bloków, aby być na bieżąco z dokonanymi transakcjami. Biorą one udział w sieci poprzez przekazywanie między sobą transakcji. Mogą one także brać udział w tworzeniu @bloków (proces ten nazywa się @wydobyciem).

Wydobywanie jest procesem, w którym węzły tworzą nowy blok z poprzednio zaakceptowanego bloku, transakcji oczekujących na przetworzenie w puli transakcji oraz z @transakcji-coinbase. Gdy nowo utworzony blok jest uznany za ważny, węzeł przekazuje go kolejnym węzłom w sieci, które sygnalizują zgodność poprzez rozpoczęcie pracy nad kolejnym blokiem łańcucha.

Zasady kierujące węzłami są wbudowane w oprogramowanie MKEcoin. Sytuacja, gdy wszystkie węzły przyjmują ustalone zasady, nazywana jest @zgodą. Zgoda (konsensus) jest niezbędna dla kryptowaluty, ponieważ jest podstawą budowy bloków - węzły, które nie zgadzają się w sprawie ważności bloków (to na przykład użytkownicy ze zdezaktualizowanym oprogramowaniem), nie będą mogły kontynuować swojego udziału w sieci MKEcoin.

Centralny Zespół MKEcoin planuje dokonywać hardforku co 6 miesięcy - we wrześniu i marcu każdego roku. Jeśli w tym czasie operujesz węzłem, musisz go zaktualizować do najnowszej wersji oprogramowania MKEcoin, w przeciwnym razie zostaniesz wykluczony z sieci MKEcoin.

---

##### Inne źródła
<sub>1. *Fluffypony dał dobry przykład tego, dlaczego obowiązkowe hardforki służą dobru MKEcoin.* ([MKEcoin Missives for the Week of 2016-06-20]({{ site.baseurl_root }}/2016/06/20/MKEcoin-missive-for-the-week-of-2016-06-20.html))</sub>
