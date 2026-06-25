# wecom. מאגר ידע פנימי

פלטפורמת ידע לנציגי שירות ותמיכה של wecom.

## 📁 מבנה הפרויקט

```
wecom-kb/
├── index.html          ← דף הבית (רשימת כל המסמכים)
├── shared.css          ← עיצוב משותף לכל הדפים
├── README.md
└── docs/
    ├── browsing-issues.html     ← איטיות / חוסר גלישה
    ├── churn-retention.html     ← דיבאג נטישה
    └── [מסמכים עתידיים].html
```

---

## 🚀 פרסום ב-GitHub Pages (שלב אחד)

1. צור repository חדש ב-GitHub (לדוגמה: `wecom-knowledge-base`)
2. העלה את כל הקבצים (drag & drop ב-GitHub.com)
3. לך ל: **Settings → Pages → Branch: main → Save**
4. תוך דקה הפלטפורמה תהיה חיה בכתובת:
   `https://[username].github.io/wecom-knowledge-base/`

---

## ➕ הוספת מסמך חדש

### שלב 1 – צור קובץ HTML חדש ב-`docs/`

העתק את המבנה הבסיסי:

```html
<!DOCTYPE html>
<html lang="he" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>[שם המסמך] | wecom. מאגר ידע</title>
<link rel="stylesheet" href="../shared.css">
</head>
<body>

<nav class="topnav">
  <a href="../index.html" class="topnav-logo">wecom.</a>
  <div class="topnav-sep"></div>
  <a href="../index.html" class="topnav-home">ראשי</a>
  <div class="topnav-sep"></div>
  <div class="topnav-label">[שם המסמך]</div>
</nav>

<div class="page-wrap">
  <main class="article">
    <div class="article-header">
      <div class="doc-meta">
        <span class="badge badge-tech">טכני</span>  <!-- או badge-retain לשימור -->
        <span class="badge badge-updated">עודכן: [תאריך]</span>
      </div>
      <h1 class="article-title">[כותרת]</h1>
      <p class="article-subtitle">[תיאור קצר]</p>
    </div>
    <div class="article-body">
      <!-- תוכן המסמך כאן -->
    </div>
  </main>

  <aside class="sidebar">
    <!-- תוכן עניינים + מסמכים קשורים -->
  </aside>
</div>

</body>
</html>
```

### שלב 2 – הוסף כרטיס ל-`index.html`

מצא את הקטגוריה המתאימה והוסף:

```html
<a href="docs/[שם-הקובץ].html" class="doc-card">
  <div class="dc-icon">📄</div>
  <div class="dc-title">[שם המסמך]</div>
  <div class="dc-desc">[תיאור קצר לנציגים]</div>
  <div class="dc-meta">
    <span class="badge badge-tech" style="font-size:11px;padding:2px 8px;">טכני</span>
    <span>[מספר שלבים] שלבים</span>
    <span class="dc-arrow">←</span>
  </div>
</a>
```

---

## 🧩 רכיבים זמינים ב-shared.css

| רכיב | Class | שימוש |
|------|-------|--------|
| כרטיס שלב | `.step-card` + `.step-num` + `.step-content` | שלבי תפעול |
| הסתעפות אם/אז | `.branch-block` + `.branch-option` | החלטות |
| תוצאות | `.outcome.ok` / `.outcome.next` / `.outcome.alert` | סיום / המשך / שגיאה |
| תסריט שיחה | `.script-block` | ציטוטים מומלצים לנציג |
| כרטיס תרחיש | `.scenario-card` | מסמכי שימור |
| התנגדות/תשובה | `.objection-block` | שאלות לקוח + תגובת נציג |
| עקרונות | `.principles-box` | סיכום עקרונות |

---

## 📋 קטגוריות קיימות

- `badge-tech` (כחול) – תפעולי / טכני
- `badge-retain` (אדום) – שימור לקוחות

להוספת קטגוריה חדשה – הוסף ב-`shared.css`:
```css
.badge-[שם] { background: #[צבע]; color: #[צבע]; }
```
