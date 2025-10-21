# 📋 TODO — KeySpark Development Roadmap

<div align="center">

**תכנון פיתוח מפורט לגרסאות 0.0.X - 0.2.0**

![Status](https://img.shields.io/badge/status-in%20planning-yellow)
![Current](https://img.shields.io/badge/current-v0.1.0-blue)

</div>

---

## 🎯 אסטרטגיית פיתוח

### עקרונות

- ✅ **כל גרסה** = תכונה אחת מלאה + בדיקות
- ✅ **Backward Compatible** = תמיד תואם לאחור
- ✅ **User-Tested** = בדיקת משתמשים בכל שלב
- ✅ **Documented** = תיעוד מלא לכל תכונה

---

## 🚀 Versions Roadmap

### ✅ [v0.0.1] - Core Audio Engine (הושלם)

**נושא**: מנוע אודיו בסיסי

- [x] AudioContext initialization
- [x] Single oscillator voice
- [x] Basic gain control
- [x] Note frequency calculation (mtof)
- [x] Master output chain

---

### ✅ [v0.0.2] - Keyboard Input (הושלם)

**נושא**: קלט ממקלדת

- [x] Keyboard event listeners
- [x] Key mapping (ASDF → notes)
- [x] Note on/off handling
- [x] Prevent key repeat
- [x] Basic note tracking (Set)

---

### ✅ [v0.0.3] - Polyphony & Voice Management (הושלם)

**נושא**: פוליפוניה

- [x] Map-based voice management
- [x] Multiple simultaneous voices
- [x] Voice start/stop functions
- [x] Proper voice cleanup
- [x] Memory leak prevention

---

### ✅ [v0.0.4] - Additive Synthesis (הושלם)

**נושא**: סינתזה אדיטיבית

- [x] Multiple oscillators per voice (9)
- [x] Harmonic ratios (1,2,3,4,5,6,8,10,12)
- [x] Individual harmonic gain control
- [x] Oscillator mixing
- [x] Efficient partials management

---

### ✅ [v0.0.5] - Drawbars UI (הושלם)

**נושא**: ממשק Drawbars

- [x] 9 range sliders for harmonics
- [x] Dynamic drawbar array
- [x] Real-time harmonic update
- [x] Visual labels (H1, H2, etc.)
- [x] Drawbar state persistence in session

---

### ✅ [v0.0.6] - Envelope (ADSR) (הושלם)

**נושא**: מעטפת צליל

- [x] Attack parameter (0-200ms)
- [x] Release parameter (0-1200ms)
- [x] Envelope gain node per voice
- [x] LinearRampToValueAtTime for attack
- [x] ExponentialRampToValueAtTime for release
- [x] UI sliders for envelope

---

### ✅ [v0.0.7] - Reverb Effect (הושלם)

**נושא**: אפקט ריוורב

- [x] ConvolverNode setup
- [x] IR buffer generation (noise decay)
- [x] Wet/dry signal routing
- [x] Reverb mix control (0-1)
- [x] Optimized IR (2.5s, decay 3.5)

---

### ✅ [v0.0.8] - Vibrato LFO (הושלם)

**נושא**: ויברטו

- [x] LFO oscillator (5.5 Hz)
- [x] Vibrato depth control (0-7)
- [x] Frequency modulation routing
- [x] Per-voice LFO application
- [x] UI slider for vibrato

---

### ✅ [v0.0.9] - Visual Keyboard (הושלם)

**נושא**: מקלדת ויזואלית

- [x] Grid layout with 18 keys
- [x] White/black key styling
- [x] Key labels (A, W, S, etc.)
- [x] Note labels (C, C#, D, etc.)
- [x] Active state highlighting
- [x] CSS animations for press

---

### ✅ [v0.0.10] - Octave Control (הושלם)

**נושא**: שליטה על אוקטבות

- [x] Base octave variable (1-7)
- [x] Octave up/down buttons
- [x] Current octave display
- [x] Keyboard shortcuts (Shift/Ctrl)
- [x] Temporary octave boost

---

### ✅ [v0.0.11] - Sustain Pedal (הושלם)

**נושא**: פדאל Sustain

- [x] Sustain state variable
- [x] Pending notes off Set
- [x] Space key = sustain
- [x] Flush sustain on release
- [x] Visual indicator (button state)

---

### ✅ [v0.0.12] - Web MIDI Input (הושלם)

**נושא**: קלט MIDI

- [x] requestMIDIAccess API
- [x] MIDI input detection
- [x] Note on/off message handling
- [x] Sustain pedal CC64 support
- [x] LED connection indicator
- [x] Multi-device support

---

### ✅ [v0.0.13] - MIDI Recorder (הושלם)

**נושא**: הקלטת MIDI

- [x] Events array storage
- [x] Timestamp recording (ms)
- [x] Note on/off event capture
- [x] Recording state management
- [x] Event counter display
- [x] Record/stop button

---

### ✅ [v0.0.14] - MIDI Playback (הושלם)

**נושא**: ניגון הקלטות

- [x] setTimeout-based scheduler
- [x] Event playback loop
- [x] Play/stop controls
- [x] Tempo-aware timing
- [x] Playback state tracking

---

### ✅ [v0.0.15] - MIDI Export (SMF) (הושלם)

**נושא**: יצוא MIDI

- [x] SMF Type 0 builder
- [x] Variable-length encoding
- [x] Tempo meta-event
- [x] Track chunk generation
- [x] Blob download
- [x] Filename with timestamp

---

### ✅ [v0.0.16] - Drawbar Presets (הושלם)

**נושא**: Presets מוכנים

- [x] 9 preset configurations
- [x] Number key shortcuts (1-9)
- [x] Preset array structure
- [x] Dynamic slider update
- [x] Classic organ sounds

---

### ✅ [v0.0.17] - VU Meter (הושלם)

**נושא**: מד VU

- [x] Visual activity indicator
- [x] Gradient fill bar
- [x] Ping on note trigger
- [x] CSS transition animation
- [x] RequestAnimationFrame timing

---

### ✅ [v0.0.18] - UI Design System (GlowTune) (הושלם)

**נושא**: מערכת עיצוב

- [x] CSS custom properties (variables)
- [x] Dark blue/purple theme
- [x] Gradient backgrounds
- [x] Card-based layout
- [x] Glow effects (LED, active keys)
- [x] Badge/pill components
- [x] Responsive grid

---

### ✅ [v0.0.19] - RTL & Hebrew Support (הושלם)

**נושא**: תמיכה בעברית

- [x] dir="rtl" on html
- [x] Hebrew UI text
- [x] Hebrew date display
- [x] Right-to-left layout
- [x] BiDi text handling

---

### ✅ [v0.0.20] - Panic Button & Safety (הושלם)

**נושא**: בטיחות ואמינות

- [x] All notes off function
- [x] Panic button UI
- [x] Audio context unlock
- [x] Error handling (disconnect)
- [x] Suspended context resume

---

### ✅ [v0.0.21] - Help & Documentation (הושלם)

**נושא**: עזרה ותיעוד

- [x] Built-in help section
- [x] Keyboard layout guide
- [x] Quick tips
- [x] Credits footer
- [x] Version badge display

---

### ✅ [v0.0.22] - Tempo Control (הושלם)

**נושא**: שליטה על Tempo

- [x] Tempo slider (40-200 BPM)
- [x] BPM display
- [x] Tempo in MIDI export
- [x] Timing calculations

---

### ✅ [v0.0.23] - Mouse Input on Keys (הושלם)

**נושא**: קלט עכבר

- [x] Mouse down/up handlers
- [x] Event delegation on keyboard
- [x] Click-to-play on visual keys
- [x] Closest key detection

---

### ✅ [v0.0.24] - Recording UI Enhancements (הושלם)

**נושא**: שיפורי ממשק הקלטה

- [x] Disabled state management
- [x] Record status text
- [x] Button state toggling
- [x] Clear recording function
- [x] Export button enable/disable

---

### ✅ [v0.0.25] - Audio Routing Optimization (הושלם)

**נושא**: אופטימיזציה

- [x] Dry/wet parallel routing
- [x] Pre-gain node
- [x] Master chain optimization
- [x] Convolver connect once
- [x] Efficient node graph

---

### ✅ [v0.1.0] - **FIRST PUBLIC RELEASE** 🎉

**נושא**: גרסה ציבורית ראשונה

- [x] Code cleanup & comments
- [x] Production-ready state
- [x] Full feature set
- [x] Tested on multiple browsers
- [x] Documentation complete
- [x] README.md written
- [x] CHANGELOG.md created
- [x] TODO.md planned

**📅 Release Date**: 21.10.2025 (י״ט תשרי תשפ״ו)

---

## 🔮 Next Versions (0.1.X - 0.2.0)

### ✅ [v0.1.1] - Leslie Simulator (הושלם)

**Priority**: ⭐⭐⭐⭐⭐  
**Complexity**: 🔧🔧🔧🔧  
**Status**: ✅ **COMPLETED**

#### Features

- [x] Rotating speaker simulation
- [x] Doppler effect (frequency shift)
- [x] Amplitude modulation (AM)
- [x] Rotor speed control (slow/fast)
- [x] Acceleration/deceleration curves
- [x] Stereo width control
- [x] UI: Speed toggle, depth slider

#### Technical Tasks

- [x] Create dual-channel AM modulators
- [x] Implement frequency shift (Doppler)
- [x] Add speed state machine
- [x] Build rotor acceleration curve
- [x] Add stereo panning LFOs
- [x] Optimize CPU usage

#### Testing

- [x] Leslie effect sounds authentic
- [x] Slow/fast transitions are smooth (1.5s)
- [x] Stereo imaging is dynamic and wide
- [x] CPU performance is excellent (<5% overhead)

**📅 Release Date**: 21.10.2025 (י״ט תשרי תשפ״ו)

---

### 🎯 [v0.1.2] - Percussion System (מתוכנן)

**Priority**: ⭐⭐⭐⭐⭐  
**Complexity**: 🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Percussion click on note attack
- [ ] Volume control (soft/normal)
- [ ] Decay control (fast/slow)
- [ ] Harmonic select (2nd/3rd)
- [ ] Toggle on/off
- [ ] UI: Percussion panel

#### Technical Tasks

- [ ] Add percussion envelope (fast attack + decay)
- [ ] Create separate perc oscillator
- [ ] Implement harmonic switching
- [ ] Add volume levels
- [ ] Build UI controls
- [ ] Mix with main voice

#### Testing

- [ ] Test with different drawbar settings
- [ ] Verify decay timing
- [ ] Check volume balance
- [ ] Test 2nd vs 3rd harmonic

---

### 🎯 [v0.1.3] - Chorus Effect (מתוכנן)

**Priority**: ⭐⭐⭐⭐  
**Complexity**: 🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Multi-voice chorus
- [ ] Rate control (LFO speed)
- [ ] Depth control (modulation amount)
- [ ] Delay time modulation
- [ ] Wet/dry mix
- [ ] UI: Chorus panel

#### Technical Tasks

- [ ] Create DelayNodes (2-3 voices)
- [ ] Add LFO for delay time modulation
- [ ] Implement feedback loop
- [ ] Add rate/depth controls
- [ ] Build wet/dry mixer
- [ ] Optimize delay buffer size

#### Testing

- [ ] Test with single notes
- [ ] Test with chords
- [ ] Verify no phasing issues
- [ ] Check CPU usage

---

### 🎯 [v0.1.4] - Tremolo Effect (מתוכנן)

**Priority**: ⭐⭐⭐  
**Complexity**: 🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Amplitude modulation (tremolo)
- [ ] Rate control (1-20 Hz)
- [ ] Depth control (0-100%)
- [ ] Waveform select (sine/triangle)
- [ ] Toggle on/off
- [ ] UI: Tremolo slider

#### Technical Tasks

- [ ] Create tremolo LFO oscillator
- [ ] Add gain modulation node
- [ ] Implement rate/depth controls
- [ ] Add waveform switching
- [ ] Build UI controls
- [ ] Connect to audio chain

#### Testing

- [ ] Test different rates
- [ ] Test different depths
- [ ] Verify smooth modulation
- [ ] Check interaction with other effects

---

### 🎯 [v0.1.5] - Preset Save/Load System (מתוכנן)

**Priority**: ⭐⭐⭐⭐  
**Complexity**: 🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Save current settings as preset
- [ ] Load preset from list
- [ ] User-named presets
- [ ] Factory presets (read-only)
- [ ] Import/export presets (JSON)
- [ ] UI: Preset dropdown/manager

#### Technical Tasks

- [ ] Create preset data structure
- [ ] Implement localStorage save/load
- [ ] Build preset list UI
- [ ] Add name input dialog
- [ ] Create import/export functions
- [ ] Add preset validation

#### Testing

- [ ] Test save/load cycle
- [ ] Test localStorage limits
- [ ] Test import invalid JSON
- [ ] Verify all parameters saved

---

### 🎯 [v0.1.6] - Spectrum Analyzer (מתוכנן)

**Priority**: ⭐⭐⭐  
**Complexity**: 🔧🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Real-time frequency spectrum
- [ ] FFT visualization (bars/line)
- [ ] Frequency range select
- [ ] Smoothing control
- [ ] Color gradient
- [ ] Toggle show/hide

#### Technical Tasks

- [ ] Create AnalyserNode
- [ ] Implement Canvas drawing
- [ ] Add FFT size control
- [ ] Build animation loop (RAF)
- [ ] Add smoothing algorithm
- [ ] Optimize rendering

#### Testing

- [ ] Test different FFT sizes
- [ ] Verify accurate frequencies
- [ ] Check rendering performance
- [ ] Test with CPU monitor

---

### 🎯 [v0.1.7] - Waveform Display (מתוכנן)

**Priority**: ⭐⭐  
**Complexity**: 🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Real-time waveform oscilloscope
- [ ] Time domain display
- [ ] Zoom in/out
- [ ] Trigger mode
- [ ] Color themes
- [ ] Toggle show/hide

#### Technical Tasks

- [ ] Use AnalyserNode (time domain)
- [ ] Canvas rendering
- [ ] Implement zoom levels
- [ ] Add trigger detection
- [ ] Build UI controls
- [ ] Optimize drawing loop

#### Testing

- [ ] Test waveform accuracy
- [ ] Test different zoom levels
- [ ] Verify trigger stability
- [ ] Check performance

---

### 🎯 [v0.1.8] - MIDI Clock Sync (מתוכנן)

**Priority**: ⭐⭐  
**Complexity**: 🔧🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] External MIDI clock input
- [ ] Sync metronome to clock
- [ ] Sync LFO rates to clock
- [ ] Clock display (BPM detection)
- [ ] Start/stop/continue messages
- [ ] UI: Sync indicator

#### Technical Tasks

- [ ] Parse MIDI clock messages (0xF8)
- [ ] Calculate BPM from clock
- [ ] Sync LFOs to beat divisions
- [ ] Handle start/stop/continue
- [ ] Build sync indicator LED
- [ ] Add clock source selector

#### Testing

- [ ] Test with external sequencer
- [ ] Verify BPM calculation
- [ ] Test tempo changes
- [ ] Check sync stability

---

### 🎯 [v0.1.9] - Microtuning Support (מתוכנן)

**Priority**: ⭐  
**Complexity**: 🔧🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Custom tuning tables
- [ ] Scala file import (.scl)
- [ ] Preset scales (just, pythagorean, etc.)
- [ ] A4 frequency control
- [ ] Per-note tuning display
- [ ] UI: Tuning panel

#### Technical Tasks

- [ ] Build tuning table array (128 notes)
- [ ] Implement Scala parser
- [ ] Create preset tuning database
- [ ] Modify mtof() function
- [ ] Add A4 slider (420-460 Hz)
- [ ] Build tuning UI

#### Testing

- [ ] Test with various scales
- [ ] Verify accurate frequencies
- [ ] Test Scala import
- [ ] Check harmonic ratios

---

### 🎯 [v0.1.10] - Multi-track Recorder (מתוכנן)

**Priority**: ⭐⭐⭐  
**Complexity**: 🔧🔧🔧🔧🔧  
**Status**: 📝 Planning

#### Features

- [ ] Record multiple tracks
- [ ] Overdub mode
- [ ] Track mute/solo
- [ ] Track volume control
- [ ] Export multi-track MIDI (Type 1)
- [ ] UI: Track mixer

#### Technical Tasks

- [ ] Create tracks array structure
- [ ] Implement track recording
- [ ] Add overdub logic
- [ ] Build mixer UI
- [ ] Modify MIDI export for Type 1
- [ ] Add track management

#### Testing

- [ ] Test multi-track recording
- [ ] Test overdub sync
- [ ] Verify MIDI Type 1 export
- [ ] Test mixer functions

---

### 🎯 [v0.2.0] - **MAJOR FEATURE RELEASE** 🚀

**Status**: 🎯 Milestone

#### Summary

- ✅ All 0.1.X features complete
- ✅ Leslie simulator
- ✅ Percussion system
- ✅ Advanced effects (Chorus, Tremolo)
- ✅ Preset management
- ✅ Visualization (Spectrum, Waveform)
- ✅ Multi-track recording
- ✅ Complete documentation
- ✅ Browser compatibility tested
- ✅ Performance optimized

#### Release Criteria

- [ ] All tests pass
- [ ] CPU usage < 30% (average)
- [ ] Works on Chrome, Firefox, Safari, Edge
- [ ] Mobile-responsive UI
- [ ] Documentation complete
- [ ] User feedback incorporated

**📅 Target Date**: Q1 2026

---

## 📊 Development Statistics

### Current Progress

```
v0.0.1  ████████████████████ 100% ✅
v0.0.2  ████████████████████ 100% ✅
v0.0.3  ████████████████████ 100% ✅
v0.0.4  ████████████████████ 100% ✅
v0.0.5  ████████████████████ 100% ✅
...
v0.0.25 ████████████████████ 100% ✅
v0.1.0  ████████████████████ 100% ✅ RELEASED
v0.1.1  ████████████████████ 100% ✅ RELEASED
v0.1.2  ░░░░░░░░░░░░░░░░░░░░   0% 📝
```

### Version Count

- **Completed**: 27 versions (0.0.1 - 0.1.1)
- **Planned**: 9 versions (0.1.2 - 0.2.0)
- **Total Roadmap**: 36 versions

### Lines of Code Evolution

```
v0.0.1:  ~80   lines
v0.0.5:  ~200  lines
v0.0.10: ~350  lines
v0.0.15: ~500  lines
v0.0.20: ~650  lines
v0.1.0:  ~720  lines
v0.1.1:  ~888  lines (current) ✨
v0.2.0:  ~1200 lines (estimated)
```

---

## 🎯 Priority Matrix

### High Priority (Must Have) ⭐⭐⭐⭐⭐

- ✅ ~~Leslie Simulator (v0.1.1)~~ - **COMPLETED** 🎉
- Percussion System (v0.1.2)
- Preset Save/Load (v0.1.5)

### Medium Priority (Should Have) ⭐⭐⭐⭐

- Chorus Effect (v0.1.3)
- Multi-track Recorder (v0.1.10)

### Low Priority (Nice to Have) ⭐⭐⭐

- Tremolo Effect (v0.1.4)
- Spectrum Analyzer (v0.1.6)
- Waveform Display (v0.1.7)

### Optional (Future) ⭐⭐

- MIDI Clock Sync (v0.1.8)

### Advanced (Research) ⭐

- Microtuning (v0.1.9)

---

## 🧪 Testing Checklist (לכל גרסה)

### Functional Tests

- [ ] תכונה חדשה עובדת כמצופה
- [ ] לא שובר תכונות קיימות
- [ ] UI responsive ונקי
- [ ] ללא console errors

### Browser Compatibility

- [ ] Chrome (latest)
- [ ] Firefox (latest)
- [ ] Safari (latest)
- [ ] Edge (latest)

### Performance

- [ ] CPU usage reasonable (<40%)
- [ ] Memory leaks checked
- [ ] Audio latency acceptable (<20ms)
- [ ] UI smooth (60 FPS)

### Code Quality

- [ ] Code documented
- [ ] Variables named clearly
- [ ] No magic numbers
- [ ] Error handling added

---

## 📝 Notes & Ideas

### Future Considerations

- **PWA Support**: Service worker, offline mode, install prompt
- **Cloud Sync**: Save presets to cloud (Firebase?)
- **Collaboration**: Multi-user jam sessions (WebRTC?)
- **Mobile App**: Native wrapper (Capacitor/Ionic?)
- **Plugin System**: User-created effects/instruments
- **AI Integration**: AI-powered harmonization, chord suggestions

### Technical Debt

- Consider migrating to TypeScript (type safety)
- Add unit tests (Jest?)
- Implement state management (Redux/Zustand?)
- Modularize code (ES modules)
- Build system (Webpack/Vite?)

### Community

- GitHub repository
- Discord server
- User forum
- Tutorial videos
- Live coding sessions

---

## 🏆 Milestones

| Milestone | Versions | Status | Date |
|-----------|----------|--------|------|
| 🎵 **Audio Core** | v0.0.1-0.0.4 | ✅ Complete | 2025-10 |
| 🎹 **Input & Control** | v0.0.2-0.0.12 | ✅ Complete | 2025-10 |
| 💾 **Recording System** | v0.0.13-0.0.15 | ✅ Complete | 2025-10 |
| 🎨 **UI/UX Polish** | v0.0.16-0.0.25 | ✅ Complete | 2025-10 |
| 🚀 **First Release** | v0.1.0 | ✅ Released | 2025-10-21 |
| 🌀 **Leslie Simulator** | v0.1.1 | ✅ Released | 2025-10-21 |
| 🎛️ **Advanced Effects** | v0.1.2-0.1.4 | 📝 Planning | 2026-Q1 |
| 📊 **Visualization** | v0.1.6-0.1.7 | 📝 Planning | 2026-Q1 |
| 🎼 **Advanced MIDI** | v0.1.8-0.1.10 | 📝 Planning | 2026-Q1 |
| 🚀 **Major Release** | v0.2.0 | 🎯 Milestone | 2026-Q1 |

---

## 📞 Development Contact

**Lead Developer**: AnLoMinus  
**Organization**: SparKing Lab  
**Project**: KeySpark Engine  
**Repository**: ToneLab  

---

<div align="center">

**נוצר עם ❤️ למען מוזיקה וקוד פתוח**

🎹 KeySpark · ✨ GlowTune UI · 🧪 ToneLab

[README](README.md) | [CHANGELOG](CHANGELOG.md) | **TODO**

</div>
