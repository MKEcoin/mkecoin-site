{% include disclaimer.html translated="yes" translationOutdated="no" %}

Случается так, что ваши средства «застревают», то есть у вас появляются заблокированные средства, которые никогда не будут разблокированы. И вот способ решения этой проблемы.

- Загрузить ваш кошелёк в MKEcoin-wallet-cli.

- Напечатать

> seed

в окне ввода команды. Ввести свою мнемоническую фразу, состоящую из 25 слов, если этого ещё не было сделано. Это наилучший способ убедиться в том, что вы не утратите доступа к собственным средствам.

- Закрыть MKEcoin-wallet-cli, напечатав

> exit

- Сохранить все файлы, связанные с вашим кошельком, включая

> yourwalletname.bin
> yourwalletname.bin.keys
> yourwalletname.bin.address.txt

Это можно сделать, скопировав все файлы в новую папку.

Иногда при создании кошелька вы можете назвать его как-нибудь так, что часть .bin будет отсутствовать. В этом случае файл кошелька должен называться yourwalletname без .bin на конце.

- Следует удалить yourwallet.bin.

- Загрузить MKEcoin-wallet-cli, ввести имя кошелька, которое вы только что удалили.

- Ввести пароль. Теперь кошелёк обновлен, а ваши заблокированные средства, я надеюсь, разблокированы.