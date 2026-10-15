# Karakter Atlası

Türkçe, ücretsiz ve özgün illüstrasyonlu kişilik keşif sitesi. 16 tip profili, 32 soruluk eğitsel test, MBTI tercihleri ve tip dinamikleri, 9 Enneagram tipi, kaynaklı dağılım tablosu içerir.

## Yerelde çalıştırma

Statik HTML/CSS/JavaScript kullanır; derleme veya paket kurulumu gerekmez. ES modülleri nedeniyle bir yerel sunucu açın:

```sh
python3 -m http.server 8000
```

Ardından `http://localhost:8000` adresini açın.

## Ücretsiz GitHub Pages yayını

Canlı adres: **https://ssuheyyo.github.io/karakter-atlasi/**

Kaynak depo: **https://github.com/ssuheyyo/karakter-atlasi**

Yayın, herkese açık deponun `main` dalındaki `/(root)` klasöründen GitHub Pages ile yapılır. Alan adı satın almak gerekmez.

Site tüm varlıkları göreli yollarla çağırır, bu nedenle GitHub Pages alt yolunda da çalışır.

## Google ile giriş ve bulut sonucu

GitHub Pages sadece statik dosya barındırır; Google girişi için ayrıca ücretsiz bir **Firebase** projesi gerekir. Giriş kurulmadan test ve tarayıcı içi sonuç kaydı çalışır; giriş düğmesi kurulum gerektiğini açıkça söyler.

1. [Firebase Console](https://console.firebase.google.com/) üzerinden proje ve Web App oluşturun.
2. **Authentication → Sign-in method** bölümünde **Google** sağlayıcısını etkinleştirin.
3. **Authentication → Settings → Authorized domains** bölümüne `ssuheyyo.github.io` alan adını ekleyin. Yerel test yapacaksanız `localhost` alan adını da ekleyin.
4. **Firestore Database** oluşturun. `firestore.rules` içeriğini **Rules** bölümüne yapıştırıp yayınlayın. Kural, kullanıcıya yalnızca kendi sonucunu okuma ve yazma hakkı verir.
5. Web uygulaması ayarlarındaki `apiKey`, `authDomain`, `projectId`, `appId` değerlerini `firebase-config.js` içine ekleyip gönderin. Bunlar istemci yapılandırma değerleridir, gizli yönetici anahtarı değildir. **Service account / admin özel anahtarını asla depoya koymayın.**
6. Sitenin yayınlandığı adreste Google girişi ve sonuç senkronizasyonunu deneyin. Popup engellendiyse tarayıcıda bu site için popup izni verin.

## Testin sınırı

Bu 32 soruluk özgün bir öz değerlendirmedir; resmî MBTI® envanteri, klinik değerlendirme veya bilimsel tanı değildir. Her eksen için 8 soru, 1–5 katılım ölçeği kullanılır. E/I, S/N, T/F, J/P eksenlerinde göreli tercih puanı hesaplanır. Merkeze yakın sonuçlar özellikle belirsiz olarak belirtilir. Sonuç tarayıcıda `localStorage` ile tutulur; Firebase etkinse ayrıca kullanıcıya özel Firestore belgesine kaydedilir.

Dağılım yüzdeleri dünyaya ait değildir. Sitedeki değerler *MBTI Manual* (3. basım, 1998) ABD örnekleminden sık aktarılan yaklaşık paylardır. Örneklem, tarih ve araç değiştikçe oranlar değişir.

## Kaynaklar

- [Myers & Briggs Foundation — 16 tip](https://www.myersbriggs.org/my-mbti-personality-type/the-16-mbti-personality-types/)
- [Myers & Briggs Foundation — tip dinamikleri](https://www.myersbriggs.org/unique-features-of-myers-briggs/type-dynamics-overview/)
- [Myers & Briggs Foundation — güvenirlik ve geçerlik](https://www.myersbriggs.org/research-and-library/validity-reliability/)
- [Enneagram Institute — dokuz tip](https://www.enneagraminstitute.com/type-descriptions/)
- [ABD örneklemini inceleyen araştırma](https://www.scirp.org/journal/paperinformation?paperid=44318)
- [Firebase Google girişi belgeleri](https://firebase.google.com/docs/auth/web/google-signin)
- [GitHub Pages yayınlama belgeleri](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

Karakter illüstrasyonları bu proje için özgün olarak üretilmiştir. Tip açıklamaları kaynaklardan alıntı değil, proje için yazılmış yorumlayıcı Türkçe içeriktir. MBTI® ve Myers-Briggs Type Indicator® ilgili hak sahiplerinin ticari markalarıdır; bu proje onlarla bağlantılı değildir.
