---
layout: page
title: Privacy Policy
permalink: /privacy/
---

# Gizlilik Politikası — Yolio

Son güncelleme: 2026-05-17

## Özet

Yolio, yola çıkmadan önce rota üzerinde yaklaşık hava durumunu ve gelecek tahminleri görmenizi sağlar.
Uygulama **kullanıcı hesabı tutmaz**, **canlı konum izlemez** (varsayılan olarak)
ve **kişisel verileri sunucumuzda saklamaz**.

Aşağıdaki bölümler **şu anda aktif olan davranışı** ve **gelecekte eklenebilecek
opsiyonel premium özellikleri** ayrı ayrı tanımlar.

---

## 1. Şu an topladığımız veri (mevcut MVP)

Uygulamayı kullandığınızda yalnızca aşağıdaki bilgiler **bir defalık** olarak
sunucumuza iletilir:

- Yazdığınız **başlangıç ve varış metni** (örn. "İzmir", "İstanbul")
- Otomatik tamamlamadan seçtiğiniz **yer koordinatı** (opsiyonel)
- Seçtiğiniz **çıkış saati**
- Cihazınızın **dil ve birim tercihi** (TR/EN, metric/imperial)
- Cihazınızın **ülke kodu** (geocoding biası için, örn. "TR")

Bu bilgiler 3rd party servislere sorgu yapmak için kullanılır.
Sunucumuzda **5 dakika boyunca cache'lenir**, ardından silinir.

## 2. Şu an toplamadığımız veri (mevcut MVP)

- **Konum izni istemiyoruz.** GPS verisi alınmaz.
- **Hesap yok.** Kayıt/giriş bilgisi yok.
- **Reklam takipçisi yok.**
- **Çerez yok** (mobil uygulamada söz konusu değil).
- **Kullanım analitiği yok**. İleride eklenirse bu doküman güncellenir.

## 3. Cihazda saklanan veriler (sunucuya gitmez)

Aşağıdaki bilgiler **yalnızca sizin cihazınızda** kalır (AsyncStorage):

- Geçmiş yolculuk planları (en son 20 adet)
- Kayıtlı (favori) yolculuklar
- Tercih ayarları (dil override, birim override)

Uygulamayı silmek bu verilerin tamamını siler.

## 4. 3rd party servisler

Sorgularınız anonim olarak şu servislere iletilir:

