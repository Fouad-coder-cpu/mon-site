<!DOCTYPE html>
<html lang="ar" dir="rtl" data-theme="dark">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>استوديو المحتوى الذكي | AI Social Studio Morocco</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Tajawal:wght@400;500;700;800&family=Poppins:wght@400;500;600;700;800&display=swap" rel="stylesheet">
<script src="https://cdn.tailwindcss.com"></script>
<style>
:root{
  box-sizing:border-box;
  padding-top:env(safe-area-inset-top,0px);
  padding-bottom:env(safe-area-inset-bottom,0px);
  --bg:#f5f3ef; --bg-soft:#ffffff; --text:#1a1a1a; --text-soft:#6b675f;
  --border:rgba(0,0,0,.09); --glass:rgba(255,255,255,.55); --shadow:0 10px 30px rgba(0,0,0,.06);
  --red:#c1272d; --green:#016a3b;
}
html{scroll-padding-top:env(safe-area-inset-top,0px)}
@media (prefers-color-scheme: dark){
  :root:not([data-theme="light"]){
    --bg:#0e1013; --bg-soft:#181b21; --text:#f2efe9; --text-soft:#9b978f;
    --border:rgba(255,255,255,.08); --glass:rgba(255,255,255,.045); --shadow:0 10px 30px rgba(0,0,0,.4);
  }
}
:root[data-theme="dark"]{
  --bg:#0e1013; --bg-soft:#181b21; --text:#f2efe9; --text-soft:#9b978f;
  --border:rgba(255,255,255,.08); --glass:rgba(255,255,255,.045); --shadow:0 10px 30px rgba(0,0,0,.4);
}
body{background:var(--bg);color:var(--text);font-family:'Poppins','Tajawal',system-ui,sans-serif;transition:background .3s,color .3s}
html[dir="rtl"] body{font-family:'Tajawal','Poppins',system-ui,sans-serif}
.glass{background:var(--glass);backdrop-filter:blur(16px);-webkit-backdrop-filter:blur(16px);border:1px solid var(--border);box-shadow:var(--shadow)}
.field{background:var(--bg-soft);border:1px solid var(--border);color:var(--text)}
.field::placeholder{color:var(--text-soft)}
header{position:sticky;top:env(safe-area-inset-top,0px);z-index:30}
.morocco-line{height:3px;background:linear-gradient(90deg,var(--red),var(--red) 50%,var(--green) 50%,var(--green))}
.pill{background:linear-gradient(135deg,var(--red),#8f1d22);color:#fff}
.chip{background:var(--bg-soft);border:1px solid var(--border);color:var(--text-soft)}
.lang-btn.active{background:var(--text);color:var(--bg)}
@keyframes fadeUp{from{opacity:0;transform:translateY(10px)}to{opacity:1;transform:translateY(0)}}
.card-in{animation:fadeUp .4s ease both}
@keyframes spin{to{transform:rotate(360deg)}}
.spinner{border:3px solid var(--border);border-top-color:var(--red);border-radius:50%;width:22px;height:22px;animation:spin .8s linear infinite}
::-webkit-scrollbar{width:8px;height:8px}
::-webkit-scrollbar-thumb{background:var(--border);border-radius:8px}
select,textarea,input{outline:none}
select:focus,textarea:focus,input:focus{border-color:var(--red)}
</style>
</head>
<body class="min-h-screen">

<header class="glass">
  <div class="morocco-line"></div>
  <div class="max-w-6xl mx-auto px-4 sm:px-6 py-3 flex items-center justify-between gap-3">
    <div class="flex items-center gap-2">
      <span class="text-2xl">✨</span>
      <div>
        <h1 data-i18n="title" class="font-extrabold text-base sm:text-lg leading-tight"></h1>
        <p data-i18n="subtitle" class="text-[11px] sm:text-xs" style="color:var(--text-soft)"></p>
      </div>
    </div>
    <div class="flex items-center gap-2">
      <div class="flex rounded-full overflow-hidden border" style="border-color:var(--border)">
        <button class="lang-btn px-2.5 py-1 text-xs font-semibold" data-lang="ar">ع</button>
        <button class="lang-btn px-2.5 py-1 text-xs font-semibold" data-lang="fr">FR</button>
        <button class="lang-btn px-2.5 py-1 text-xs font-semibold" data-lang="en">EN</button>
      </div>
      <button id="themeBtn" class="chip w-9 h-9 rounded-full flex items-center justify-center text-base">🌙</button>
    </div>
  </div>
</header>

<main class="max-w-6xl mx-auto px-4 sm:px-6 py-6 grid lg:grid-cols-5 gap-5">

  <section class="lg:col-span-2 glass rounded-2xl p-5 h-fit card-in">
    <h2 data-i18n="formTitle" class="font-bold text-lg mb-4"></h2>
    <div class="space-y-4">
      <div>
        <label data-i18n="bizLabel" class="block text-sm font-semibold mb-1.5"></label>
        <select id="bizSel" class="field w-full rounded-xl px-3 py-2.5 text-sm"></select>
      </div>
      <div>
        <label data-i18n="descLabel" class="block text-sm font-semibold mb-1.5"></label>
        <textarea id="descInput" rows="3" class="field w-full rounded-xl px-3 py-2.5 text-sm resize-none"></textarea>
      </div>
      <div class="grid grid-cols-2 gap-3">
        <div>
          <label data-i18n="toneLabel" class="block text-sm font-semibold mb-1.5"></label>
          <select id="toneSel" class="field w-full rounded-xl px-3 py-2.5 text-sm"></select>
        </div>
        <div>
          <label data-i18n="platformLabel" class="block text-sm font-semibold mb-1.5"></label>
          <select id="platformSel" class="field w-full rounded-xl px-3 py-2.5 text-sm"></select>
        </div>
      </div>
      <div class="grid grid-cols-2 gap-3">
        <div>
          <label data-i18n="outputLangLabel" class="block text-sm font-semibold mb-1.5"></label>
          <select id="outLangSel" class="field w-full rounded-xl px-3 py-2.5 text-sm"></select>
        </div>
        <div id="countWrap">
          <label data-i18n="countLabel" class="block text-sm font-semibold mb-1.5"></label>
          <select id="countSel" class="field w-full rounded-xl px-3 py-2.5 text-sm">
            <option value="3">3</option><option value="5" selected>5</option><option value="7">7</option><option value="10">10</option>
          </select>
        </div>
      </div>
      <label class="flex items-center gap-2 text-sm font-medium cursor-pointer select-none">
        <input type="checkbox" id="calChk" class="w-4 h-4 accent-current" style="accent-color:var(--red)">
        <span data-i18n="calendarLabel"></span>
      </label>
      <button id="genBtn" class="pill w-full rounded-xl py-3 font-bold text-sm flex items-center justify-center gap-2 hover:opacity-90 transition">
        <span id="genIcon">✨</span><span id="genLabel" data-i18n="generateBtn"></span>
      </button>
    </div>
  </section>

  <section class="lg:col-span-3 glass rounded-2xl p-5 card-in">
    <h2 data-i18n="resultsTitle" class="font-bold text-lg mb-4"></h2>
    <div id="results" class="space-y-3">
      <p id="emptyState" data-i18n="emptyState" class="text-sm text-center py-16" style="color:var(--text-soft)"></p>
    </div>
  </section>

</main>

<footer class="max-w-6xl mx-auto px-6 pb-8 pt-2 text-center text-xs" style="color:var(--text-soft)">
  <span data-i18n="footerText"></span>
</footer>

<script>
/* ---------- static reference data ---------- */
const DAY_NAMES={Saturday:{ar:'السبت',fr:'Samedi',en:'Saturday'},Sunday:{ar:'الأحد',fr:'Dimanche',en:'Sunday'},Monday:{ar:'الاثنين',fr:'Lundi',en:'Monday'},Tuesday:{ar:'الثلاثاء',fr:'Mardi',en:'Tuesday'},Wednesday:{ar:'الأربعاء',fr:'Mercredi',en:'Wednesday'},Thursday:{ar:'الخميس',fr:'Jeudi',en:'Thursday'},Friday:{ar:'الجمعة',fr:'Vendredi',en:'Friday'}};
const DAY_ORDER=['Saturday','Sunday','Monday','Tuesday','Wednesday','Thursday','Friday'];
const POST_TYPES=['promo','behind','testimonial','tip','question','offer','culture'];

const BUSINESS_TYPES=[
 {code:'restaurant',ar:'مطعم / مقهى',fr:'Restaurant / Café',en:'restaurant or café'},
 {code:'beauty',ar:'صالون تجميل',fr:'Salon de beauté',en:'beauty salon'},
 {code:'fashion',ar:'متجر ملابس',fr:'Boutique de vêtements',en:'clothing boutique'},
 {code:'realestate',ar:'عقارات',fr:'Immobilier',en:'real estate agency'},
 {code:'photography',ar:'استوديو تصوير',fr:'Studio photo',en:'photography studio'},
 {code:'ecommerce',ar:'متجر إلكتروني',fr:'Boutique en ligne',en:'e-commerce store'},
 {code:'crafts',ar:'حرف تقليدية',fr:'Artisanat traditionnel',en:'traditional Moroccan crafts business'},
 {code:'riad',ar:'رياض / بيت ضيافة',fr:"Riad / Maison d'hôtes",en:'riad or guesthouse'},
 {code:'other',ar:'أخرى',fr:'Autre',en:'local Moroccan business'}
];
const TONES=[
 {code:'professional',ar:'احترافي',fr:'Professionnel',en:'professional'},
 {code:'friendly',ar:'ودود وقريب من الناس',fr:'Amical et proche',en:'friendly and warm'},
 {code:'funny',ar:'فكاهي وخفيف',fr:'Humoristique',en:'humorous and light-hearted'},
 {code:'luxury',ar:'فاخر وراقي',fr:'Luxueux et élégant',en:'luxurious and elegant'}
];
const OUTPUT_LANGS=[
 {code:'darija',ar:'الدارجة المغربية',fr:'Darija marocaine',en:'Moroccan Darija'},
 {code:'msa',ar:'العربية الفصحى',fr:'Arabe classique',en:'Modern Standard Arabic'},
 {code:'fr',ar:'الفرنسية',fr:'Français',en:'French'},
 {code:'en',ar:'الإنجليزية',fr:'Anglais',en:'English'}
];
const PLATFORMS=[
 {code:'instagram',ar:'انستغرام',fr:'Instagram',en:'Instagram'},
 {code:'facebook',ar:'فيسبوك',fr:'Facebook',en:'Facebook'},
 {code:'tiktok',ar:'تيك توك',fr:'TikTok',en:'TikTok'},
 {code:'whatsapp',ar:'واتساب بزنس',fr:'WhatsApp Business',en:'WhatsApp Business'}
];
const I18N={
 ar:{title:'استوديو المحتوى الذكي',subtitle:'محتوى تسويقي ذكي لأصحاب الأعمال المغاربة',formTitle:'أنشئ محتواك',bizLabel:'نوع النشاط التجاري',descLabel:'وصف المنتج أو الخدمة',descPlaceholder:'مثال: نقدم بيتزا مغربية بلمسة عصرية في مراكش، توصيل سريع خلال 30 دقيقة...',toneLabel:'أسلوب الكتابة',platformLabel:'المنصة',outputLangLabel:'لغة النص',countLabel:'عدد الأفكار',calendarLabel:'خطة أسبوعية كاملة (7 أيام)',generateBtn:'أنشئ المحتوى الآن',generatingBtn:'جارِ الإنشاء...',resultsTitle:'النتائج',emptyState:'املأ النموذج واضغط "أنشئ المحتوى الآن" لتظهر أفكارك هنا',copyBtn:'نسخ',copiedBtn:'تم النسخ ✓',ctaLabel:'دعوة للعمل',footerText:'صُمم خصيصاً لأصحاب الأعمال في المغرب 🇲🇦'},
 fr:{title:'Studio de Contenu IA',subtitle:'Contenu marketing intelligent pour les entrepreneurs marocains',formTitle:'Créez votre contenu',bizLabel:"Type d'activité",descLabel:'Description du produit ou service',descPlaceholder:'Ex : Nous proposons une pizza marocaine revisitée à Marrakech, livraison en 30 minutes...',toneLabel:'Ton de rédaction',platformLabel:'Plateforme',outputLangLabel:'Langue du texte',countLabel:"Nombre d'idées",calendarLabel:'Plan hebdomadaire complet (7 jours)',generateBtn:'Générer le contenu',generatingBtn:'Génération...',resultsTitle:'Résultats',emptyState:'Remplissez le formulaire et cliquez sur "Générer le contenu"',copyBtn:'Copier',copiedBtn:'Copié ✓',ctaLabel:"Appel à l'action",footerText:'Conçu pour les entrepreneurs au Maroc 🇲🇦'},
 en:{title:'AI Content Studio',subtitle:'Smart marketing content for Moroccan business owners',formTitle:'Create your content',bizLabel:'Business type',descLabel:'Product or service description',descPlaceholder:'e.g. We serve modern Moroccan-style pizza in Marrakech, 30-minute delivery...',toneLabel:'Tone of voice',platformLabel:'Platform',outputLangLabel:'Content language',countLabel:'Number of ideas',calendarLabel:'Full weekly plan (7 days)',generateBtn:'Generate content',generatingBtn:'Generating...',resultsTitle:'Results',emptyState:'Fill the form and click "Generate content" to see your ideas here',copyBtn:'Copy',copiedBtn:'Copied ✓',ctaLabel:'Call to action',footerText:'Built for business owners in Morocco 🇲🇦'}
};

/* ---------- content-generation template banks ---------- */
const DEFAULT_DESC={darija:'المنتوج ديالنا المميز اللي غادي يعجبكم',msa:'منتجنا المميز الذي سيعجبكم',fr:'notre produit unique qui va vous plaire',en:"our unique product you'll love"};

const HOOKS={
 professional:{darija:['فـ {biz} ديالنا، الجودة هي لي كتفرقنا 💼','كل يوم كنخدمو باش نعطيوكم الأحسن فـ {biz} 🌿'],
  msa:['في {biz}، الجودة هي ما يميزنا 💼','نسعى كل يوم لتقديم الأفضل لكم في {biz} 🌿'],
  fr:['Chez {biz}, la qualité fait toute la différence 💼','Chaque jour, nous travaillons pour vous offrir le meilleur 🌿'],
  en:['At {biz}, quality is what sets us apart 💼','Every day, we work to bring you the best 🌿']},
 friendly:{darija:['أهلا بيكم فـ {biz} ديالنا 🤗','واش جربتو {biz} ديالنا؟ غادي تعجبكم بزاف 😍'],
  msa:['أهلاً بكم في {biz} 🤗','هل جربتم {biz}؟ ستعجبكم كثيراً 😍'],
  fr:['Bienvenue chez {biz} 🤗',"Vous n'avez pas encore essayé {biz} ? Vous allez adorer 😍"],
  en:['Welcome to {biz} 🤗',"Haven't tried {biz} yet? You're in for a treat 😍"]},
 funny:{darija:['واخا نقولها؟ {biz} غادي يبدل حياتكم 😂✨','ماشي كنبالغو، ولكن {biz} ديالنا top 🔥😜'],
  msa:['لنكن صريحين، {biz} سيغيّر يومكم 😂✨','لا نبالغ، لكن {biz} فعلاً رائع 🔥😜'],
  fr:["On ne va pas mentir, {biz} va changer votre journée 😂✨","On n'exagère pas, mais {biz} est juste top 🔥😜"],
  en:['Not to be dramatic, but {biz} might just change your day 😂✨',"We don't want to brag, but {biz} is kind of amazing 🔥😜"]},
 luxury:{darija:['تجربة فاخرة كتستناكم فـ {biz} ✨👑','{biz}... فين الأناقة كتلتقي بالجودة 💎'],
  msa:['تجربة راقية تنتظركم في {biz} ✨👑','{biz}... حيث تلتقي الأناقة بالجودة 💎'],
  fr:['Une expérience haut de gamme vous attend chez {biz} ✨👑',"{biz}... où l'élégance rencontre la qualité 💎"],
  en:['An elevated experience awaits at {biz} ✨👑','{biz}... where elegance meets quality 💎']}
};
const CONNECTORS={
 promo:{darija:'هاذي فرصة ماشي غادي تتكرر: {desc} 🎯',msa:'هذه فرصة لا تعوض: {desc} 🎯',fr:'Une occasion à ne pas manquer : {desc} 🎯',en:"This is one you don't want to miss: {desc} 🎯"},
 behind:{darija:'من وراء الكواليس... {desc} 👀',msa:'من كواليس العمل... {desc} 👀',fr:'Dans les coulisses... {desc} 👀',en:'Behind the scenes... {desc} 👀'},
 testimonial:{darija:'الزبناء ديالنا كيقولو: {desc} 💬',msa:'عملاؤنا يقولون: {desc} 💬',fr:'Nos clients en parlent : {desc} 💬',en:'Our customers are talking: {desc} 💬'},
 tip:{darija:'نصيحة اليوم بخصوص: {desc} 💡',msa:'نصيحة اليوم: {desc} 💡',fr:'Astuce du jour : {desc} 💡',en:"Today's tip: {desc} 💡"},
 question:{darija:'شنو رأيكم فـ: {desc}؟ قولو لينا فالكومنت ✍️',msa:'ما رأيكم في: {desc}؟ أخبرونا في التعليقات ✍️',fr:'Qu\'en pensez-vous : {desc} ? Dites-le-nous en commentaire ✍️',en:'What do you think about: {desc}? Tell us in the comments ✍️'},
 offer:{darija:'عرض خاص هاد الأسبوع: {desc} ⏰',msa:'عرض خاص هذا الأسبوع: {desc} ⏰',fr:'Offre spéciale cette semaine : {desc} ⏰',en:'Special offer this week: {desc} ⏰'},
 culture:{darija:'من قلب المغرب لعندكم: {desc} 🇲🇦',msa:'من قلب المغرب إليكم: {desc} 🇲🇦',fr:'Du cœur du Maroc jusqu\'à vous : {desc} 🇲🇦',en:'Straight from the heart of Morocco: {desc} 🇲🇦'}
};
const CTA_OPENER={
 professional:{darija:'تواصلو معانا:',msa:'تواصلوا معنا:',fr:'Contactez-nous :',en:'Get in touch:'},
 friendly:{darija:'راكم فالانتظار، تعالو:',msa:'ننتظركم، تعالوا:',fr:'On vous attend, venez :',en:"We can't wait to see you:"},
 funny:{darija:'يالله متبطيوش 😜',msa:'هيا لا تترددوا 😜',fr:"Alors, on n'attend plus 😜",en:'So... what are you waiting for 😜'},
 luxury:{darija:'تفضلو باش تعيشو التجربة:',msa:'تفضلوا لعيش التجربة:',fr:"Offrez-vous l'expérience :",en:'Treat yourself to the experience:'}
};
const PLATFORM_ACTION={
 instagram:{darija:'تابعونا هنا 📸',msa:'تابعونا على حسابنا 📸',fr:'Suivez-nous ici 📸',en:'Follow us here 📸'},
 facebook:{darija:'زورو صفحتنا فالفيسبوك 👍',msa:'زوروا صفحتنا على فيسبوك 👍',fr:'Visitez notre page Facebook 👍',en:'Check out our Facebook page 👍'},
 tiktok:{darija:'شوفو الفيديو ديالنا فتيك توك 🎥',msa:'شاهدوا فيديوهاتنا على تيك توك 🎥',fr:'Regardez notre TikTok 🎥',en:'Watch us on TikTok 🎥'},
 whatsapp:{darija:'صيفطو رسالة فالواتساب باش تطلبو 📲',msa:'راسلونا عبر واتساب للطلب 📲',fr:'Contactez-nous sur WhatsApp pour commander 📲',en:'Message us on WhatsApp to order 📲'}
};
const GENERIC_TAGS=['#المغرب','#Maroc','#MoroccoBusiness','#صنع_في_المغرب','#دعم_المنتوج_المحلي','#مغربي','#Marrakech','#Casablanca','#Rabat','#تسوق_مغربي','#MadeInMorocco','#تجارة_مغربية'];
const BUSINESS_TAGS={
 restaurant:['#مطعم_مغربي','#أكل_بيتي','#Foodie','#مطبخ_مغربي'],
 beauty:['#صالون_تجميل','#عناية_بالبشرة','#Beauty','#مكياج'],
 fashion:['#موضة_مغربية','#ملابس','#Fashion','#ستايل'],
 realestate:['#عقارات_المغرب','#شقق_للبيع','#RealEstate','#استثمار_عقاري'],
 photography:['#تصوير_فوتوغرافي','#استوديو_تصوير','#Photography','#لقطة'],
 ecommerce:['#تسوق_أونلاين','#توصيل_سريع','#Ecommerce','#عروض'],
 crafts:['#حرف_يدوية','#صناعة_تقليدية','#Handmade','#تراث_مغربي'],
 riad:['#رياض','#سياحة_مغربية','#Travel','#ضيافة_مغربية'],
 other:['#مشروع_مغربي','#عمل_حر','#SmallBusiness','#تجارة']
};

/* ---------- state & i18n helpers ---------- */
let uiLang='ar', theme='dark', busy=false;
const $=id=>document.getElementById(id);

function applyI18n(){
  const t=I18N[uiLang];
  document.querySelectorAll('[data-i18n]').forEach(el=>el.textContent=t[el.dataset.i18n]||'');
  $('descInput').placeholder=t.descPlaceholder;
  document.documentElement.dir = uiLang==='ar' ? 'rtl':'ltr';
  document.documentElement.lang = uiLang;
  document.querySelectorAll('.lang-btn').forEach(b=>b.classList.toggle('active',b.dataset.lang===uiLang));
}
function fillSelect(sel,arr){
  const cur=sel.value;
  sel.innerHTML=arr.map(o=>`<option value="${o.code}">${o[uiLang]||o.en}</option>`).join('');
  if(cur && arr.some(o=>o.code===cur)) sel.value=cur;
}
function refreshSelects(){
  fillSelect($('bizSel'),BUSINESS_TYPES);
  fillSelect($('toneSel'),TONES);
  fillSelect($('outLangSel'),OUTPUT_LANGS);
  fillSelect($('platformSel'),PLATFORMS);
}
function setLang(l){ uiLang=l; applyI18n(); refreshSelects(); try{localStorage.setItem('acs_lang',l)}catch(e){} }
function setTheme(t){ theme=t; document.documentElement.setAttribute('data-theme',t); $('themeBtn').textContent = t==='dark'?'🌙':'☀️'; try{localStorage.setItem('acs_theme',t)}catch(e){} }

document.querySelectorAll('.lang-btn').forEach(b=>b.addEventListener('click',()=>setLang(b.dataset.lang)));
$('themeBtn').addEventListener('click',()=>setTheme(theme==='dark'?'light':'dark'));
$('calChk').addEventListener('change',()=>{ $('countWrap').style.display = $('calChk').checked ? 'none':'block'; });

/* ---------- content engine ---------- */
function pickTags(bizCode){
  const pool=[...(BUSINESS_TAGS[bizCode]||BUSINESS_TAGS.other),...GENERIC_TAGS];
  for(let i=pool.length-1;i>0;i--){ const j=Math.floor(Math.random()*(i+1)); [pool[i],pool[j]]=[pool[j],pool[i]]; }
  return pool.slice(0,6);
}
function craftContent(v){
  const bizObj=BUSINESS_TYPES.find(o=>o.code===v.biz);
  const bizText = v.lang==='fr' ? bizObj.fr : v.lang==='en' ? bizObj.en : bizObj.ar;
  const desc = v.desc || DEFAULT_DESC[v.lang];
  const n = v.calendar ? 7 : v.count;
  const out=[];
  for(let i=0;i<n;i++){
    const pt = POST_TYPES[i % POST_TYPES.length];
    const hookArr = HOOKS[v.tone][v.lang];
    const hook = hookArr[Math.floor(Math.random()*hookArr.length)].replace('{biz}', bizText);
    const connector = CONNECTORS[pt][v.lang].replace('{desc}', desc);
    const cta = CTA_OPENER[v.tone][v.lang] + ' ' + PLATFORM_ACTION[v.platform][v.lang];
    const item = { caption: hook+'\n\n'+connector, hashtags: pickTags(v.biz), cta };
    if(v.calendar) item.day = DAY_ORDER[i];
    out.push(item);
  }
  return out;
}
function renderResults(items,calendar){
  const t=I18N[uiLang], wrap=$('results');
  wrap.innerHTML='';
  items.forEach((it,i)=>{
    const day = calendar && it.day && DAY_NAMES[it.day] ? DAY_NAMES[it.day][uiLang] : null;
    const card=document.createElement('div');
    card.className='field rounded-xl p-4 card-in';
    card.style.animationDelay=(i*0.05)+'s';
    card.innerHTML=`
      ${day?`<span class="pill inline-block text-[11px] font-bold rounded-full px-2.5 py-0.5 mb-2">${day}</span>`:''}
      <p class="text-sm leading-relaxed whitespace-pre-wrap mb-2">${(it.caption||'').replace(/</g,'&lt;')}</p>
      <div class="flex flex-wrap gap-1.5 mb-2">${(it.hashtags||[]).map(h=>`<span class="chip text-[11px] rounded-full px-2 py-0.5">${h.replace(/</g,'&lt;')}</span>`).join('')}</div>
      ${it.cta?`<p class="text-xs font-semibold" style="color:var(--text-soft)">${t.ctaLabel}: <span style="color:var(--text)">${it.cta.replace(/</g,'&lt;')}</span></p>`:''}
      <button class="copy-btn mt-3 text-xs font-bold chip rounded-lg px-3 py-1.5 hover:opacity-80">${t.copyBtn}</button>`;
    card.querySelector('.copy-btn').addEventListener('click',async e=>{
      const full=[it.caption,(it.hashtags||[]).join(' '),it.cta].filter(Boolean).join('\n\n');
      try{ await navigator.clipboard.writeText(full); e.target.textContent=t.copiedBtn; setTimeout(()=>e.target.textContent=t.copyBtn,1500); }
      catch(err){
        const ta=document.createElement('textarea'); ta.value=full; document.body.appendChild(ta); ta.select();
        try{ document.execCommand('copy'); e.target.textContent=t.copiedBtn; setTimeout(()=>e.target.textContent=t.copyBtn,1500); }catch(e2){}
        document.body.removeChild(ta);
      }
    });
    wrap.appendChild(card);
  });
}
function generate(){
  if(busy) return;
  const t=I18N[uiLang];
  const v={ biz:$('bizSel').value, desc:$('descInput').value.trim(), tone:$('toneSel').value,
    platform:$('platformSel').value, lang:$('outLangSel').value, count:parseInt($('countSel').value,10),
    calendar:$('calChk').checked };
  busy=true; $('genBtn').disabled=true;
  $('genIcon').innerHTML='<span class="spinner inline-block align-middle"></span>'; $('genLabel').textContent=t.generatingBtn;
  $('results').innerHTML=`<div class="flex justify-center py-16"><span class="spinner"></span></div>`;
  setTimeout(()=>{
    try{ renderResults(craftContent(v), v.calendar); }
    finally{ busy=false; $('genBtn').disabled=false; $('genIcon').textContent='✨'; $('genLabel').textContent=t.generateBtn; }
  }, 600+Math.random()*500);
}
$('genBtn').addEventListener('click',generate);

(function init(){
  try{ const sl=localStorage.getItem('acs_lang'); if(sl) uiLang=sl; const st=localStorage.getItem('acs_theme'); if(st) theme=st; }catch(e){}
  setTheme(theme); applyI18n(); refreshSelects();
})();
</script>
</body>
</html>
