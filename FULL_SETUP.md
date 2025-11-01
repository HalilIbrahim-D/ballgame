# 🎮 TAM PROJE KURULUM REHBERİ

Bu proje **Unity Editor**'de açıldığında hazır olacak şekilde yapılandırılmıştır!

## ✅ Projede Bulunanlar

### 📁 Klasör Yapısı
```
cursorgame/
├── Assets/
│   ├── Scripts/          ✅ (Tüm C# scriptleri)
│   ├── Scenes/           ✅ (GameScene.unity)
│   ├── Prefabs/          ✅ (Arrow.prefab)
│   ├── Materials/        ✅ (Hazır)
│   └── Sprites/          ✅ (Hazır)
├── ProjectSettings/      ✅ (Unity ayarları)
└── Packages/             ✅ (Bağımlılıklar)
```

### 📝 Scriptler
- ✅ `BallController.cs` - Top kontrolü
- ✅ `Arrow.cs` - Ok davranışı
- ✅ `ArrowSpawner.cs` - Ok spawn sistemi
- ✅ `GameManager.cs` - Oyun yönetimi

### 🎯 Scene Hazırlığı
- ✅ Main Camera (Orthographic, Size: 5)
- ✅ Ball GameObject (Tag: Ball, Rigidbody2D, BallController)
- ✅ Ground GameObject (Tag: Ground, BoxCollider2D)
- ✅ ArrowSpawner GameObject (ArrowSpawner script)
- ✅ GameManager GameObject (GameManager script)

### 🏷️ Tag Ayarları
- ✅ Ball tag'i oluşturuldu
- ✅ Ground tag'i oluşturuldu

## 🚀 Unity'de Açma Adımları

### 1. Unity Hub'dan Projeyi Aç
1. Unity Hub'ı aç
2. **Add** butonuna tıkla
3. `C:\Users\Halo\Desktop\cursorgame` klasörünü seç
4. Unity sürümü seç (2021.3 LTS veya üzeri önerilir)
5. **Open** ile projeyi aç

### 2. Scene'i Kontrol Et
1. `Assets/Scenes/GameScene.unity` dosyasını aç
2. Hierarchy penceresinde şunları görmelisin:
   - Main Camera
   - Ball
   - Ground
   - ArrowSpawner
   - GameManager

### 3. Prefab Referanslarını Düzelt

#### Arrow Prefab'ı Ayarla:
1. `Assets/Prefabs/Arrow.prefab` dosyasını aç
2. Inspector'da Arrow script'inin ekli olduğunu kontrol et
3. Eğer script görünmüyorsa: Add Component → Arrow script'ini ekle

#### ArrowSpawner'a Prefab Bağla:
1. Hierarchy'de `ArrowSpawner` seç
2. Inspector'da `Arrow Spawner` component'ini bul
3. `Arrow Prefab` alanına `Assets/Prefabs/Arrow.prefab` dosyasını sürükle

### 4. UI Oluştur (Canvas)

#### Canvas ve UI Elementleri:
1. **Hierarchy** → **Right Click** → **UI** → **Canvas**
2. Canvas seçili iken **Inspector**:
   - Canvas Scaler → **UI Scale Mode**: Scale With Screen Size
   - Reference Resolution: **1080 x 1920** (mobil için)

#### Start Panel:
1. Canvas → **Right Click** → **UI** → **Panel** → İsim: `StartPanel`
2. StartPanel → **Right Click** → **UI** → **Button** → İsim: `StartButton`
   - Text: "START" veya "BAŞLA"
   - Button'u düzenle, güzel görün

#### Game Over Panel:
1. Canvas → **Right Click** → **UI** → **Panel** → İsim: `GameOverPanel`
2. GameOverPanel içinde:
   - **Right Click** → **UI** → **Text** → İsim: `FinalScoreText`
     - Text: "Final Score: 0"
   - **Right Click** → **UI** → **Button** → İsim: `RestartButton`
     - Text: "RESTART" veya "YENİDEN"

#### In-Game UI:
1. Canvas → **Right Click** → **UI** → **Text** → İsim: `ScoreText`
   - Anchor: **Top-Left**
   - Position: **(50, -50, 0)**
   - Text: "Score: 0"
   - Font Size: 30
   - Color: Beyaz

2. Canvas → **Right Click** → **UI** → **Text** → İsim: `LevelText`
   - Anchor: **Top-Right**
   - Position: **(-50, -50, 0)**
   - Text: "Level: 1"
   - Font Size: 30
   - Color: Beyaz

