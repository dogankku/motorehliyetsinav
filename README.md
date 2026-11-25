# Motosiklet Direksiyon Sınavı – Tarayıcı Oyunu

Resmi "Motorlu Bisiklet ve Motosiklet Direksiyon Eğitim ve Sınav Yeri Krokisi" (EK-7) temel alınarak yapılmış, kuşbakışı HTML5 oyunu. Tek dosya (`index.html`), kurulum gerektirmez. Kuşbakışı ve 3D sürücü gözü (three.js) görünümleri vardır; `V` tuşuyla geçilir. Sürücü gözünde gerçekçi asfalt, gölgeler, çalışan dikiz aynaları, devir/vites göstergesi, yatış ve motor sesi bulunur.

## Oynamak

`index.html` dosyasını tarayıcıda aç. GitHub Pages açıksa şu adresten de oynanabilir:
`https://<kullanıcı-adı>.github.io/<repo-adı>/`

## Aşamalar

1. **Slalom** – 6 m arayla 8 koni, sırayla sağ-sol
2. **Sekiz çizme** – 3,5 m yarıçaplı iki çember, ters yönde tam tur
3. **Denge çizgisi** – 20 m × 20 cm
4. **Dar alanda U dönüşü** – 8 × 6 m (A sınıfı: 8 × 7 m)
5. **Hızlan · yavaşla · dur** – 30 m'de 40 km/h (M: 25 km/h), 30 m'de yavaşlayıp DURMA alanında dur
6. **Engelden kaçış** – 20 km/h ile giriş noktası, engelin yanından geçip çıkış noktasına dönüş
7. **Ani fren** – 20 km/h'de fren çizgisinden sonra kısa mesafede dur

## Kontroller

| Tuş | İşlev |
|---|---|
| ↑ / W | Gaz |
| ↓ / S / Boşluk | Fren |
| ← → / A D | Direksiyon |
| V | Kuşbakışı / sürücü gözü |
| M | Motor sesi aç / kapat |
| Q / E | Sol / sağ sinyal |
| H | Korna (basılı tut) |
| L | Uzun far |
| G | Göstergeye bak (basılı tut) |
| R | Aşamayı baştan al |
| Enter | Başla / tekrar |
| + / − | Yakınlaştır / uzaklaştır |

## Telefonda

Telefonu yan çevir. Sol alttaki SOL / SAĞ kollarına basılı tutarak dön, sağdaki GAZ ve FREN pedallarına basarak hızlan ve yavaşla. Açılış ekranından Joystick ya da "Ekranda kaydır" seçeneğine de geçilebilir. İstersen açılış ekranından "Telefonu eğ" seçerek eğimle sürebilirsin (iPhone'da izin ister). Tam ekran için tarayıcıda "Ana ekrana ekle" de kullanılabilir.

## Özellikler

- Sınav görevlisinin Türkçe sesli ve yazılı komutları
- Her aşamada süre sınırı, sonuçta aşama aşama süreler ve en iyi süre rekoru
- Hata anında motor yatma, sarsıntı ve kırmızı uyarı; düşük hızda gidon salınımı
- Virajda bakış dönüş yönüne kayar
- Rüzgâr, lastik ve fren, çarpma sesleri
- Grafik ayarı (Yüksek / Düşük), telefonda sinyal/korna/far/görünüm düğmeleri

## Kurallar

- Aşama sırasında hız 2 km/h altına düşerse "ayak yere değdi" sayılır.
- Koni/engele çarpmak, çizgiye basmak, şeritten çıkmak hatadır.
- **Sınav modu:** ilk hatada elenirsin. **Antrenman modu:** hatalı aşama tekrarlanır.
- **Gerçekçi / Kolay** zorluk: çizgi toleransları değişir.
