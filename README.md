# TetrisliCalarSaat
Gömülü Sistemler Dönem Sonu Projesi

Bu proje, sabah uyanmakta zorlanan bireyler için tasarlanmış etkileşimli bir alarm sistemidir. Ayarlanan saatte otomatik olarak çalan alarm, yalnızca kullanıcı Tetris oyununda 10 puan topladığında kapanır. Alarm sesi, Arduino NANO'nun donanım tabanlı Timer1 zamanlayıcısı ile interrupt (kesme) yoluyla üretilir. Sistem, bir OLED ekran ve 3 buton ile kullanıcı etkileşimini sağlar.

Kullanılan Donanım ve Yazılım

Donanım:
- Arduino NANO
- 128x64 I2C OLED ekran (SSD1306)
- 3 adet push buton (sol, sağ, hız)
- Aktif buzzer
- Breadboard, bağlantı kabloları

Yazılım:
- Arduino IDE
- Gerekli kütüphaneler:
  - Wire.h
  - Adafruit_GFX.h
  - Adafruit_SSD1306.h

Projeyi Çalıştırmak (Kurulum)
1. Arduino IDE'yi açın.
2. Aşağıdaki kütüphaneleri Library Manager üzerinden yükleyin:
   - Adafruit SSD1306
   - Adafruit GFX
3. Kod dosyasını Arduino IDE'ye yapıştırın veya açın.
4. Gerekli bağlantıları aşağıdaki gibi yapın:
   - OLED ekran: VCC → 5V, GND → GND, SDA → A4, SCL → A5  
   - Butonlar: Dijital pin 9, 10 ve 11  
   - Buzzer: Dijital pin 3
5. Arduino UNO’yu bağlayın ve kodu yükleyin.
6. Güç verildiğinde sistem otomatik olarak saati saymaya başlar.

Kullanım Şekli
- Test için sistem saat 08:00:08’e ulaştığında alarm sesi başlar.
- OLED ekran Tetris oyununa geçer.
- Kullanıcı 3 buton ile oyunu oynar:
  - Sol buton → Bloğu sola hareket ettirir
  - Sağ buton → Bloğu sağa hareket ettirir
  - Hız butonu → Bloğu hızlı aşağı indirir
- 10 puan toplandığında alarm susar ve “Günaydın” mesajı görüntülenir.
- Ardından sistem tekrar saat ekranına döner.

Kısıtlamalar
- Yalnızca kare Tetris bloğu kullanılmaktadır (RAM sınırı nedeniyle).
- RTC (gerçek zamanlı saat) modülü eklenmemiştir; zaman millis() ile sayılır.
- Alarm sesi sabit bip olarak ayarlanmıştır.

Geliştirme Önerileri
- RTC modülü ile gerçek saat entegrasyonu
- Daha güçlü bir mikrodenetleyici ile tüm Tetris bloklarının eklenmesi
- Skor kaydı ve oyun seviyelerinin arttırılması
- Bluetooth/Wi-Fi modülü ile mobil kontrol ve takip
- TFT ekran ile daha zengin arayüz
