# 📝 CHANGELOG

כל השינויים המשמעותיים בפרויקט KeySpark יתועדו בקובץ זה.

הפורמט מבוסס על [Keep a Changelog](https://keepachangelog.com/he/1.0.0/),
והפרויקט עוקב אחר [Semantic Versioning](https://semver.org/lang/he/).

---

## [0.1.1] - 2025-10-21 (י״ט בתשרי תשפ״ו)

### 🌀 Leslie Speaker Simulator - תכונה מרכזית

#### ✨ Added - תכונות חדשות

##### 🌀 Leslie Speaker Effect
- **Rotating Speaker Simulation** - סימולציה של רמקול מסתובב בסגנון Leslie
  - Horn rotor (treble) - רוטור גבוה מהיר יותר
  - Drum rotor (bass) - רוטור נמוך איטי יותר
- **Doppler Effect** - אפקט דופלר (frequency modulation) עבור אפקט סיבוב אותנטי
- **Amplitude Modulation** - אפנון אמפליטודה (tremolo) עבור עומק הצליל
- **Stereo Panning** - פנינג סטריאו דינמי עם LFO
- **Speed Control** - בקרת מהירות עם שני מצבים:
  - 🐢 **Slow** - סיבוב איטי (Horn: 0.8Hz, Drum: 0.6Hz)
  - ⚡ **Fast** - סיבוב מהיר (Horn: 6.5Hz, Drum: 5.2Hz)
- **Smooth Transitions** - מעברים חלקים בין מהירויות (1.5 שניות האצה/האטה)
- **Depth Control** - שליטה על עוצמת האפקט (0-100%)
- **Wet/Dry Mix** - ערבוב אוטומטי בין אות מעובד לישיר

##### 🎛️ UI Controls - בקרות ממשק
- **Leslie Toggle Button** - כפתור הפעלה/כיבוי של Leslie
  - 🌀 Leslie Off (warn) → 🌀 Leslie On (ok)
  - השבתה/הפעלה אוטומטית של כפתורים נלווים
- **Speed Switch Button** - כפתור מעבר בין Slow/Fast
  - 🐢 Slow ↔️ ⚡ Fast
  - רק פעיל כאשר Leslie מופעל
- **Depth Slider** - סליידר לשליטה על עומק האפקט
  - טווח: 0-100%
  - משפיע על AM ו-panning depth
  - רק פעיל כאשר Leslie מופעל

#### 🔧 Technical - שינויים טכניים

##### Audio Architecture
- **Leslie Audio Chain** - שרשרת אודיו ייעודית ל-Leslie:
  ```
  Voice → Leslie Input → Splitter (Stereo) → 
    Left/Right AM Gain → Merger → 
    StereoPanner → Leslie Wet Gain → Dry Gain → Master
  ```
- **6 LFO Oscillators** - 6 מתנדים לאפקט מורכב:
  - hornLFO_AM - אפנון אמפליטודה Horn
  - hornLFO_FM - אפנון תדר Horn (Doppler)
  - drumLFO_AM - אפנון אמפליטודה Drum
  - drumLFO_FM - אפנון תדר Drum (Doppler)
  - panLFO - פנינג סטריאו
  - כל LFO עם gain node ייעודי לשליטה על depth
- **Stereo Processing** - עיבוד סטריאו מלא:
  - ChannelSplitter/Merger
  - StereoPanner או fallback ל-Panner
  - AM modulation נפרד לכל ערוץ
- **Voice Routing Update** - עדכון ניתוב קולות:
  - כל voice מחובר גם ל-`leslie.input` וגם ל-`leslie.dryBypass`
  - בחירה דינמית בין wet/dry לפי מצב Leslie

##### Code Quality
- **Memory Management** - ניהול זיכרון משופר:
  - ניתוק מלא של gain nodes (`pre`, `mix`, `voiceGain`) בסיום voice
  - מניעת דליפות זיכרון (memory leaks)
- **Function Organization** - ארגון פונקציות:
  - `setLeslieSpeed(speed)` - שינוי מהירות עם ramping
  - `toggleLeslie(enabled)` - הפעלה/כיבוי עם fade
  - Event handlers ייעודיים ל-UI controls

#### 📊 Performance - ביצועים
- **CPU Optimization** - אופטימיזציה למעבד:
  - Leslie LFOs רצים ברקע רק פעם אחת (לא per-voice)
  - Gain modulation יעיל דרך AudioParam
  - Minimal computational overhead
- **Efficient Routing** - ניתוב יעיל:
  - Signal splitting נעשה פעם אחת בשרשרת
  - Stereo processing מרוכז ב-Leslie processor

#### 🎨 UI/UX Improvements
- **Visual Feedback** - משוב ויזואלי:
  - שינוי צבע כפתור Leslie (warn → ok)
  - השבתה/הפעלה דינמית של controls
  - תצוגת מהירות נוכחית (Slow/Fast)
- **User Experience** - חווית משתמש:
  - מעברים חלקים בין מצבים
  - אינטגרציה טבעית עם UI קיים
  - Badge חדש: 🌀 Leslie Sim

#### 📖 Documentation
- **Updated Descriptions** - תיעוד מעודכן:
  - תיאור משנה כולל "Leslie Speaker Simulator"
  - Badge חדש בממשק
  - TODO.md מעודכן עם הישג v0.1.1

---

## [0.1.0] - 2025-10-21 (י״ט בתשרי תשפ״ו)

### 🎉 גרסה ראשונית - First Release

#### ✨ Added - תכונות חדשות

##### 🎹 מנוע סינתזה

- **Drawbar Organ Engine** - מנוע אורגן מלא עם 9 Drawbars
- **Additive Synthesis** - סינתזה אדיטיבית עם 9 הרמוניות (1, 2, 3, 4, 5, 6, 8, 10, 12)
- **Voice Management** - ניהול פוליפוני של תווים עם Map-based architecture
- **ADSR Envelope** - מעטפת Attack/Release מותאמת אישית
- **Vibrato LFO** - אפנון LFO עם שליטה על עומק (0-7)

##### 🎛️ אפקטים

- **Convolution Reverb** - ריוורב באיכות גבוהה עם Impulse Response מותאם
- **Dry/Wet Mix** - שליטה מלאה על יחס אות ישיר/מעובד
- **Master Gain** - שליטה על עוצמה כוללת (0-1)
- **Dynamic VU Meter** - תצוגה ויזואלית של רמת האודיו

##### 🎮 קלט ושליטה

- **Computer Keyboard Input** - מקלדת QWERTY מלאה למפת פסנתר
  - שורת ASDF... למקשים לבנים
  - WETYU... למקשים שחורים
  - כיסוי של אוקטבה וחצי
- **Web MIDI Support** - קלט מלא ממכשירי MIDI חיצוניים
  - זיהוי אוטומטי של מכשירים
  - תמיכה ב-Note On/Off
  - תמיכה ב-Sustain Pedal (CC 64)
  - LED אינדיקטור לסטטוס חיבור
- **Mouse Input** - אפשרות לנגינה עם העכבר על המקלדת הוירטואלית
- **Sustain Control** - פדאל Sustain וירטואלי (מקש Space)
- **Octave Shift** - מעבר בין 7 אוקטבות (1-7)
  - כפתורי ⬆️/⬇️
  - Shift/Ctrl למעבר זמני

##### 🎨 ממשק משתמש (GlowTune UI)

- **Visual Keyboard** - מקלדת ויזואלית עם 18 מקשים
  - הדגשה אקטיבית של מקשים לחוצים
  - עיצוב משתנה למקשים שחורים/לבנים
  - תצוגת קיצורי מקלדת
- **Drawbars Panel** - 9 סליידרים להרמוניות עם תצוגת מספר הרמוניה
- **Controls Grid** - פאנל בקרה עם Attack, Release, Vibrato, Gain, Reverb
- **Octave Display** - תצוגה דינמית של אוקטבה נוכחית
- **Dark Theme** - ערכת נושא כחול-סגול עמוק עם אלמנטים זוהרים
- **RTL Support** - תמיכה מלאה בעברית ו-RTL
- **Responsive Design** - מתאים לכל גודל מסך

##### 💾 הקלטה ויצוא MIDI

- **Real-time Recording** - הקלטה חיה של כל אירועי MIDI
  - תיעוד Note On/Off עם Velocity
  - תיעוד Timestamp מדויק במילישניות
  - מונה אירועים בזמן אמת
- **Playback Engine** - ניגון הקלטות עם timing מדויק
  - תמיכה ב-Tempo מותאם (40-200 BPM)
  - Stop/Resume functionality
- **MIDI Export (SMF)** - יצוא לפורמט Standard MIDI File Type 0
  - Variable-length encoding תקני
  - Tempo meta-event
  - שמירה אוטומטית עם timestamp בשם
- **Recording Controls** - כפתורי הקלטה/ניגון/עצירה/ניקוי
- **Tempo Slider** - שליטה על מהירות (40-200 BPM)

##### 🎼 Drawbar Presets

- **9 קונפיגורציות מוכנות** - טעינה מהירה עם מקשי 1-9
  1. **888000000** - Full Organ (עשיר ועמוק)
  2. **808060200** - Jazz (בינוני עם בס)
  3. **874220000** - Blues (חם ועמוק)
  4. **905000321** - Gospel (בהיר עם הרמוניות גבוהות)
  5. **666632111** - Flutes (רך ועדין)
  6. **992211100** - Rock (חזק ואגרסיבי)
  7. **850603020** - Percussive (חד עם אטק מהיר)
  8. **508050302** - Hollow (צליל חלול)
  9. **933111111** - Bright (בהיר ועדין)

##### 🛡️ תכונות אמינות

- **Panic Button** - כפתור All Notes Off לעצירת כל התווים
- **Audio Context Unlock** - טיפול אוטומטי ב-suspended audio context
- **Error Handling** - ניהול שגיאות עבור disconnect של nodes
- **Browser Compatibility** - תמיכה ב-webkit prefixes

##### 📚 תיעוד

- **Built-in Help Section** - מדור עזרה מהירה בממשק
- **Visual Hints** - הסברים על גבי הכפתורים והבקרות
- **Keyboard Layout Guide** - מפת מקלדת ויזואלית
- **Credits Footer** - קרדיטים מלאים עם תאריכים לועזיים ועבריים

##### 🎨 Design System - GlowTune

- **CSS Custom Properties** - משתני צבע גלובליים
- **Gradient Backgrounds** - גרדיאנטים רדיאליים עמוקים
- **Glow Effects** - אפקטי זוהר על LEDs וכפתורים פעילים
- **Card-based Layout** - עיצוב מבוסס כרטיסיות מודרני
- **Badge Components** - תגי סטטוס מעוצבים
- **Pill Indicators** - אינדיקטורים מעוגלים

#### 🔧 Technical - טכני

##### ארכיטקטורה

- **Single File Application** - אפליקציה שלמה בקובץ HTML יחיד
- **No Dependencies** - ללא ספריות חיצוניות
- **Vanilla JavaScript** - ES6+ נקי
- **Web Audio API** - שימוש מלא ב-API נייטיבי
- **Web MIDI API** - אינטגרציה מלאה

##### ביצועים

- **Efficient Voice Management** - Map-based במקום Array
- **Lazy Audio Unlock** - אתחול רק כשצריך
- **VU Meter Optimization** - שימוש ב-requestAnimationFrame
- **Event Delegation** - מאזינים יעילים

##### תאימות

- **Modern Browsers** - Chrome, Edge, Safari, Firefox
- **WebKit Prefix Support** - תמיכה ב-Safari ישן יותר
- **Mobile-Ready** - ממשק רספונסיבי (למרות שהדגש על שולחן עבודה)

#### 📊 Statistics - סטטיסטיקות

- **קווי קוד**: ~720
- **גודל קובץ**: ~32KB
- **פוליפוניה**: ללא הגבלה (תלוי במעבד)
- **Latency**: <10ms (בתנאים אידיאליים)
- **תמיכה בדפדפנים**: 95%+ של משתמשים

---

## 🔮 תכנון עתידי - Planned Features

### [0.2.0] - Roadmap

#### תכונות מתוכננות

- [ ] **Chorus Effect** - אפקט Chorus עם Rate ו-Depth
- [ ] **Tremolo** - אפנון אמפליטודה
- [ ] **Percussion** - מערכת Percussion בסגנון Hammond B3
- [ ] **Leslie Simulator** - סימולציה של רמקול Leslie מסתובב
- [ ] **Preset Management** - שמירה וטעינה של Patches
- [ ] **Multi-track Recording** - מספר רצועות
- [ ] **Loop Recording** - הקלטת Loops
- [ ] **Metronome** - מטרונום מובנה
- [ ] **Tuning Control** - שליטה על A4 frequency
- [ ] **Microtuning** - תמיכה ב-scales שונים
- [ ] **MIDI Clock Sync** - סנכרון עם MIDI Clock חיצוני
- [ ] **Spectrum Analyzer** - אנליזת פס תדרים ויזואלי
- [ ] **Waveform Display** - תצוגת גל הצליל

#### שיפורים מתוכננים

- [ ] **PWA Support** - Progressive Web App
- [ ] **Offline Mode** - עבודה ללא אינטרנט
- [ ] **Theme Switcher** - מספר ערכות נושא
- [ ] **Accessibility** - שיפורי נגישות (ARIA)
- [ ] **Mobile Optimizations** - אופטימיזציה למובייל
- [ ] **Touch Gestures** - מחוות מגע למובייל
- [ ] **Keyboard Shortcuts** - קיצורי מקלדת נוספים
- [ ] **Settings Persistence** - שמירת הגדרות ב-localStorage
- [ ] **Export to WAV** - יצוא אודיו ישיר
- [ ] **Import MIDI** - ייבוא קבצי MIDI

#### תיקונים ידועים לטיפול

- [ ] בדיקת תאימות ל-Firefox (Web MIDI)
- [ ] אופטימיזציה של זיכרון ב-sessions ארוכים
- [ ] שיפור דיוק timing בניגון הקלטות

---

## 📖 פורמט רישום שינויים

### קטגוריות

- **Added** - תכונות חדשות
- **Changed** - שינויים בפונקציונליות קיימת
- **Deprecated** - תכונות שיוסרו בקרוב
- **Removed** - תכונות שהוסרו
- **Fixed** - תיקוני באגים
- **Security** - תיקוני אבטחה

### גרסאות

- **[MAJOR.MINOR.PATCH]** - פורמט Semantic Versioning
  - **MAJOR**: שינויים לא תואמים לאחור
  - **MINOR**: תכונות חדשות תואמות לאחור
  - **PATCH**: תיקוני באגים תואמים לאחור

---

<div align="center">

**KeySpark - נוצר עם ❤️ על ידי AnLoMinus @ SparKing Lab**

*"אורגן שהופך כל דפדפן לבמה מוזיקלית"* 🎹✨

[חזור ל-README](README.md)

</div>
