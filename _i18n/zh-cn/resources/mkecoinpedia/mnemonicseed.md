---
terms: ["mnemonic-seed", "mnemonic"]
summary: "a 13 or 25 word phrase used to backup a MKEcoin account, available in a number of languages"
---

{% include disclaimer.html translated="yes" translationOutdated="no" %}
### 基础知识

一个13或25个单词的词组，用于备份门罗币帐户，有多个语种可用。这个25个单词组成的词组（MyMKEcoin钱包用的是13个单词组成的词组，与大部分其它钱包不通用）是你需要的所有信息，用来查看和使用罗币@帐户的资金```


### 深度信息

在官方钱包中，助记种子由25个单词组成，最后一个单词用作校验和。这些单词对应一个256位整数，即帐户的*私有* @支付密钥。

*私有* @查看密钥是通过用Keccak-256散列私有支付密钥得到的，生成第二个256位整数。然后，从私有密钥派生出相应的*公开*密钥。

通过将25个单词的助记词存储在一个安全的位置，您可以备份您的私钥，从而备份您所有的门罗币。分享这25个单词的密钥相当于允许其他人完全使用您的资金。  

不要把太多（超过你所能承受的损失的数量）的币存在一个热钱包里面，热钱包指的是现在或曾经被联网的钱包，或在任何曾经或将来会联网的设备上加载的钱包，或在不可信来源上载入的钱包。

通过创建一个冷钱包，或@纸钱包，来安全地存储门罗币。