- **OpenRouteService** — rota hesaplama, adres çözümü, otomatik tamamlama
  ([Privacy Policy](https://openrouteservice.org/privacy/))
- **Open-Meteo** — saatlik hava tahmini, hava kalitesi
  ([Terms](https://open-meteo.com/en/terms))

Her iki servis de IP adresinizi geçici olarak görür. Yolio bu IP'leri saklamaz.

## 5. Veri saklama süreleri (sunucu)

| Veri | Süre |
|---|---|
| Plan cevabı cache'i | 5 dakika |
| Hava tahmini cache'i | 30 dakika |
| Rota cache'i | 24 saat |
| Geocoding cache'i | 30 gün |

Geliştirme ortamında cache tamamen kapalıdır. Kalıcı kullanıcı veritabanı yok.

---

## 6. Premium özellikler — opsiyonel veri kullanımı (gelecek sürümlerde)

Aşağıdaki özellikler henüz **aktif değildir**. Eklendiklerinde **opsiyonel**
olacak; kullanmak istemezseniz davranış mevcut MVP ile aynı kalır.

### 6.1. Push bildirimleri (premium, opt-in)

Premium kullanıcılar şu bildirimleri alabilir:

- "Yarınki yolculuğun için hava değişti"
- "Yola çıkmadan 1 saat kaldı"
- "Bursa yakınında yağmur başladı" (Akıllı Sürüş Modu açıksa)

**Toplanan veri:**
- **Cihaz push token'ı** (Apple APNs veya Firebase FCM tarafından üretilen
  anonim kimlik) — sadece bildirim göndermek için sunucumuzda saklanır.
- **Kayıtlı yolculuklarınıza ait özet** (origin/destination/zaman) — bildirim
  zamanlamak için 30 günden uzun saklanmaz.

**Kontrol:** Uygulama içi ayarlardan veya cihaz sistem ayarlarından bildirimleri
istediğiniz zaman kapatabilirsiniz. Token sunucudan silinir.

### 6.2. Akıllı Sürüş Modu — Konum izni (premium, opt-in)

Bu özellik açıldığında uygulama, **rotanız üzerindeki ara noktalara yaklaştığınızda**
otomatik olarak saat ve hava bilgilerini günceller.

**Nasıl çalışır:**
- Yalnızca "**Uygulama kullanılırken**" konum izni istenir. Arka plan konum
  izlemesi **istenmez**.
- Konum verisi **yalnızca cihazınızda** geofence (coğrafi sınır) kontrolü için
  kullanılır.
- **Ham koordinatlar sunucumuza gönderilmez**. Yalnızca "X noktasına ulaştın"
  olayı tetiklendiğinde, o noktanın sonrasındaki saatlerin hava güncellemesi
  istenir.
- Uygulama kapatıldığında konum izleme durur.

**Kontrol:** Akıllı Sürüş Modunu istediğiniz zaman kapatabilirsiniz. Cihaz
ayarlarından konum iznini de kaldırabilirsiniz.

### 6.3. Abonelik (premium)

Premium özellikleri kullanmak için aylık veya yıllık abonelik gerekir.

- **Ödeme:** Apple App Store veya Google Play Store üzerinden işlenir.
  **Kart bilgileriniz Yolio sunucusuna asla iletilmez**.
- **Abonelik doğrulama:** RevenueCat altyapısı kullanılır
  ([RevenueCat Privacy Policy](https://www.revenuecat.com/privacy/)). Sadece
  abonelik durumunuz (premium / değil) sorgulanır.
- **Anonim kullanıcı kimliği:** Uygulamada hesap olmadığı için, abonelik
  durumunu cihazınıza bağlı anonim bir kimlik üzerinden takip ederiz. Bu kimlik
  e-posta veya kişisel bilgi içermez.

**Cihaz değiştirme:** Apple/Google aboneliğiniz cihaz değişikliğinde otomatik
taşınır (aynı Apple ID / Google hesabı ile).

### 6.4. Crash raporları (premium, opsiyonel)

Eğer uygulama çökerse, gönüllü olarak anonim çökme raporları gönderebilirsiniz
([Sentry](https://sentry.io/privacy/)). Bu raporlar şunları içerir:

- Çökme stack trace'i (hangi fonksiyonda hata)
- Cihaz modeli ve OS sürümü
- Yolio sürümü

**İçermez:** kişisel veri, konum, yolculuk içeriği.

---

## 7. Çocuklara yönelik

Yolio özel olarak çocuklara pazarlanmaz; 4+ yaş için uygun bir araç
uygulamasıdır. Çocuklardan herhangi bir kişisel veri toplanmaz.

## 8. Avrupa kullanıcıları (GDPR)

Avrupa Birliği'nde bulunuyorsanız aşağıdaki haklara sahipsiniz:

- Sizinle ilgili saklanan verilere erişim talep etme
- Verilerin silinmesini talep etme
- İşleme itiraz etme

Yolio uygulama tasarımı gereği kişisel veri saklamadığından bu talepler için
özel bir form gerekmez — uygulamayı silmek tüm yerel veriyi siler. Yine de
sorularınız için privacy@yolio.app adresine yazabilirsiniz.

## 9. California kullanıcıları (CCPA)

Yolio kişisel veri satmaz, kiralama veya pazarlama amaçlı paylaşmaz.

## 10. Değişiklikler

Bu politika değişirse:
- "Son güncelleme" tarihi yenilenir.
- Önemli değişikliklerde uygulama içinde bilgilendirme yapılır.
- Geriye dönük değişiklik (önceki davranışı etkileyen) yapılmaz.

## 11. İletişim

Gizlilik soruları için: **privacy@yolio.app**

---

# Privacy Policy — Yolio (English)

Last updated: 2026-05-17

## Summary

Yolio shows approximate weather along your driving route before you leave.
The app **does not require an account**, **does not track your live location by
default**, and **does not store personal data on our servers**.

Sections below describe **current behavior (MVP)** and **optional premium
features that may be added in the future**, marked separately.

---

## 1. What we collect (current MVP)

When you use the app, only the following is sent **once** to our server:

- The **origin and destination text** you typed (e.g. "Izmir", "Istanbul")
- The **place coordinates** from autocomplete (when you pick a suggestion)
- The **departure time** you selected
- Your device **language and unit preferences** (TR/EN, metric/imperial)
- Your device **country code** (for geocoding bias, e.g. "TR")

This data is forwarded to third-party services. Cached on our server for
**5 minutes**, then discarded.

## 2. What we do NOT collect (current MVP)

- **No location permission.** No GPS data.
- **No accounts.** No login credentials.
- **No advertising trackers.**
- **No cookies.**
- **No usage analytics** (in MVP — this document will be updated if added).

## 3. Stored on your device only

The following lives **only on your device** (AsyncStorage):

- Trip history (last 20)
- Saved (favorite) trips
- Preferences (language override, unit override)

Uninstalling the app removes all of this.

## 4. Third-party services

Your queries are forwarded anonymously to:

- **OpenRouteService** — routing, geocoding, autocomplete
  ([Privacy](https://openrouteservice.org/privacy/))
- **Open-Meteo** — hourly weather forecast, air quality
  ([Terms](https://open-meteo.com/en/terms))

Both services see your IP address temporarily. Yolio does not store these IPs.

## 5. Server-side retention

| Data | Retention |
|---|---|
| Plan response cache | 5 minutes |
| Weather cache | 30 minutes |
| Route cache | 24 hours |
| Geocoding cache | 30 days |

No persistent user database.

---

## 6. Premium features — optional data usage (future versions)

The following are **not yet active**. When introduced, they will be
**opt-in**; if you don't enable them, behavior matches the current MVP.

### 6.1. Push notifications (premium, opt-in)

Premium users can receive notifications such as:

- "Weather changed for your trip tomorrow"
- "1 hour until your departure"
- "Rain started near Bursa" (when Smart Drive Mode is on)

**Data collected:**
- **Device push token** (anonymous identifier from Apple APNs or Firebase FCM)
  — stored on our server only to send notifications.
- **Summary of your saved trips** (origin/destination/time) — used to schedule
  notifications; not kept longer than 30 days.

**Control:** You can turn notifications off in app settings or device system
settings at any time. The token is removed from our server.

### 6.2. Smart Drive Mode — Location permission (premium, opt-in)

When enabled, the app automatically updates upcoming waypoint times and weather
as you approach each point along the route.

**How it works:**
- Only "**While Using the App**" location permission is requested. **No
  background tracking.**
- Location is used **only on your device** for geofence checks.
- **Raw coordinates are never sent to our servers.** Only the event "you crossed
  waypoint X" triggers a weather refresh for upcoming points.
- Tracking stops when you close the app.

**Control:** You can disable Smart Drive Mode anytime. Location permission can
also be revoked in device settings.

### 6.3. Subscription (premium)

Premium features require a monthly or annual subscription.

- **Payment:** Processed through Apple App Store or Google Play.
  **Your card information is never sent to Yolio servers.**
- **Subscription validation:** Handled via RevenueCat
  ([Privacy](https://www.revenuecat.com/privacy/)). Only your subscription
  status (premium / free) is queried.
- **Anonymous user ID:** Since the app has no accounts, we use a device-bound
  anonymous identifier to track subscription status. This ID contains no email
  or personal info.

**Device switching:** Apple/Google subscriptions automatically transfer when
you change devices (same Apple ID / Google account).

### 6.4. Crash reports (premium, optional)

If the app crashes, you may voluntarily send anonymous crash reports
([Sentry](https://sentry.io/privacy/)). Reports include:

- Crash stack trace (which function failed)
- Device model and OS version
- Yolio version

**Not included:** personal data, location, trip content.

---

## 7. Children

Yolio is not specifically marketed to children. It is rated 4+ as a general
utility app. No personal data is collected from children.

## 8. European users (GDPR)

If you are in the EU, you have the right to:

- Request access to data we hold about you
- Request deletion
- Object to processing

Yolio's design avoids storing personal data, so these requests are typically
satisfied by uninstalling the app (which clears all local data). You may still
contact privacy@yolio.app with any concerns.

## 9. California users (CCPA)

Yolio does not sell, rent, or share personal data for marketing.

## 10. Changes

If this policy changes:
- The "Last updated" date is renewed.
- Major changes are announced inside the app.
- We do not make retroactive changes that worsen existing user privacy.

## 11. Contact

Privacy questions: **privacy@yolio.app**
