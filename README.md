# React Pre-Commit Kod Checklist

## 1. Genel Kod Kalitesi
- [ ] **Lint Hataları:** `eslint` çalıştırıldı ve tüm uyarı/hata temizlendi.  
- [ ] **Format:** `prettier` ile otomatik formatlama yapıldı.  
- [ ] **Unused:** Tüm kullanılmayan `import`, değişken ve fonksiyonlar kaldırıldı.

## 2. Dosya & Yapı
- [ ] **Dosya Adlandırma:** Bileşen dosya isimleri `PascalCase.jsx/tsx`, yardımcı modüller `camelCase.js/ts` formatında.  
- [ ] **Folder Structure:** Aynı feature/alanla ilgili komponent, hook ve stil dosyaları tek bir klasörde.  
- [ ] **Index Exports:** Gereksiz `index.js` kullanımı yok, named export tercih ediliyor.

## 3. Type Safety / Prop Validation
- [ ] **TypeScript:** Eğer TS kullanıyorsak, tüm `any`’ler yerine spesifik tipler tanımlandı.  
- [ ] **PropTypes:** JS projede PropTypes kullanılıyorsa, tüm bileşenler için `propTypes` ve `defaultProps` eklendi.

## 4. React-Özel Kontroller
- [ ] **Hooks Kuralları:** Tüm hook’lar bileşen üstünde; koşul/döngü içinde hook çağrılmıyor.  
- [ ] **State Yönetimi:** Gereksiz local state’ler kaldırıldı; karmaşıklık durumunda context veya global store düşünüldü.  
- [ ] **Key Props:** List render’larında `key` olarak stable, benzersiz bir değer kullanıldı (index değil).

## 5. Performans
- [ ] **Re-render Kontrolü:** Gerektiğinde `React.memo`, `useMemo`, `useCallback` kullanılarak tekrarlı render’lar engellendi.  
- [ ] **Lazy-Load:** Uygun komponentler ve routelar `React.lazy` + `Suspense` ile bölündü.

## 6. Testler
- [ ] **Unit Test:** Yeni veya değişen bileşenler için Jest + React Testing Library testleri yazıldı.  
- [ ] **Coverage:** Test kapsamı %80’in altına düşmedi.  
- [ ] **Snapshot Test:** Karmaşık UI’larda snapshot test eklendi ve güncellendi.

## 7. Accessibility (Erişilebilirlik)
- [ ] **ARIA Etiketleri:** Gerekli yerlerde `aria-` öznitelikleri eklendi.  
- [ ] **Keyboard Navigasyonu:** Tüm interaktif öğeler klavye odaklanabilir (`tabindex`) ve semantik.  
- [ ] **Alt Metinler:** Görsel içeriklere `alt` parametresi eklendi.

## 8. Güvenlik
- [ ] **XSS Koruması:** HTML içeriklerin doğrudan render’ı yerine `dangerouslySetInnerHTML`’den kaçınıldı veya sanitize edildi.  
- [ ] **Env Değişkenleri:** Sadece `REACT_APP_` prefix’li ve `.env`’de tanımlı değişkenler kullanıldı.

## 9. Dokümantasyon & Commit Mesajı
- [ ] **Kod İçi Yorum:** Karmaşık mantık bloklarına kısa açıklama eklendi.  
- [ ] **README/GUIDE:** Yeni feature varsa `README.md` veya proje dokümantasyonuna eklendi.  
- [ ] **Commit Mesajı:**  
  - Başlık 50 karakteri geçmiyor.  
  - Emoji veya ön ek (feat, fix, chore, refactor) kullanıldı.  
  - Mesajın gövdesi (varsa) 72 karakter satır uzunluğunu aşmıyor; ne, neden yapıldığı kısa anlatıldı.
