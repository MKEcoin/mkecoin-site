{% include disclaimer.html translated="yes" translationOutdated="no" %}

# MKEcoind

`MKEcoind` هو برنامج خادم مونيرو. وهو برنامج وحده تحكم في سلسله الكتل. بينما تُدير محفظه البيتكوين كلاً من الحساب وسلسله الكتل, يقوم مونيرو بفصلهم, فالخادم `MKEcoind` يتحكم في سلسله الكتل وواجهه سطر الأوامر `MKEcoin-wallet-cli` تتحكم في الحساب.

يفترض هذا الدليل أنك قمت بإنشاء الخادم الإفتراضي (VPS) الخاص بك بالفعل وتستخدم (SSH) للإتصال بوحده تحكم الخادم.

## Linux, 64-bit (Ubuntu 16.04 LTS)

### تأكد من أن المنفذ 18080 مفتوح

يستخدم هذا لمنفذ للتواصل مع الخوادم الأخري بشبكه مونيرو.

Example if using `ufw`: `sudo ufw allow 18080`
Example if using `iptables`: `sudo iptables -A INPUT -p tcp --dport 18080 -j ACCEPT`

### قم بتحميل ملفات تسطيب مونيرو.

    wget https://downloads.getMKEcoin.org/linux64

### قم بإنشاء مجلد جديد وفك ضغط الملف.

    mkdir MKEcoin
    tar -xjvf linux64 -C MKEcoin

### شَغِل الخادم.

    cd MKEcoin
    ./MKEcoind

### الخيارات:

أعرض قائمه بكل الخيارات والإعدادات:

    ./MKEcoind --help

شَغِل الخادم بالخلفيه:

    ./MKEcoind --detach

تابع مُخرجات الخادم `MKEcoind`:

    tail -f ~/.bitMKEcoin/bitMKEcoin.log

حافظ علي أمان الخادم بتشغيل التحديثات التلقائيه:

https://help.ubuntu.com/community/AutomaticSecurityUpdates