### 5. GameManager'a UI Referanslarını Bağla

1. Hierarchy'de `GameManager` seç
2. Inspector'da `Game Manager` component'inde:
   - `Start Panel` → `StartPanel` GameObject'ini sürükle
   - `Game Over Panel` → `GameOverPanel` GameObject'ini sürükle
   - `Score Text` → `ScoreText` Text component'ini sürükle
   - `Level Text` → `LevelText` Text component'ini sürükle
   - `Final Score Text` → `FinalScoreText` Text component'ini sürükle
   - `Restart Button` → `RestartButton` Button component'ini sürükle
   - `Start Button` → `StartButton` Button component'ini sürükle

### 6. Görsel İyileştirmeler (Opsiyonel)

#### Ball'a Sprite/Color:
1. Ball seç
2. Inspector → **Add Component** → **Sprite Renderer**
3. Veya basit renk için Material ekle

#### Ground'a Görsel:
1. Ground seç
2. Inspector → **Add Component** → **Sprite Renderer**
3. Veya basit bir kare sprite oluştur

#### Arrow'a Görsel:
1. Arrow Prefab'ı aç
2. Inspector → **Add Component** → **Sprite Renderer**
3. Arrow şeklinde bir sprite ekle veya renklendir

## 🎮 Test Etme

1. **Play** butonuna bas (▶️)
2. **Start Button**'a tıkla
3. **Space** tuşu ile top zıplasın
4. Oklar sağdan gelmeye başlasın!
5. Top oklara çarptığında Game Over ekranı çıksın

## 🔧 Sorun Giderme

### Script Referansları Eksik
- Unity Editor açıldığında script'ler otomatik compile olur
- Eğer hata varsa Console penceresine bak
- Script dosyalarının `Assets/Scripts/` içinde olduğundan emin ol

### Prefab Referansları Çalışmıyor
- ArrowSpawner'da Arrow Prefab referansını manuel olarak sürükleyip bırak
- Arrow Prefab'ının Inspector'da doğru script'lere sahip olduğunu kontrol et

### UI Görünmüyor
- Canvas'ın Render Mode'unun "Screen Space - Overlay" olduğundan emin
- UI elementlerinin aktif (enabled) olduğunu kontrol et

### Oklar Spawn Olmuyor
- GameManager'ın StartGame() çağrıldığından emin ol
- ArrowSpawner'da Prefab referansının olduğunu kontrol et
- Console'da hata mesajı var mı bak

### Top Zıplamıyor
- BallController script'inin Ball'a eklendiğinden emin
- Rigidbody2D'nin Gravity Scale'inin 0 olduğundan emin
- Space tuşuna bas veya ekrana dokun

### Çarpışma Algılanmıyor
- Arrow'un Collider'ının Is Trigger açık olmalı
- Ball'un tag'inin "Ball" olduğundan emin
- Arrow'un tag'inin doğru olduğundan emin

## 📱 Mobil Build

1. **File** → **Build Settings**
2. Platform: **Android** veya **iOS** seç
3. **Switch Platform**
4. **Player Settings**:
   - Company Name: İstediğin isim
   - Product Name: CursorGame
   - Default Orientation: Portrait
5. **Build** veya **Build and Run**

## ✨ Özellikler

- ✅ Dokunma ile zıplama (mobil)
- ✅ Klavye kontrolü (test için)
- ✅ Dinamik ok takibi
- ✅ Level sistemi
- ✅ Skor sistemi
- ✅ UI yönetimi
- ✅ Game Over sistemi
- ✅ Restart mekaniği

## 🎯 Oyun Kuralları

1. Topa dokunarak zıpla (Space tuşu da çalışır)
2. Sağdan gelen oklardan kaçın
3. Her saniye skor artar
4. Her 100 skorda level artar
5. Level artınca ok hızı ve sayısı artar
6. Ok topa çarparsa oyun biter

## 📝 Notlar

- Unity Editor'de ilk açılışta script'ler compile olur (1-2 dakika)
- GUID'ler Unity tarafından otomatik oluşturulur
- Scene dosyasında bazı referanslar placeholder olabilir, manuel bağlaman gerekebilir
- Tüm core mekanikler hazır, sadece görsel iyileştirmeler yapabilirsin

---

**İyi oyunlar! 🎮**

