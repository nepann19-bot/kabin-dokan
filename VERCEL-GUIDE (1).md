# 🚀 Vercel मा वेबसाइट राख्ने पूरा गाइड (नि:शुल्क)

तपाईंको पसललाई **Vercel.com** मा राख्ने तरिका — करिब ३०–४० मिनेट लाग्छ। `index.html` र `Code.gs` फाइल उही चल्छ, केही फेर्नु पर्दैन।

**चाहिने कुरा:** Gmail खाता। पैसा लाग्दैन (डोमेन बाहेक)।

---

## स्टेप १, २, ३: Google Sheet + Apps Script + URL

यी तीन स्टेप **GUIDE.md मा भनेजस्तै** गर्नुहोस् (उही हो):
1. Google Sheet बनाएर ५ ट्याब (Config, Products, Offers, Shipping, Reviews) बनाउने
2. Extensions → Apps Script मा `Code.gs` टाँसेर **Deploy → Web app → Access: Anyone** → URL कपी गर्ने
3. `index.html` Notepad मा खोलेर `API_URL` मा त्यो URL टाँसेर सेभ गर्ने

---

## स्टेप ४: GitHub मा फाइल राख्नुहोस् (Vercel ले यहीँबाट साइट बनाउँछ)

Vercel मा साइट राख्न फाइलहरू पहिले **GitHub** (कोड राख्ने नि:शुल्क साइट) मा हुनुपर्छ — तर चिन्ता नलिनुस्, सबै browser बाटै हुन्छ, कुनै कोडिङ चाहिँदैन:

1. [github.com](https://github.com) मा नि:शुल्क खाता बनाउनुहोस् (Gmail ले हुन्छ)।
2. दायाँमाथि **+ → New repository** थिच्नुहोस्।
3. **Repository name:** `mero-pasal` लेख्नुहोस् → **Public** छानेर → **Create repository** थिच्नुहोस्।
4. खुलेको पेजमा **"uploading an existing file"** भन्ने नीलो लिंक थिच्नुहोस्।
5. आफ्नो `index.html` फाइल **तानेर (drag गरेर)** त्यहाँ छोड्नुहोस्।
6. तल हरियो **Commit changes** बटन थिच्नुहोस्। ✅ फाइल GitHub मा पुग्यो!

---

## स्टेप ५: Vercel मा जोड्नुहोस् (२ मिनेट)

1. [vercel.com](https://vercel.com) मा जानुहोस् → **Sign Up** → **Continue with GitHub** थिच्नुहोस् (भर्खर बनाएको GitHub खाताले login गर्ने)।
2. **Add New… → Project** थिच्नुहोस्।
3. लिस्टमा आफ्नो **mero-pasal** देखिन्छ → छेउको **Import** थिच्नुहोस्।
4. केही फेर्नु पर्दैन — सिधै **Deploy** थिच्नुहोस्।
5. ३०–६० सेकेन्डमा 🎉 — तपाईंको साइट लाइभ! `https://mero-pasal.vercel.app` जस्तो लिंक पाउनुहुन्छ।
6. त्यो लिंक खोलेर **टेस्ट अर्डर** गर्नुहोस् → Google Sheet को **Orders ट्याबमा अर्डर आयो कि हेर्नुहोस्।** ✅

---

## स्टेप ६: आफ्नो डोमेन जोड्नुहोस्

1. डोमेन किन्नुहोस् — Namecheap / Hostinger / GoDaddy (रु. १,५००–२,०००/वर्ष)। **.com.np चाहिँ [register.com.np](https://register.com.np) बाट नि:शुल्क** (नागरिकता/कम्पनी कागज चाहिन्छ)।
2. Vercel मा: आफ्नो प्रोजेक्ट खोलेर **Settings → Domains** → आफ्नो डोमेन (जस्तै `meropasal.com`) लेखेर **Add** थिच्नुहोस्।
3. डोमेन किनेको साइटको **DNS सेटिङ** मा गएर यी २ रेकर्ड राख्नुहोस्:

| Type | Name/Host | Value |
|---|---|---|
| A | @ | `76.76.21.21` |
| CNAME | www | `cname.vercel-dns.com` |

   *(Namecheap: Domain List → Manage → Advanced DNS। GoDaddy: My Products → DNS। Hostinger: Domains → DNS/Nameservers।)*

4. १०–३० मिनेटमा (बढीमा २४ घण्टा) Vercel को Domains पेजमा हरियो ✓ देखिन्छ — तपाईंको डोमेनमा पसल लाइभ! **HTTPS (🔒) Vercel ले आफैं** मिलाइदिन्छ।

> टिप: यी DNS Value हरू तपाईंको साइटको एडमिन → 🌐 डोमेन ट्याबमा पनि "कपी" बटनसहित राखिदिएको छु।

---

## दैनिक चलाउने तरिका

| काम | कसरी |
|---|---|
| 🛒 नयाँ अर्डर हेर्ने | Google Sheet → `Orders` ट्याब (status column मा कन्फर्म/पठाइयो लेख्दै जानुहोस्) |
| ➕ प्रोडक्ट थप्ने/फेर्ने | `Products` ट्याब — फेर्नासाथ साइटमा देखिन्छ, केही deploy गर्नु पर्दैन |
| 🎁 Unit अफर / छुट | `Offers` ट्याब |
| 🚚 डेलिभरी शुल्क | `Shipping` ट्याब |
| ⭐ रिभ्यू | `Reviews` ट्याब |
| 📊 Facebook Pixel | `Config` ट्याबको pixelId |

**`index.html` आफैं फेर्नुपरे:** GitHub मा आफ्नो repo खोल्नुहोस् → `index.html` थिच्नुहोस् → ✏️ (पेन्सिल) थिचेर फेर्नुहोस् → Commit changes → **Vercel ले आफैं नयाँ भर्सन लाइभ गरिदिन्छ** (यही नै Vercel को सबैभन्दा ठूलो फाइदा हो!)

**FB/Insta बुस्ट गर्दा:** ad मा आफ्नै डोमेनको लिंक राख्नुहोस् — Pixel ले Purchase इभेन्ट पठाउने भएकाले Meta ले किन्ने ग्राहक आफैं खोज्दै ad सस्तो बनाउँदै लैजान्छ।

कुनै स्टेपमा अड्किए स्क्रिनसट पठाएर Claude लाई सोध्नुहोस्! 🙌
