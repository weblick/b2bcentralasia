/* b2bcentralasia — общий код для всех страниц (дни 2–4) */
(function () {
  "use strict";

  // ---------- ПЕРЕВОДЫ ИНТЕРФЕЙСА ----------
  var T = {
    ru: {
      nav_catalog: "Каталог", nav_countries: "Страны", nav_how: "Как это работает", nav_join: "Стать поставщиком",
      hero_badge: "B2B-платформа Центральной Азии",
      hero_title: "Поставщики и производители <span>пяти стран</span> в одном месте",
      hero_sub: "Казахстан, Кыргызстан, Таджикистан, Туркменистан и Узбекистан. Находите проверенных партнёров и связывайтесь с ними напрямую.",
      search_ph: "Что ищете? Например: цемент, хлопок, упаковка", search_btn: "Найти",
      stat_countries: "стран", stat_cats: "отраслей", stat_sup: "поставщиков", stat_ver: "проверенных",
      sec_countries: "Страны", sec_countries_sub: "Выберите страну, чтобы увидеть её поставщиков",
      sec_cats: "Отрасли", sec_cats_sub: "Основные направления торговли в регионе",
      sec_feat: "Проверенные поставщики", sec_feat_sub: "Компании, прошедшие проверку платформы", see_all: "Весь каталог →",
      sec_how: "Как это работает",
      how1_t: "Найдите", how1_d: "Ищите по названию, товару, стране и отрасли.",
      how2_t: "Сравните", how2_d: "Смотрите профиль, отметку о проверке и контакты компании.",
      how3_t: "Свяжитесь", how3_d: "Пишите в Telegram, WhatsApp или звоните напрямую, без посредников.",
      cta_t: "Вы производитель или поставщик?", cta_d: "Разместите компанию в каталоге и получайте заявки со всего региона.", cta_btn: "Оставить заявку",
      footer_rights: "Все права защищены.",
      cat_title: "Каталог поставщиков", f_country: "Страна", f_cat: "Отрасль", f_all_c: "Все страны", f_all_cat: "Все отрасли",
      f_verified: "Только проверенные", f_reset: "Сбросить", found: "Найдено", nothing: "Ничего не нашлось. Попробуйте другой запрос или сбросьте фильтры.",
      verified: "Проверен", more: "Подробнее", loading: "Загрузка…",
      sp_contacts: "Контакты", sp_about: "О компании", sp_call: "Позвонить", sp_tg: "Telegram", sp_wa: "WhatsApp",
      sp_mail: "E-mail", sp_ig: "Instagram", sp_web: "Сайт", sp_similar: "Похожие поставщики", sp_back: "← Назад в каталог",
      sp_notfound: "Поставщик не найден или скрыт.", sp_nodesc: "Описание пока не добавлено.", sp_country: "Страна", sp_city: "Город", sp_cat: "Отрасль",
      demo: "Демо-режим: показаны тестовые данные", test_tag: "тест"
    },
    en: {
      nav_catalog: "Catalog", nav_countries: "Countries", nav_how: "How it works", nav_join: "Become a supplier",
      hero_badge: "Central Asia B2B platform",
      hero_title: "Suppliers and manufacturers of <span>five countries</span> in one place",
      hero_sub: "Kazakhstan, Kyrgyzstan, Tajikistan, Turkmenistan and Uzbekistan. Find trusted partners and contact them directly.",
      search_ph: "What are you looking for? e.g. cement, cotton, packaging", search_btn: "Search",
      stat_countries: "countries", stat_cats: "industries", stat_sup: "suppliers", stat_ver: "verified",
      sec_countries: "Countries", sec_countries_sub: "Pick a country to see its suppliers",
      sec_cats: "Industries", sec_cats_sub: "Key trade sectors of the region",
      sec_feat: "Verified suppliers", sec_feat_sub: "Companies checked by the platform", see_all: "Full catalog →",
      sec_how: "How it works",
      how1_t: "Find", how1_d: "Search by name, product, country and industry.",
      how2_t: "Compare", how2_d: "Check the profile, verification badge and contacts.",
      how3_t: "Connect", how3_d: "Message on Telegram, WhatsApp or call directly, no middlemen.",
      cta_t: "Are you a manufacturer or supplier?", cta_d: "List your company and receive requests from across the region.", cta_btn: "Apply",
      footer_rights: "All rights reserved.",
      cat_title: "Supplier catalog", f_country: "Country", f_cat: "Industry", f_all_c: "All countries", f_all_cat: "All industries",
      f_verified: "Verified only", f_reset: "Reset", found: "Found", nothing: "Nothing found. Try another query or reset filters.",
      verified: "Verified", more: "Details", loading: "Loading…",
      sp_contacts: "Contacts", sp_about: "About", sp_call: "Call", sp_tg: "Telegram", sp_wa: "WhatsApp",
      sp_mail: "E-mail", sp_ig: "Instagram", sp_web: "Website", sp_similar: "Similar suppliers", sp_back: "← Back to catalog",
      sp_notfound: "Supplier not found or hidden.", sp_nodesc: "No description yet.", sp_country: "Country", sp_city: "City", sp_cat: "Industry",
      demo: "Demo mode: showing test data", test_tag: "test"
    },
    zh: {
      nav_catalog: "目录", nav_countries: "国家", nav_how: "使用方式", nav_join: "成为供应商",
      hero_badge: "中亚B2B平台",
      hero_title: "<span>中亚五国</span>的供应商与制造商汇聚一处",
      hero_sub: "哈萨克斯坦、吉尔吉斯斯坦、塔吉克斯坦、土库曼斯坦和乌兹别克斯坦。寻找可靠伙伴，直接联系。",
      search_ph: "您在找什么？例如：水泥、棉花、包装", search_btn: "搜索",
      stat_countries: "个国家", stat_cats: "个行业", stat_sup: "家供应商", stat_ver: "家已认证",
      sec_countries: "国家", sec_countries_sub: "选择国家查看其供应商",
      sec_cats: "行业", sec_cats_sub: "本地区主要贸易领域",
      sec_feat: "认证供应商", sec_feat_sub: "经过平台审核的企业", see_all: "查看完整目录 →",
      sec_how: "使用方式",
      how1_t: "查找", how1_d: "按名称、产品、国家和行业搜索。",
      how2_t: "比较", how2_d: "查看企业资料、认证标志和联系方式。",
      how3_t: "联系", how3_d: "通过Telegram、WhatsApp或电话直接联系，无中间商。",
      cta_t: "您是制造商或供应商吗？", cta_d: "将您的企业加入目录，接收来自整个地区的询价。", cta_btn: "提交申请",
      footer_rights: "版权所有。",
      cat_title: "供应商目录", f_country: "国家", f_cat: "行业", f_all_c: "所有国家", f_all_cat: "所有行业",
      f_verified: "仅认证", f_reset: "重置", found: "找到", nothing: "未找到结果。请尝试其他关键词或重置筛选。",
      verified: "已认证", more: "详情", loading: "加载中…",
      sp_contacts: "联系方式", sp_about: "公司简介", sp_call: "致电", sp_tg: "Telegram", sp_wa: "WhatsApp",
      sp_mail: "邮箱", sp_ig: "Instagram", sp_web: "网站", sp_similar: "类似供应商", sp_back: "← 返回目录",
      sp_notfound: "未找到该供应商或已隐藏。", sp_nodesc: "暂无简介。", sp_country: "国家", sp_city: "城市", sp_cat: "行业",
      demo: "演示模式：显示测试数据", test_tag: "测试"
    }
  };

  // ---------- ЦВЕТА СТРАН (полоса на карточках) ----------
  var COUNTRY_COLOR = { KZ: "#00a7c8", KG: "#e8112d", TJ: "#1e8f3a", TM: "#2fae66", UZ: "#1e88c8" };
  var COUNTRY_FLAG = { KZ: "🇰🇿", KG: "🇰🇬", TJ: "🇹🇯", TM: "🇹🇲", UZ: "🇺🇿" };

  // ---------- ТЕСТОВЫЕ ДАННЫЕ (как в базе после дня 1) ----------
  var DEMO = {
    countries: [
      { code: "KZ", name: { ru: "Казахстан", en: "Kazakhstan", zh: "哈萨克斯坦" }, sort: 1 },
      { code: "KG", name: { ru: "Кыргызстан", en: "Kyrgyzstan", zh: "吉尔吉斯斯坦" }, sort: 2 },
      { code: "TJ", name: { ru: "Таджикистан", en: "Tajikistan", zh: "塔吉克斯坦" }, sort: 3 },
      { code: "TM", name: { ru: "Туркменистан", en: "Turkmenistan", zh: "土库曼斯坦" }, sort: 4 },
      { code: "UZ", name: { ru: "Узбекистан", en: "Uzbekistan", zh: "乌兹别克斯坦" }, sort: 5 }
    ],
    categories: [
      { id: 1, slug: "construction", icon: "🧱", sort: 1, name: { ru: "Строительные материалы", en: "Construction materials", zh: "建筑材料" } },
      { id: 2, slug: "food", icon: "🍞", sort: 2, name: { ru: "Продукты питания", en: "Food products", zh: "食品" } },
      { id: 3, slug: "textile", icon: "🧵", sort: 3, name: { ru: "Текстиль и одежда", en: "Textiles & apparel", zh: "纺织品和服装" } },
      { id: 4, slug: "agriculture", icon: "🌾", sort: 4, name: { ru: "Сельское хозяйство", en: "Agriculture", zh: "农业" } },
      { id: 5, slug: "packaging", icon: "📦", sort: 5, name: { ru: "Упаковка", en: "Packaging", zh: "包装" } },
      { id: 6, slug: "metals", icon: "🔩", sort: 6, name: { ru: "Металлы и металлопрокат", en: "Metals & metal products", zh: "金属及金属制品" } },
      { id: 7, slug: "chemicals", icon: "🧪", sort: 7, name: { ru: "Химия и пластик", en: "Chemicals & plastics", zh: "化工和塑料" } },
      { id: 8, slug: "machinery", icon: "⚙️", sort: 8, name: { ru: "Оборудование и станки", en: "Machinery & equipment", zh: "机械设备" } },
      { id: 9, slug: "logistics", icon: "🚚", sort: 9, name: { ru: "Логистика и перевозки", en: "Logistics", zh: "物流" } },
      { id: 10, slug: "furniture", icon: "🪑", sort: 10, name: { ru: "Мебель", en: "Furniture", zh: "家具" } }
    ],
    suppliers: [
      ["toshkent-qurilish", "Toshkent Qurilish Savdo", "UZ", "Ташкент", 1, "Цемент, кирпич и сухие смеси оптом.", "Cement, bricks and dry mixes wholesale.", true],
      ["samarqand-tekstil", "Samarqand Tekstil Group", "UZ", "Самарканд", 3, "Хлопковая пряжа и ткани.", "Cotton yarn and fabrics.", true],
      ["fergana-agro", "Fergana Agro Export", "UZ", "Фергана", 4, "Свежие фрукты и сухофрукты на экспорт.", "Fresh and dried fruits for export.", false],
      ["almaty-pack", "Almaty Pack", "KZ", "Алматы", 5, "Гофрокороба и плёнка.", "Corrugated boxes and film.", true],
      ["steppe-metal", "Steppe Metal Trade", "KZ", "Караганда", 6, "Арматура, трубы, листовой металл.", "Rebar, pipes, sheet metal.", false],
      ["astana-food", "Astana Food Supply", "KZ", "Астана", 2, "Мука, крупы, масло.", "Flour, grains, oil.", true],
      ["bishkek-furniture", "Bishkek Furniture Factory", "KG", "Бишкек", 10, "Офисная и корпусная мебель.", "Office and cabinet furniture.", false],
      ["osh-dried-fruits", "Osh Dried Fruits", "KG", "Ош", 2, "Орехи и сухофрукты.", "Nuts and dried fruits.", true],
      ["issyk-kul-textile", "Issyk-Kul Textile", "KG", "Каракол", 3, "Шерсть и войлочные изделия.", "Wool and felt products.", false],
      ["dushanbe-alu", "Dushanbe Aluminium Trade", "TJ", "Душанбе", 6, "Алюминиевый профиль и прокат.", "Aluminium profiles and rolled products.", true],
      ["khujand-silk", "Khujand Silk", "TJ", "Худжанд", 3, "Шёлк и шёлковые ткани.", "Silk and silk fabrics.", false],
      ["pamir-logistics", "Pamir Logistics", "TJ", "Душанбе", 9, "Грузоперевозки по Центральной Азии.", "Freight across Central Asia.", true],
      ["ashgabat-chem", "Ashgabat Chemical", "TM", "Ашхабад", 7, "Полиэтилен и полипропилен.", "Polyethylene and polypropylene.", true],
      ["turkmen-machinery", "Turkmen Machinery", "TM", "Туркменабат", 8, "Промышленное оборудование и запчасти.", "Industrial equipment and spare parts.", false],
      ["mary-cotton", "Mary Cotton Trade", "TM", "Мары", 4, "Хлопок-сырец.", "Raw cotton.", false]
    ].map(function (r, i) {
      return {
        slug: r[0], name: r[1], country_code: r[2], city: r[3], category_id: r[4],
        description: { ru: "Тестовая компания. " + r[5], en: "Test company. " + r[6] },
        phone: "+998 00 000 00 " + String(i + 1).padStart(2, "0"), email: "test" + (i + 1) + "@example.com",
        telegram: null, whatsapp: null, instagram: null, website: null, logo_url: null,
        is_verified: r[7], status: "approved", is_test: true
      };
    })
  };

  // ---------- УТИЛИТЫ ----------
  var $ = function (s, el) { return (el || document).querySelector(s); };
  function esc(s) {
    return String(s == null ? "" : s).replace(/[&<>"']/g, function (c) {
      return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c];
    });
  }
  function safeUrl(u) { u = String(u || "").trim(); return /^https?:\/\//i.test(u) ? u : ""; }
  function params() { return new URLSearchParams(location.search); }

  var LANGS = ["ru", "en", "zh"];
  var lang = (function () {
    var p = params().get("lang");
    var s = null; try { s = localStorage.getItem("lang"); } catch (e) {}
    var l = p || s || (window.CONFIG && CONFIG.defaultLang) || "ru";
    return LANGS.indexOf(l) >= 0 ? l : "ru";
  })();
  function t(k) { return (T[lang] && T[lang][k]) || T.ru[k] || k; }
  function tr(obj) { // перевод jsonb-поля: нужный язык → ru → en → первое
    if (!obj) return "";
    if (typeof obj === "string") return obj;
    return obj[lang] || obj.ru || obj.en || Object.values(obj)[0] || "";
  }

  // ---------- ДАННЫЕ (Supabase или демо) ----------
  var HAS_DB = !!(window.CONFIG && CONFIG.SUPABASE_URL && CONFIG.SUPABASE_KEY);
  function api(path) {
    var base = CONFIG.SUPABASE_URL.replace(/\/+$/, "");
    return fetch(base + "/rest/v1/" + path, { headers: { apikey: CONFIG.SUPABASE_KEY, Accept: "application/json" } })
      .then(function (r) { if (!r.ok) throw new Error("HTTP " + r.status); return r.json(); });
  }
  var cache = null;
  function loadAll() {
    if (cache) return cache;
    if (!HAS_DB) { cache = Promise.resolve(DEMO); return cache; }
    cache = Promise.all([
      api("countries?select=code,name,sort&order=sort"),
      api("categories?select=id,slug,name,icon,sort&order=sort"),
      api("suppliers?select=slug,name,country_code,city,category_id,description,logo_url,phone,email,telegram,whatsapp,instagram,website,is_verified,is_test&status=eq.approved&order=is_verified.desc,name&limit=1000")
    ]).then(function (r) { return { countries: r[0], categories: r[1], suppliers: r[2] }; })
      .catch(function (e) {
        console.error("Supabase error:", e);
        HAS_DB = false; return DEMO;
      });
    return cache;
  }

  // ---------- ОБЩИЕ ЧАСТИ: шапка, подвал, язык ----------
  var LOGO_SVG = '<svg viewBox="0 0 40 40" aria-hidden="true"><g fill="none" stroke="currentColor" stroke-width="2"><path d="M20 3l4.9 7.3 8.6-1.8-1.8 8.6L39 20l-7.3 4.9 1.8 8.6-8.6-1.8L20 37l-4.9-7.3-8.6 1.8 1.8-8.6L1 20l7.3-4.9-1.8-8.6 8.6 1.8z"/><circle cx="20" cy="20" r="6.5"/></g></svg>';

  function renderChrome(page) {
    var head = $("#site-header");
    if (head) {
      head.innerHTML =
        '<div class="wrap head-row">' +
          '<a class="logo" href="index.html">' + LOGO_SVG + '<span>B2B <b>Central Asia</b></span></a>' +
          '<nav class="nav" id="nav">' +
            '<a href="catalog.html"' + (page === "catalog" ? ' class="on"' : "") + '>' + t("nav_catalog") + '</a>' +
            '<a href="index.html#countries">' + t("nav_countries") + '</a>' +
            '<a href="index.html#how">' + t("nav_how") + '</a>' +
            '<a class="nav-join" href="index.html#join">' + t("nav_join") + '</a>' +
          '</nav>' +
          '<div class="langs" role="group" aria-label="Language">' +
            LANGS.map(function (l) { return '<button data-lang="' + l + '"' + (l === lang ? ' class="on"' : "") + '>' + (l === "zh" ? "中文" : l.toUpperCase()) + '</button>'; }).join("") +
          '</div>' +
          '<button class="burger" id="burger" aria-label="Menu"><i></i><i></i><i></i></button>' +
        '</div>';
      head.querySelectorAll("[data-lang]").forEach(function (b) {
        b.onclick = function () {
          try { localStorage.setItem("lang", b.dataset.lang); } catch (e) {}
          var p = params(); p.delete("lang");
          var qs = p.toString();
          location.href = location.pathname + (qs ? "?" + qs : "") + location.hash;
        };
      });
      $("#burger").onclick = function () { document.body.classList.toggle("menu-open"); };
      $("#nav").onclick = function (e) { if (e.target.tagName === "A") document.body.classList.remove("menu-open"); };
    }
    var foot = $("#site-footer");
    if (foot) {
      foot.innerHTML =
        '<div class="orn-line"></div>' +
        '<div class="wrap foot-row">' +
          '<a class="logo" href="index.html">' + LOGO_SVG + '<span>B2B <b>Central Asia</b></span></a>' +
          '<div class="flags">' + ["KZ", "KG", "TJ", "TM", "UZ"].map(function (c) { return '<span style="--c:' + COUNTRY_COLOR[c] + '"></span>'; }).join("") + '</div>' +
          '<p>© ' + new Date().getFullYear() + ' b2bcentralasia. ' + t("footer_rights") + '</p>' +
        '</div>';
    }
    document.documentElement.lang = lang === "zh" ? "zh-CN" : lang;
    document.querySelectorAll("[data-t]").forEach(function (el) { el.innerHTML = t(el.dataset.t); });
    document.querySelectorAll("[data-tph]").forEach(function (el) { el.placeholder = t(el.dataset.tph); });
  }

  function demoNotice() {
    if (HAS_DB) return;
    var n = document.createElement("div");
    n.className = "demo-note"; n.textContent = t("demo");
    var h = document.getElementById("site-header"); h.parentNode.insertBefore(n, h.nextSibling);
  }

  // ---------- КАРТОЧКА ПОСТАВЩИКА ----------
  function initials(name) {
    return String(name || "?").split(/\s+/).filter(Boolean).slice(0, 2).map(function (w) { return w[0]; }).join("").toUpperCase();
  }
  function logoHtml(s, big) {
    var u = safeUrl(s.logo_url);
    var cls = big ? "s-logo big" : "s-logo";
    if (u) return '<div class="' + cls + '"><img src="' + esc(u) + '" alt="" loading="lazy"></div>';
    return '<div class="' + cls + '" style="--c:' + (COUNTRY_COLOR[s.country_code] || "#c9a24a") + '">' + esc(initials(s.name)) + '</div>';
  }
  function maps(data) {
    var c = {}, k = {};
    data.countries.forEach(function (x) { c[x.code] = x; });
    data.categories.forEach(function (x) { k[x.id] = x; });
    return { c: c, k: k };
  }
  function card(s, m) {
    var cat = m.k[s.category_id], ctry = m.c[s.country_code];
    return '<a class="s-card" href="supplier.html?s=' + encodeURIComponent(s.slug) + '" style="--c:' + (COUNTRY_COLOR[s.country_code] || "#c9a24a") + '">' +
      '<div class="s-top">' + logoHtml(s) +
        '<div class="s-meta"><h3>' + esc(s.name) + '</h3>' +
        '<div class="s-loc">' + (COUNTRY_FLAG[s.country_code] || "") + ' ' + esc(ctry ? tr(ctry.name) : s.country_code) + (s.city ? " · " + esc(s.city) : "") + '</div></div>' +
      '</div>' +
      '<p class="s-desc">' + esc(tr(s.description)) + '</p>' +
      '<div class="s-foot">' +
        (cat ? '<span class="chip">' + esc(cat.icon || "") + ' ' + esc(tr(cat.name)) + '</span>' : "") +
        (s.is_verified ? '<span class="ver">✓ ' + t("verified") + '</span>' : "") +
        (s.is_test ? '<span class="test">' + t("test_tag") + '</span>' : "") +
      '</div></a>';
  }

  // ========== ДЕНЬ 2: ГЛАВНАЯ ==========
  function pageHome() {
    var form = $("#hero-search");
    form.onsubmit = function (e) {
      e.preventDefault();
      var q = $("#hero-q").value.trim();
      location.href = "catalog.html" + (q ? "?q=" + encodeURIComponent(q) : "");
    };
    loadAll().then(function (d) {
      var m = maps(d);
      var count = {};
      d.suppliers.forEach(function (s) { count[s.country_code] = (count[s.country_code] || 0) + 1; });
      $("#st-c").textContent = d.countries.length;
      $("#st-k").textContent = d.categories.length;
      $("#st-s").textContent = d.suppliers.length;
      $("#st-v").textContent = d.suppliers.filter(function (s) { return s.is_verified; }).length;

      $("#countries-grid").innerHTML = d.countries.map(function (c) {
        return '<a class="c-card" href="catalog.html?country=' + c.code + '" style="--c:' + (COUNTRY_COLOR[c.code] || "#c9a24a") + '">' +
          '<span class="c-flag">' + (COUNTRY_FLAG[c.code] || "") + '</span>' +
          '<b>' + esc(tr(c.name)) + '</b><small>' + (count[c.code] || 0) + ' ' + t("stat_sup") + '</small></a>';
      }).join("");

      $("#cats-grid").innerHTML = d.categories.map(function (k) {
        return '<a class="k-card" href="catalog.html?cat=' + encodeURIComponent(k.slug) + '"><span>' + esc(k.icon || "•") + '</span>' + esc(tr(k.name)) + '</a>';
      }).join("");

      var feat = d.suppliers.filter(function (s) { return s.is_verified; }).slice(0, 6);
      $("#feat-grid").innerHTML = feat.map(function (s) { return card(s, m); }).join("");
      demoNotice();
    });
    var join = $("#join-btn");
    if (join) join.href = "mailto:" + (CONFIG.contactEmail || "") + "?subject=" + encodeURIComponent("Заявка поставщика / Supplier application");
  }

  // ========== ДЕНЬ 3: КАТАЛОГ ==========
  function pageCatalog() {
    var p = params();
    var q = $("#f-q"), fc = $("#f-country"), fk = $("#f-cat"), fv = $("#f-ver");
    q.value = p.get("q") || "";
    fv.checked = p.get("verified") === "1";

    loadAll().then(function (d) {
      var m = maps(d);
      fc.innerHTML = '<option value="">' + t("f_all_c") + '</option>' + d.countries.map(function (c) {
        return '<option value="' + c.code + '">' + (COUNTRY_FLAG[c.code] || "") + ' ' + esc(tr(c.name)) + '</option>';
      }).join("");
      fk.innerHTML = '<option value="">' + t("f_all_cat") + '</option>' + d.categories.map(function (k) {
        return '<option value="' + esc(k.slug) + '">' + esc(k.icon || "") + ' ' + esc(tr(k.name)) + '</option>';
      }).join("");
      fc.value = p.get("country") || "";
      fk.value = p.get("cat") || "";

      var slugToId = {};
      d.categories.forEach(function (k) { slugToId[k.slug] = k.id; });

      function norm(s) { return String(s || "").toLowerCase().replace(/ё/g, "е"); }
      function haystack(s) {
        var cat = m.k[s.category_id], ctry = m.c[s.country_code];
        var desc = s.description && typeof s.description === "object" ? Object.values(s.description).join(" ") : s.description;
        return norm([s.name, s.city, desc, cat && Object.values(cat.name || {}).join(" "), ctry && Object.values(ctry.name || {}).join(" ")].join(" "));
      }
      d.suppliers.forEach(function (s) { s._h = haystack(s); });

      function apply() {
        var words = norm(q.value).split(/\s+/).filter(Boolean);
        var cc = fc.value, kid = fk.value ? slugToId[fk.value] : null, ver = fv.checked;
        var list = d.suppliers.filter(function (s) {
          if (cc && s.country_code !== cc) return false;
          if (kid && s.category_id !== kid) return false;
          if (ver && !s.is_verified) return false;
          // каждое слово должно встречаться (по началу слова допускаем окончания: "цемента" найдёт "цемент")
          return words.every(function (w) {
            if (s._h.indexOf(w) >= 0) return true;
            return w.length > 4 && s._h.indexOf(w.slice(0, w.length - 2)) >= 0;
          });
        });
        $("#count").textContent = t("found") + ": " + list.length;
        $("#results").innerHTML = list.length ? list.map(function (s) { return card(s, m); }).join("")
          : '<div class="empty">' + t("nothing") + '</div>';

        var np = new URLSearchParams();
        if (q.value.trim()) np.set("q", q.value.trim());
        if (cc) np.set("country", cc);
        if (fk.value) np.set("cat", fk.value);
        if (ver) np.set("verified", "1");
        var qs = np.toString();
        history.replaceState(null, "", location.pathname + (qs ? "?" + qs : ""));
      }
      var timer;
      q.oninput = function () { clearTimeout(timer); timer = setTimeout(apply, 200); };
      fc.onchange = fk.onchange = fv.onchange = apply;
      $("#f-form").onsubmit = function (e) { e.preventDefault(); q.blur(); apply(); };
      $("#f-reset").onclick = function () { q.value = ""; fc.value = ""; fk.value = ""; fv.checked = false; apply(); };
      apply();
      demoNotice();
    });
  }

  // ========== ДЕНЬ 4: СТРАНИЦА ПОСТАВЩИКА ==========
  function pageSupplier() {
    var slug = params().get("s");
    loadAll().then(function (d) {
      var m = maps(d);
      var s = d.suppliers.filter(function (x) { return x.slug === slug; })[0];
      var box = $("#sp");
      if (!s) { box.innerHTML = '<div class="empty">' + t("sp_notfound") + '<br><br><a class="btn" href="catalog.html">' + t("sp_back") + '</a></div>'; return; }
      var cat = m.k[s.category_id], ctry = m.c[s.country_code];
      document.title = s.name + " — B2B Central Asia";

      var digits = function (v) { return String(v || "").replace(/[^\d]/g, ""); };
      var tg = String(s.telegram || "").trim().replace(/^@/, "").replace(/^https?:\/\/t\.me\//i, "");
      var ig = String(s.instagram || "").trim().replace(/^@/, "").replace(/^https?:\/\/(www\.)?instagram\.com\//i, "").replace(/\/$/, "");
      var btns = [];
      if (s.phone) btns.push('<a class="cbtn gold" href="tel:+' + digits(s.phone) + '">📞 ' + t("sp_call") + '<small>' + esc(s.phone) + '</small></a>');
      if (tg) btns.push('<a class="cbtn" target="_blank" rel="noopener" href="https://t.me/' + encodeURIComponent(tg) + '">✈️ ' + t("sp_tg") + '<small>@' + esc(tg) + '</small></a>');
      if (s.whatsapp) btns.push('<a class="cbtn" target="_blank" rel="noopener" href="https://wa.me/' + digits(s.whatsapp) + '">💬 ' + t("sp_wa") + '<small>' + esc(s.whatsapp) + '</small></a>');
      if (s.email) btns.push('<a class="cbtn" href="mailto:' + esc(s.email) + '">✉️ ' + t("sp_mail") + '<small>' + esc(s.email) + '</small></a>');
      if (ig) btns.push('<a class="cbtn" target="_blank" rel="noopener" href="https://instagram.com/' + encodeURIComponent(ig) + '">📷 ' + t("sp_ig") + '<small>@' + esc(ig) + '</small></a>');
      var web = safeUrl(s.website);
      if (web) btns.push('<a class="cbtn" target="_blank" rel="noopener" href="' + esc(web) + '">🌐 ' + t("sp_web") + '<small>' + esc(web.replace(/^https?:\/\//, "")) + '</small></a>');

      box.innerHTML =
        '<a class="back" href="catalog.html">' + t("sp_back") + '</a>' +
        '<div class="sp-head" style="--c:' + (COUNTRY_COLOR[s.country_code] || "#c9a24a") + '">' +
          logoHtml(s, true) +
          '<div><h1>' + esc(s.name) + '</h1>' +
          '<div class="sp-tags">' +
            (s.is_verified ? '<span class="ver">✓ ' + t("verified") + '</span>' : "") +
            (cat ? '<span class="chip">' + esc(cat.icon || "") + ' ' + esc(tr(cat.name)) + '</span>' : "") +
            (s.is_test ? '<span class="test">' + t("test_tag") + '</span>' : "") +
          '</div></div>' +
        '</div>' +
        '<div class="sp-grid">' +
          '<div class="panel"><h2>' + t("sp_about") + '</h2><p class="sp-desc">' + (esc(tr(s.description)) || t("sp_nodesc")) + '</p>' +
            '<dl class="facts">' +
              '<dt>' + t("sp_country") + '</dt><dd>' + (COUNTRY_FLAG[s.country_code] || "") + ' ' + esc(ctry ? tr(ctry.name) : s.country_code) + '</dd>' +
              (s.city ? '<dt>' + t("sp_city") + '</dt><dd>' + esc(s.city) + '</dd>' : "") +
              (cat ? '<dt>' + t("sp_cat") + '</dt><dd>' + esc(tr(cat.name)) + '</dd>' : "") +
            '</dl></div>' +
          '<div class="panel"><h2>' + t("sp_contacts") + '</h2><div class="cbtns">' + btns.join("") + '</div></div>' +
        '</div>';

      var sim = d.suppliers.filter(function (x) { return x.slug !== s.slug && x.category_id === s.category_id; });
      if (sim.length < 3) sim = sim.concat(d.suppliers.filter(function (x) { return x.slug !== s.slug && x.category_id !== s.category_id && x.country_code === s.country_code; }));
      sim = sim.slice(0, 3);
      if (sim.length) {
        $("#similar").innerHTML = '<h2 class="h2">' + t("sp_similar") + '</h2><div class="grid3">' + sim.map(function (x) { return card(x, m); }).join("") + '</div>';
      }
      demoNotice();
    });
  }

  // ---------- СТАРТ ----------
  document.addEventListener("DOMContentLoaded", function () {
    var page = document.body.dataset.page;
    renderChrome(page);
    if (page === "home") pageHome();
    if (page === "catalog") pageCatalog();
    if (page === "supplier") pageSupplier();
  });
})();
