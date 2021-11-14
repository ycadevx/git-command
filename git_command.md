# GIT KOMUTLARI
## _İş Akışı :_

**Yerel deponuz git tarafından yönetilen üç "ağaçtan" oluşur.** 
- Çalışma Dizini (Director)
- Stage
- HEAD 

**Birincisi gerçek dosyaları tutan Çalışma Dizini.**
<br>**ikinci etap Stage.**
<br>**Sonuncusu yaptığınız son commit'i gösteren HEAD.**


## _START COMMAND_
**Yeni bir depo oluşturmak için, bir klasör oluşturup içerisinde komutu çalıştırın.**

```sh
git init
```

## _CLONE Command_ 
**Bir depoyu kopyalamak
yerel deponuzun çalışan bir kopyasını oluşturmak için**

```sh
git clone /yol/depo
```

*Uzak sunucu kullandığımız durumda*
```sh
git clone kullaniciadi@sunucu:/yol/depo
```
## _Add & Commit_

**Değişiklikleri belirtmek (Index'e eklemek) için**
```sh
git add <dosyaadı>
git add *
```
**Temel git iş akışında bu ilk adımdır. Değişiklikleri depoya eklemek için.**
```sh
git commit -m "Teslim mesajı"
```

**Şimdi dosyalar HEAD'e eklendi, fakat henüz uzak deponuza değil.**

## _Değişiklikleri Göndermek  -PUSH_
*Şuan değişikliklerimiz yerel depomuz *HEAD* içerisinde.*
*Bu değişiklikleri uzak deponuza göndermek için,*

```ruby
git push origin master 
```

*Değişiklikleri uzak deponuzdaki göndermek istediğiniz branch'ı master ile değiştirin.*

## _Uzak Depo Ekleme_
<code> git remote add origin sunucu </code>


## _BRANCH_

**Branchlar farklı özellikleri ayrı ayrı geliştirmek için kullanılır. Yeni bir depo oluşturduğunuzda master "varsayılan" branchtır. Diğer branchlar geliştirildikten sonra master'a birleştirilir.**
</br>
</br>
![BRANCH](https://r.resimlink.com/2j5PQa.png)


*Yeni bir branch oluşturup o dala geçmek için ;*
```
 git checkout -b feature_x
```

*Master'a geri geçmek için*
```
 git checkout master
```

*Oluşturduğumuz branch'ı silmek için*
```
git branch -d feature_x
```

*Eğer bir branch uzak depoya gönderilmez ise başkaları tarafından kullanılmaz. Branch  uzak depoya göndermek için*

```
git push origin <branch>
```

## _GÜNCELLEME VE BİRLEŞTİRME (ADD&PULL&MERGE)_


*En son değişiklikleri (commit) yerel deponuza almak için *
```
git pull
```
*Depomuza alma işlemi ile  Fetch ve Merge işlemi yapmış olacağız*

*Aktif brach'a başka bir branch'ı birleştirmek için*
```
git merge branch
```

*Her merge işlemi sağlıklı olmaz. Bu otomatik birleştirmeler bazı problemlere sebep olabilir. 
Bu çakışmalara yani Conflict'leri birleştirmek kullanıcıya düşer.*

*Değişikliklerden sonra dosyaları  eklemek için;*
```
git add <dosyaadı>
```

*Değişiklikler olmadan önce önizleme yapmak için;*
```
git diff <kaynak_branch> <hedef_branch>
```

## _VERSİYONLAMAK_ 

*Uzak depoya veriler Push edilip,işlemler tamamlandıktan sonra sürüm adı oluşturulmalı.*
</br>

*1.0.0 adıyla 1a2b3c4d bir sürüm oluşturmak için*
</br>
*1a2b3c4d yayımlanacak yazılım sürümünüz işlem numarasının ilk 10 karakteridir*
</br>
*İşlem kimlik numaralarını görmek için;*</br>
```
git log
```

```
git tag 1.0.0 1a2b3c4d
```

## _CHECKOUT_

*Yaptığınız değişiklikleri  geri almak için;*

```
git checkout -- <dosyaadı>git log
```

*Bu değişiklik ile HEAD içerisinde ki son içerik ile değiştirilir.Index'e önceden eklenmiş değişiklikler ve yeni dosyalar korunacaktır.*
</br>

*Eğer tüm yerel değişiklik ve teslimlerinizi iptal etmek istiyorsanız, sunucudan en son kayıtları getirin ve yerel master branchınıza gösterin*
```
git fetch origin
git reset --hard origin/master
```


## _EXTRA_

*dahili git GUI (Grafiksel Kullanıcı Arayüzü)*
```
gitk
```
*renkli git çıktısı kullanın*
```
git config color.ui true
```
*commit başına sadece tek satır log gösterin*
```
git config format.pretty oneline
```
*interaktif ekleme kullanın*
```
git add -i
```