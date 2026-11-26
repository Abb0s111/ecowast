# EcoWast: sozlash qo'llanmasi

Barcha sozlamalar `index.html` oxiridagi `CONFIG` blokida. Bo'sh qoldirilgan narsa sahifada ko'rinmaydi.

## 1. Buyurtmalar Telegramga kelishi
1. Telegramda **@BotFather** orqali yangi bot yarating va tokenni oling.
2. Botga `/start` yozing, so'ng chat ID ni **@userinfobot** orqali bilib oling (guruhga ulasangiz, guruh ID si kerak).
3. https://dash.cloudflare.com > Workers & Pages > Create > Worker. `worker.js` mazmunini joylang va Deploy qiling.
4. Worker > Settings > Variables and Secrets: `BOT_TOKEN` (Secret), `CHAT_ID`, `ALLOWED_ORIGIN` (masalan `https://ecowast.uz`).
5. Worker manzilini `CONFIG.ORDER_ENDPOINT` ga qo'ying. Server javob bermasa, forma avtomatik ravishda WhatsApp/Telegram usuliga qaytadi.

## 2. Statistika
- Yandex Metrika yoki Google Analytics hisobi oching, ID ni `YANDEX_METRIKA_ID` / `GA_ID` ga yozing.
- Kuzatiladigan hodisalar: `phone_click`, `whatsapp_click`, `telegram_click`, `cta_order`, `order_submit`, `order_sent`, `district_select`, `calc_apply`.

## 3. Rasmlar
1. Asl rasmlarni `images-src/` ga tashlang, `pip install pillow`, so'ng `python optimize-images.py`.
2. `images/` dagi fayllarni `CONFIG.GALLERY` ga yozing.

## 4. Narx kalkulyatori
`CONFIG.PRICES` ni haqiqiy narxlar bilan to'ldiring (namuna blok ichida izohda). Narx 0 bo'lgan xizmat kalkulyatorda chiqmaydi.

## 5. Sharhlar
`CONFIG.REVIEWS` ga faqat haqiqiy mijozlarning, ularning roziligi bilan olingan fikrlarini qo'shing.

## 6. Hosting va domen
Fayllar: `index.html`, `robots.txt`, `sitemap.xml`, `images/`. Cloudflare Pages, Netlify yoki GitHub Pages'ga yuklang, so'ng hosting panelida `ecowast.uz` domenini ulang va DNS yozuvlarini ko'rsatilganidek kiriting.

## Ochiq qolgan joylar
- Telefon `+998991234567` namunaviy: `index.html` da (HTML, JSON-LD, `CONFIG.PHONE`) almashtiring.
- Statistika ulansa, saytga cookie/maxfiylik haqida qisqa ogohlantirish qo'shish tavsiya etiladi.
