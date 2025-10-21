# 🎹 KeySpark — Web Organ

<div align="center">

![Version](https://img.shields.io/badge/version-0.1-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Tech](https://img.shields.io/badge/tech-WebAudio%20%7C%20WebMIDI-purple)

**אורגן אינטרנטי מתקדם עם Drawbars בסגנון Hammond**

[תיעוד](#תיעוד) • [התקנה](#התקנה) • [שימוש](#שימוש) • [תכונות](#תכונות)

</div>

---

## 📋 תיאור

**KeySpark** הוא אורגן אינטרנטי מלא המשלב טכנולוגיות Web Audio API ו-Web MIDI API ליצירת חוויית נגינה מקצועית בדפדפן. המכשיר כולל מנוע סינתזה חיה עם Drawbars בסגנון אורגן Hammond קלאסי, מערכת הקלטה ויצוא MIDI, וממשק משתמש מעוצב ומתקדם.

### 🎯 מטרות הפרויקט

- **נגישות**: מכשיר מוזיקלי מלא ללא צורך בהתקנה או תוכנה חיצונית
- **איכות**: צליל אותנטי של אורגן עם הרמוניות מרובות
- **גמישות**: תמיכה במקלדת מחשב, קלט MIDI חיצוני ועכבר
- **יצירתיות**: אפשרויות עיצוב צליל נרחבות עם Drawbars, ריוורב ו-vibrato

---

## ✨ תכונות עיקריות

### 🎛️ מנוע סינתזה

- **9 Drawbars** להרמוניות בסגנון Hammond (1, 2, 3, 4, 5, 6, 8, 10, 12)
- **סינתזה אדיטיבית** עם 9 גלי סינוס בו-זמנית לכל תו
- **Vibrato LFO** עם שליטה על עומק
- **מעטפת ADSR** עם Attack ו-Release מותאמים אישית
- **9 קונפיגורציות מוכנות** (מקשי 1-9) לצלילים קלאסיים

### 🎹 ממשק נגינה

- **מקלדת מחשב מלאה**: שורת ASDF... ללבנים, WETYU... לשחורים
- **קלט MIDI**: זיהוי אוטומטי של מקלדות MIDI חיצוניות
- **ממשק ויזואלי**: מקלדת אינטראקטיבית עם הדגשת מקשים
- **Sustain Pedal**: תמיכה בפדאל ובמקש רווח
- **שליטה על אוקטבות**: מעבר מהיר בין אוקטבות (±7 אוקטבות)

### 🔊 אפקטים ועיבוד

- **Reverb מובנה**: קונבולושן עם IR מותאם (Schroeder network)
- **Mix Dry/Wet**: שליטה מלאה על עוצמת הריוורב
- **Master Gain**: שליטה על עוצמה כללית
- **VU Meter**: תצוגה ויזואלית של פעילות אודיו

### 💾 הקלטה ויצוא

- **הקלטה חיה**: תיעוד כל אירועי MIDI בזמן אמת
- **ניגון הקלטות**: השמעה של ההקלטה עם כל הפרמטרים
- **יצוא MIDI**: שמירת ההקלטה כקובץ `.mid` תקני (SMF Type 0)
- **שליטה על Tempo**: 40-200 BPM

---

## 🚀 התקנה

### דרישות מערכת

- דפדפן מודרני התומך ב:
  - Web Audio API
  - Web MIDI API (אופציונלי - לקלט MIDI)
- אין צורך בשרת - הקובץ עובד באופן עצמאי

### התקנה

1. **הורד את הקובץ**:

   ```bash
   # העתק את KeySpark.html למחשב
   ```

2. **פתח בדפדפן**:
   - גרור את הקובץ אל חלון הדפדפן
   - או: לחיצה כפולה על הקובץ

3. **אפשר גישה**:
   - לחץ בכל מקום במסך כדי לאפשר אודיו
   - אשר גישה ל-MIDI אם יש מכשיר מחובר

---

## 🎮 שימוש

### מקלדת מחשב

#### מקשי נגינה

| מקש | תו | סוג |
|-----|-----|-----|
| A | C | לבן |
| W | C# | שחור |
| S | D | לבן |
| E | D# | שחור |
| D | E | לבן |
| F | F | לבן |
| T | F# | שחור |
| G | G | לבן |
| Y | G# | שחור |
| H | A | לבן |
| U | A# | שחור |
| J | B | לבן |
| K | C (אוקטבה גבוהה) | לבן |

#### מקשי שליטה

- **Space**: Sustain (החזק תווים)
- **Shift**: בוסט זמני למעלה אוקטבה
- **Ctrl**: בוסט זמני למטה אוקטבה
- **1-9**: טעינה מהירה של קונפיגורציות Drawbar

### Drawbar Presets

| מקש | קונפיגורציה | תיאור |
|-----|------------|-------|
| 1 | 888000000 | Full organ - עשיר ועמוק |
| 2 | 808060200 | Jazz - בינוני עם קצת בס |
| 3 | 874220000 | Blues - חם ועמוק |
| 4 | 905000321 | Gospel - בהיר עם הרמוניות גבוהות |
| 5 | 666632111 | Flutes - רך ועדין |
| 6 | 992211100 | Rock - חזק ואגרסיבי |
| 7 | 850603020 | Percussive - חד עם אטק מהיר |
| 8 | 508050302 | Hollow - צליל חלול |
| 9 | 933111111 | Bright - בהיר ועדין |

### קלט MIDI

1. חבר מקלדת MIDI למחשב
2. פתח את KeySpark (הגישה תאושר אוטומטית)
3. נגן - כל אירועי Note On/Off ו-Sustain Pedal נתמכים
4. LED ירוק יציין חיבור פעיל

### הקלטה ויצוא

1. **התחל הקלטה**: לחץ על ⏺️ הקלט
2. **נגן**: כל הנגינה תתועד (מקלדת או MIDI)
3. **עצור**: לחץ שוב על הכפתור
4. **נגן חזרה**: ▶️ נגן
5. **ייצא**: 💾 הורד .mid - קובץ MIDI מוכן לשימוש ב-DAW

---

## 🎛️ פרמטרים מתקדמים

### מעטפת (Envelope)

- **Attack**: 0-200ms - זמן עליית הצליל
- **Release**: 0-1200ms - זמן דעיכת הצליל

### אפקטים

- **Vibrato**: 0-7 - עומק תנודת הגובה
- **Gain**: 0-1 - עוצמה כוללת
- **Reverb Mix**: 0-1 - יחס Dry/Wet

### אוקטבות

- טווח: 1-7
- שליטה: כפתורים או Shift/Ctrl
- ברירת מחדל: אוקטבה 4 (Middle C)

---

## 🏗️ ארכיטקטורה טכנית

### מבנה הקוד

```
KeySpark
├── Audio Engine (Web Audio API)
│   ├── AudioContext & Master Chain
│   ├── Reverb (Convolver + IR Generator)
│   ├── Voice Management (Map-based)
│   └── Additive Synthesis (9 oscillators per voice)
├── MIDI Engine
│   ├── Recorder (Events array)
│   ├── Player (setTimeout-based)
│   └── Exporter (SMF Type 0 builder)
├── Input Handlers
│   ├── Keyboard (KeyDown/Up)
│   ├── MIDI (WebMIDI API)
│   └── Mouse (Optional)
└── UI (GlowTune Design System)
    ├── Drawbars Grid
    ├── Visual Keyboard
    ├── Controls Panel
    └── Recorder Panel
```

### טכנולוגיות

- **Web Audio API**: מנוע האודיו העיקרי
- **Web MIDI API**: קלט ממכשירים חיצוניים
- **Vanilla JavaScript**: ללא תלויות חיצוניות
- **CSS Grid & Flexbox**: ממשק רספונסיבי
- **Custom Properties**: ערכת נושא מותאמת

---

## 🎨 עיצוב UI

### GlowTune Design System

- **פלטת צבעים**: כחול-סגול עמוק עם הדגשות ניאון
- **טיפוגרפיה**: Sans-serif מודרני עם מספרים טבולריים
- **אנימציות**: VU meter, LED indicators, key highlights
- **רספונסיביות**: מתאים לכל גודל מסך

### תכונות נגישות

- עברית RTL מלאה
- ניגודיות גבוהה
- פידבק ויזואלי ברור
- תמיכה במקלדת מלאה

---

## 🛠️ פיתוח ותרומה

### הרחבות אפשריות

- [ ] אפקטים נוספים (Chorus, Tremolo, Distortion)
- [ ] שמירה/טעינה של Patches
- [ ] Polyphony Counter
- [ ] Spectrum Analyzer
- [ ] Loop Recording
- [ ] Multi-track Sequencer

### תרומה לפרויקט

1. Fork את הפרויקט
2. צור branch חדש (`git checkout -b feature/AmazingFeature`)
3. Commit את השינויים (`git commit -m 'Add some AmazingFeature'`)
4. Push ל-branch (`git push origin feature/AmazingFeature`)
5. פתח Pull Request

---

## 📄 רישיון

MIT License - ראה קובץ LICENSE לפרטים נוספים.

קוד זה פתוח לשימוש חופשי, שינוי והפצה.

---

## 👨‍💻 קרדיטים

**פותח על ידי**: AnLoMinus  
**ארגון**: SparKing Lab  
**תאריך**: 21.10.2025 (י״ט בתשרי תשפ״ו)

### טכנולוגיות ומקורות השראה

- Web Audio API Documentation (MDN)
- Web MIDI API Specification (W3C)
- Hammond Organ Drawbar System
- Schroeder Reverb Algorithm
- MIDI Standard Format 1.0

---

## 🔗 קישורים

- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [Web MIDI API](https://www.w3.org/TR/webmidi/)
- [MIDI Specification](https://www.midi.org/specifications)

---

## 📞 יצירת קשר

יש לך שאלות? רעיונות? בעיות?

- פתח Issue בפרויקט
- שלח Pull Request עם שיפורים
- צור קשר דרך AnLoMinus

---

<div align="center">

**עשוי באהבה למוזיקה ולקוד פתוח 🎹✨**

**KeySpark Engine · GlowTune UI · ToneLab Repository**

</div>
