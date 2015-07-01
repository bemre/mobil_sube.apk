Türk Finans Sektörünü Hedef Alan Mobil Zararlı Yazılım: Mobil Şube
==================================================================

Geçtiğimiz senelerde [MitB](https://en.wikipedia.org/wiki/Man-in-the-browser)* zararlı yazılımlarından [**Tinba**] ile baş gösteren
ve Türkiye'deki banka müşterilerini hedef alan salgından sonra şirketlerin
korkulu rüyası [**cryptolocker**] vakaları olmuştu. 

Şimdilerde ise zararlı yazılım geliştiricileri kullanımı giderek artan akıllı
telefonlar ve mobil bankacılık uygulamalarını gözlerine kestirmiş gibi
görünüyor. [**Forbes**]'ta yayınlanan makaleye göre mobil cihazlar içerisinde
Android kullanımı %87 civarında olduğu belirtiliyor. Ve yine mobil cihazları
tehdit eden zararlı yazılımların %97'si android platformunu hedef alan
zararlılar olarak görülmektedir. 

![](<imgs/threats-by-platform.jpg>)

Sadece 2014 yılında  900 bini aşkın android zararlı yazılımı tespit edilmiş durumda. Tespit edilen  zararlı yazılımların yaklaşık 50 bin adedi ise info stealer kategorisindedir. Bahsedilen zararlı yazılımların android platformunu etkilemesi iOS ve Windows Phone vs gibi platformların zararlı yazılımlara karşı bağışıklı olduğu anlamına gelmiyor. Zararlı yazılım geliştiricileri pazar payında daha fazla söz sahibi olan Android'den daha fazla geri dönüş alabildikleri için bu platformu tercih ettiği anlaşılmaktadır. Jailbreak, yeni çıkan açıkların istismar edilmesi vb ile Android dışındaki platformlardaki zararlı yazılım oranının da artma eğiliminde olduğu görülmektedir. 

Geliştirilen mobil zararlı yazılımlar komuta kontrol sunucularından alacağı direktifleri akıllı cihaz üzerinde çalıştıracak şekilde yapılandırırlar. Örnek bir [komuta kontrol] sunucusu arayüzü şekildeki gibidir:

![](<imgs/C-C-Panel.png>)
Bu arayüz vasıtası ile ele geçirilen mobil cihaza uzaktan komut gönderilerek cihaz üzerinde istenilen işlemler gerçekleştirilebilmektedir.

Türkiye'de finansal sektörü hedef alan zararlı yazılımları sınıflandırdığımızda ilk beş tehdit olarak aşağıdaki zararlı yazılım aileleri öne çıkmaktadır. 

- Dyre
- Tinba
- Hesperbot
- Carbanak
- Neverquest

Bunların dışında Zeus, gozi, spyeye gootkit, bugat vb. zararlı yazılım aileleri de varlıklarını sürdürmektedir.

Online bankacılık işlemlerini kullanan, neredeyse her _**100 kullanıcının 5**_'inde finans sektörünü hedefleyen zararlı yazılım bulaşmış durumdadır.  

[**DRWEB**]’e göre dünyanın farklı yerlerindeki banka kullanıcılarını hedef alan mobil zararlı yazılımlar email ile yayılmayı hedeflemektedir. Örnek zararlı yazılım:
![](<imgs/sberbank-bankbot.png>)

İndirilen zararlı yazılım ile
- IMEI
- Operator Bilgisi
- Bluetooth Bilgisi
- Cihaz API versiyon Bilgisi
- Trojan versiyon
- Trojan adı
- En son çalıştırılan komut
gibi bilgiler gönderilmekte ve alınmaktadır. 

Geçen senelerde etkin olan Hesperbot ve onunla gelen [**CEPWAP**] isimli mobil zararlı yazılım da benzer şekilde phishing ile yayılmaya başlamış, Android kullanıcılarını hedef almıştır. CEPWAP kendisini OTP yazılımı olarak gösterip arka planda gelen SMS’lerin arasına girmekte, var olan mesajlaşma programlarını kapatmakta ve online bankacılık için lazım olan tek kullanımlık parolayı yakalamaktadır.
![](<imgs/cepwap.png>)


# Mobil Şube
Bugünlerde aktif olan ve bu yazı içerisinde analizini yapacağımız **mobil_sube** zararlı yazılımı Türkiye’deki birçok banka müşterisini hedef almaktadır. **mobil_sube** zararlı yazılımının SMS ile yayıldığını görmekteyiz. Android kullanıcılarını hedef alan **mobil_sube** farklı banka kullanıcılarına, o bankaya ait mobil bankacılık uygulamasının yenilendiğine dair SMS ile sahte bilgilendirme mesajı yollamaktadır. Müşterilere gönderilen örnek SMS mesajlardan bazıları aşağıdaki gibidir.

![](<imgs/SMS-I.png>)

![](<imgs/SMS-II.png>)

Son kullanıcı gelen SMS'teki linke tıklayarak zararlının barındırıldığı web sitesine erişmektedir. İlgili siteden **mobil_sube.apk** kurulum dosyasını indirilmesi sağlamaktadır. Kullanıcı android işletim sistemi dışındaki platformlardaki herhangi bir internet tarayıcı ile erişmeye çalıştığında ise ya ilgili bankanın ana sayfasına yönlendirilmekte ya da boş bir sayfa gösterilmektedir.

Zararlı yazılım geliştiricisi SMS ile gönderdiği linklerde her bir banka için bir subdomain ile ilgili bankaya aitmiş gibi görünen internet bankacılığı uygulamasını indirtmektedir. hedeflenen bankalardan bazılarına ait ekran görüntüleri şu şekildedir:

![](<imgs/bank-I.png>)
![](<imgs/bank-II.png>)
![](<imgs/bank-III.png>)
![](<imgs/bank-IV.png>)
![](<imgs/bank-V.png>)
![](<imgs/bank-VI.png>)
![](<imgs/bank-VII.png>)
![](<imgs/bank-VIII.png>)
![](<imgs/bank-IX.png>)

**mobil_sube** zararlısı geçtiğimiz 3 ay içerisinde her hafta farklı domainler ile yayılmaya çalışmıştır bu domainlerden bazıları:

- mobilsubeyukle.com
- mobilayar.com
- mobilsubeniz.com 
- mobilsubeaktivasyonu.com 
- mobilsubesiaktivasyon.com
- cepsubeonay.com
- mobilaktivasyon.com 
- mobilsubesi.com
- mobilsubeayarlari.com 
- mobilsubeniz.com 
- smsaktivasyon.com
- mobilesubekurulumu.com
- mobilsubekurulum.com

Zararlının yayılmasında bu domainler doğrudan kullanılmamış, her bir domainde hedef alınan banka müşterisine göre **subdomain**ler oluşturulmuş ve uygulama ilgili **subdomain**de servis edilmiştir.
- banka1.mobilsubeyukle.com
- banka3.cepsubeonay.com

gibi.

ilgili domainlerin whois bilgilerine bakıldığında yakın zamanlarda alındığı bilgisi ön plana çıkmaktadır.
- http://whois.domaintools.com/mobilsubeyukle.com
- http://www.tcpiputils.com/browse/domain/mobilsubeayarlari.com
- http://www.tcpiputils.com/browse/ip-address/178.32.143.123
- http://www.yoncu.com/ip/94.23.78.48

Kullanılan domainlerin bazılarına ait IP bilgileri ise şu şekildedir:

| Domain       | IP Adres       |
| -------------|-------------:|
|mobilesubekurulumu.com|5.135.59.57 |
|mobilsubeniz.com|46.105.72.189|
|mobilaktivasyon.com|178.32.58.215|
|mobilsubeniz.com|46.105.72.189|
|smsaktivasyon.com|178.32.143.123|
|mobilesubeaktivasyon.com|37.59.254.50|
|mobilsubeyukle.com |94.23.78.48|
|mobilsubekurulum.com|5.135.59.57|

Zararlı yazılımın ilk ortaya çıktığı tarihlerden kısa bir süre önce internet üzerinde sadece [**virscan.org**] sitesinde bilgi bulanabilmektedir. 
![](<imgs/virscan.png>)

Görüldüğü üzere sadece bir antivirüs tarayıcısı tarafında tanınmaktadır. 

Muhtemelen zararlı yazılımın geliştiricisi zararlının hangi antivirüs tarayıcısı tarafından yakalanabildiğini görmek için bu yöntemi kullanmıştır.

Zararlının güncel versiyonunu VirusTotal’de tanıyabilen tarayıcı oranı ise 13/57’dir. Zararlı infostealer kategorisinde yer almaktadır.
![](<imgs/virustotal.png>)
Uygulama sisteme kurulduktan sonra açmak için ikonuna dokununca kendi ikonunu silmekte ve arkaplanda bir servis olarak çalışmaktadır. Arka planda çalışan servis ile komuta kontrol merkezine veri göndermeye hazır hale gelmektedir.

Kullanıcı bu sitelerden indirdiği APK dosyasının kurulum sırasında istediği izinler şu şekildedir.
![](<imgs/permission-I.png>)
![](<imgs/permission-II.png>)

```XML
<?xml version="1.0" encoding="utf-8"?>
<manifest
    xmlns:android="http://schemas.android.com/apk/res/android" android:versionCode="1" android:versionName="1.0" package="com.googleandroid.listener" platformBuildVersionCode="21" platformBuildVersionName="APKTOOL" >
    <uses-sdk android:minSdkVersion="5" android:targetSdkVersion="19" ></uses-sdk>
    <uses-permission android:name="android.permission.WRITE_SMS" ></uses-permission>
    <uses-permission android:name="android.permission.READ_SMS" ></uses-permission>
    <uses-permission android:name="android.permission.SEND_SMS" ></uses-permission>
    <uses-permission android:name="android.permission.RECEIVE_SMS" ></uses-permission>
    <uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" ></uses-permission>
    <uses-permission android:name="android.permission.READ_PHONE_STATE" ></uses-permission>
    <uses-permission android:name="android.permission.READ_CALL_LOG" ></uses-permission>
    <uses-permission android:name="android.permission.INTERNET" ></uses-permission>
    <uses-permission android:name="android.permission.READ_CONTACTS" ></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" ></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" ></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" ></uses-permission>
    <uses-permission android:name="android.permission.CHANGE_WIFI_STATE" ></uses-permission>
    <uses-permission android:name="android.permission.ACCESS_WIFI_STATE" ></uses-permission>
    <uses-permission android:name="android.permission.CHANGE_NETWORK_STATE" ></uses-permission>
    <uses-permission android:name="android.permission.CALL_PHONE" ></uses-permission>
    <uses-permission android:name="android.permission.READ_LOGS" ></uses-permission>
    <uses-permission android:name="android.permission.WAKE_LOCK" ></uses-permission>
    <application android:theme="@7F060001" android:label="@7F050001" android:icon="@7F020000" android:allowBackup="true" android:largeHeap="true" >
        <activity android:theme="@android:0103000B" android:name="com.googleandroid.listener.LegalActivity" >
            <intent-filter >
                <action android:name="android.intent.action.MAIN" ></action>
                <category android:name="android.intent.category.LAUNCHER" ></category>
            </intent-filter>
        </activity>
        <receiver android:name="com.googleandroid.listener.receivers.ProgramStartReceiver" android:exported="false" >
            <intent-filter >
                <action android:name="com.androidlistener.services.ServiceStart" ></action>
                <action android:name="android.net.conn.CONNECTIVITY_CHANGE" ></action>
                <action android:name="android.intent.action.BOOT_COMPLETED" ></action>
            </intent-filter>
        </receiver>
        <receiver android:name="com.googleandroid.listener.receivers.ProgramBootReceiver" >
            <intent-filter >
                <action android:name="android.intent.action.BOOT_COMPLETED" ></action>
            </intent-filter>
        </receiver>
        <receiver android:name="com.googleandroid.listener.receivers.SmsReceiver" android:exported="true" >
            <intent-filter android:priority="2147483647" >
                <action android:name="android.provider.Telephony.SMS_RECEIVED" ></action>
            </intent-filter>
        </receiver>
        <receiver android:name="com.googleandroid.listener.receivers.SystemDialogReceiver" >
            <intent-filter >
                <action android:name="android.intent.action.CLOSE_SYSTEM_DIALOGS" ></action>
            </intent-filter>
        </receiver>
        <activity android:theme="@android:0103000B" android:name="com.googleandroid.listener.tasks.PopAct" ></activity>
        <service android:name="com.googleandroid.listener.services.LocatorService" ></service>
        <service android:name="com.googleandroid.listener.services.MessageService" ></service>
        <service android:name="com.googleandroid.listener.services.ListenersService" ></service>
    </application>
</manifest> 
```
**mobil_sube** oldukça fazla şüpheli izne gereksinim duymaktadır.
- SMS alma/okuma/yazma/gönderme yapabilmesi,
- Başlangıçta çalışması, 
- Arama yapabilmesi,
- Arama kayıtlarına erişmesi

**mobil_sube** ilk bakışta kendisini gizlemek/tespitini zorlaştırmak için kullandığı isimlendirme formatı ise şu şekildedir: **com.googleandroid.listener**
![](<imgs/googleandroid-listener.png>)
Google’a ait uygulamalar cihaz üzerinde **com.google.*** şeklinde iken kullanıcının gözünden kaçırmak için **com.googleandroid.** isimlendirmesini kullanmaktadır. Bu isimlendirme ile legal görünmeye çalışmaktadır.

Farklı versiyonlara ait komuta kontrol merkezi IP adresleri aşağıdaki gibidir

- **185.50.69.100**
- **188.165.164.108**
- **188.165.3.245**

ve komuta kontrol merkezi ile aşağıdaki URL’leri kullanacak şekilde iletişime geçmektedir.

- http://185.50.69.100:4444/api/Device
- http://188.165.164.108/api/ga.js
- http://188.165.3.245/api/ga.js

Uygulamanın C&C sunucusuna bakıldığında farklı zamanlar içerisinde bu kodun değiştirildiğine ait bilgiler bulunmaktadır. 
![](<imgs/ccc-index.png>)
Görüldüğü üzere sunucu üzerinde komutları alan **ga.js** dosyasının farklı tarihlerde oluşturulmuş yedek dosyaları da bulunmaktadır. **ga - Kopya.js** dosyası ile zararlı yazılım geliştiricisinin türkçe windows işletim sistemi kullandığını düşünebiliriz. Ayrıca C&C de bulunan **ga.js** dosyası javascript dosyası değil bir PHP uygulamasıdır.
ilk yakalanan örnekte **185.50.69.100** IP adresinde **4444** gibi olağan dışı bir port’a erişen zararlı, cihaza ait aşağıdaki verileri göndermektedir.

![](<imgs/status-from-mobile-to-CC.png>)
- IMEI Bilgisi
- Cihaz İsmi
- İşletim Sistemi Versiyonu
- SMS Sayısı
- Güncelleme Zamanı
- Kaydetme Zamanı
- Tarayıcı Geçmişi
- Arama geçmişi
- Adres Defteri
- Konum Bilgisi
- SMS Engelleme
- SMS Aktif Etme
- ID

gibi bilgileri gönderdiği görülebilmektedir. 

Bunun dışında zararlı sanki istihbarat servislerine çalışıyormuş gibi: 
- Telefon görüşmelerini kayıt altına almakta, 
- Cihazın konumunu tespit edip, kayıt altına almakta, 
- Gelen/giden mesajların arasına girmektedir.

Zararlı yazılım telefon görüşmelerini ses dosyası olarak harici kart içerisinde **11111111111111** adlı dizin oluşturarak her aramayı **3gp** formatında kaydetmektedir ve C&C sunucusuna gönderebilmektedir.

Farklı zamanlarda farklı Komuta kontrol merkezlerine gönderilen trafik incelendiğinde uygulamaya ait hangi verilerin gönderildiği bilgisi de elde edilebilmektedir.

![](<imgs/v1post.png>)

Her bir cihazın C&C sunucusuna erişirken kullandığı ID değeri gönderilen HTTP isteğinde bulunan basic authentication parametreleri ile elde edilebilmektedir.

```bash
echo -n "dXNlcm5hbWU6MmNkYjVhYWMtMjE0MC00NmFhLWI4NDgtMjQyMWI5YzlhODY0" | base64 -D

username:2cdb5aac-2140-46aa-b848-2421b9c9a864
```

Zararlı yazılımın ilk örneklerinde HTTP POST verisi açık olarak gönderilirken yeni versiyonlarında ise şifreli olarak iletilmektedir.

![](<imgs/ccserver.png>)

Yeni versiyona ait [HTTP trafiğine buradan](/pcaps/http.pcap) erişebilirsiniz.

Ayrıca zararlının yeni geliştirilen versiyonlarında kod karmaşıklaştırma işlemi de uygulanmıştır. Böylece kodun anlaşılmasını da zorlaştırmıştır. Yeni versiyonda C&C ile iletişime geçerken **ga.js**’ye çeşitli parametreler göndermektedir. Bunlar ise kod içerisinde aşağıdaki satırlarda belirlenebilmiştir. 
```java
	v2 = "ga.js?e=1"; // (String@931)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.a.a, "ga.js?e=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.a.a, "ga.js?e=1"); // (Method@793)
		v2 = "ga.js?ca=1"; // (String@928)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.b.b, "ga.js?ca=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.b.b, "ga.js?ca=1"); // (Method@793)
		v2 = "ga.js?m=1"; // (String@933)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.c.b, "ga.js?m=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.c.b, "ga.js?m=1"); // (Method@793)
		v2 = "ga.js?m=1"; // (String@933)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.d.b, "ga.js?m=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.d.b, "ga.js?m=1"); // (Method@793)
		result = com.a.a.c.a(com.googleandroid.listener.tasks.d.b, "ga.js?m=1"); // (Method@576)
		v3 = "ga.js?ca=1"; // (String@928)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.f.a, "ga.js?ca=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.f.a, "ga.js?ca=1"); // (Method@793)
		v3 = "ga.js?ds=1"; // (String@930)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.g.b, "ga.js?ds=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.g.b, "ga.js?ds=1"); // (Method@791)
		v3 = "ga.js?d=1"; // (String@929)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.h.b, "ga.js?d=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.h.b, "ga.js?d=1"); // (Method@791)
		v4 = "ga.js?m=1"; // (String@933)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.i.a, "ga.js?m=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.i.a, "ga.js?m=1"); // (Method@793)
		v3 = "ga.js?l=1"; // (String@932)
		result = com.googleandroid.listener.a.a.a(com.googleandroid.listener.tasks.i.a, "ga.js?l=1"); // (Method@765)
		result = com.googleandroid.listener.helpers.JSONHttpClient.a(com.googleandroid.listener.tasks.i.a, "ga.js?l=1"); // (Method@793)
```

Göründüğü üzere C&C ile iletişime geçerken kullanılan bazı parametreler bulunmaktadır.
- e,
- m,
- d,
- l,
- ds,
- ca

kodları incelediğimizde sunucu IP adresi, bazı türkçe fonksiyon isimleri ve parametrelere ulaşabilmekteyiz.

Ayrıca kod içerisinde geçen 
![](<imgs/interesting-strings.png>)
```java
localIntent4.setAction("com.muratgokce.services.ServiceStart");
```
**muratgokce** ismini aratinca çıkan [kaynak] ise olayı biraz daha ilginç hale getirmektedir.
![](<imgs/gizli-kamera-notepad.png>)
Zararlıya ait örneklerden bazılarının hash değerleri aşağıdaki gibidir.

- 00c27cd5c671c6a43f477d7c8d267b5d
- 0817e131e722c8634aa37c878caebb9c
- 0d6f21d503b626ab0cac96dd0911a253
- 135182c7b0e72f9ba0f2fa39f6d3584c
- 3ea1e56dae9c41e06a7f8441aba0f444
- 616dc9da911a6d674861450fa629abdd
- 648602e7a6e7d662022146b056815133
- 91d700382d2b14246c2af73643778367
- a296ff07fa5b305c2616d1be003eea2e
- b6ef3a4f212a1b57e56935401dd6c707
- bf56f5cf7d4e0a61cdf7d5ece5e56941
- d17898ac5741c8604e35822a9e9574f4
- d7800b1ae85bf184c422d4e0a935cb27
- ddfbe84fb50763d9d3ebcb908c782735
- f13eb9eda466c1902c0c6324f8318395
- 5e0c5e642c32a8df4ff31abbded53da427ab273f40861d5eca4bb9ae6f38e8db
 


**Devam Edecek...**

[**Tinba**]: https://www.bilgiguvenligi.gov.tr/zararli-yazilimlar/tinba-zararli-yazilim-analizi.html
[**cryptolocker**]: https://www.bilgiguvenligi.gov.tr/zararli-yazilimlar/guncel-cryptolocker-saldirisina-dikkat.html
[**forbes**]: http://www.forbes.com/sites/gordonkelly/2014/03/24/report-97-of-mobile-malware-is-on-android-this-is-the-easy-way-you-stay-safe/
[**DRWEB**]: http://news.drweb.com/show/?i=9489&lng=en&c=5
[**CEPWAP**]: http://www.oguzhantopgul.com/2014/09/android-hesperbot-malware-analysis.html 
[**virscan.org**]: http://r.virscan.org/report/7f94869db35f883f556b832d7bf75a3f
[kaynak]: https://play.google.com/store/apps/details?id=tr.com.muratgokce.spycamera&hl=tr
[Komuta Kontrol]: https://blogs.rsa.com/ibanking-mobile-bot-source-code-leaked/

- *MitB:  Man in the Browser - İnternet tarayıcıları ile kullanıcı arasına girme.
- cryptolocker: fidye amaçlı kişisel dosyaları silen,şifreleyen zararlı yazılım
