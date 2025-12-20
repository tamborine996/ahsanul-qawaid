# Qaida Project - Development Notes

## Project Context

Interactive Qaida app for a 6-year-old learning Arabic (non-native speaker) to prepare for Quran reading. Parent-guided learning with mother.

## Key Decisions

- **Single HTML file** - No build process, just serve and use
- **Progress tracking** - Completed lessons saved to localStorage
- **Explicit icon actions** - Speaker icon for audio, star icon for bookmarking (replaced tap/hold)
- **Tap card = show transliteration** - Safe exploration without accidental sounds
- **RTL layout** - Arabic reads right-to-left
- **Compact header navigation** - Lesson number with prev/next arrows, hamburger menu for full list
- **PWA support** - Installable, works offline
- **ElevenLabs audio** - Pre-recorded MP3s (no browser TTS fallback)

## Ahsanul Qawaid Curriculum Reference

Full curriculum has 29 lessons (source: equranschool.com):
- Lessons 1-3: Letters and forms
- Lessons 4-6: Fatha, Kasra, Damma
- Lessons 7-9: Tanween (Fathatain, Kasratain, Dammatain)
- Lessons 10-19: Madd, Sukoon, Leen letters
- Lessons 20-29: Tashdeed, Shaddah combinations, advanced rules

**Currently implemented:** Full curriculum - Lessons 3-30 (all content from physical book)

## Audio System

**Current implementation:** ElevenLabs TTS with Hanafi voice (Egyptian educational)
- Voice ID: `DWMVT5WflKt0P8OPpIrY`
- Model: `eleven_multilingual_v2`
- Files stored in `audio/` folder as hex-encoded MP3s
- Mapping in `audio-mapping.json`

**Audio coverage:**
- Lesson 1: 29 letter names (using English transliteration for correct pronunciation)
- Lesson 2: 16 Fatha exercise words
- Lessons 3-29: Not yet generated

**Key learning:** ElevenLabs pronounces letter names better with English input ("Laam", "Seen") rather than Arabic script (لَام, سِين)

**Generation scripts (not committed):**
- `generate-lesson1-english.js` - Letter names
- `generate-lesson2.js` - Fatha words
- `generate-all-audio.js` - All 842 sounds (ready to run)
- `arabic-sounds.json` - Full list of sounds needed

**ElevenLabs free tier:** 10,000 characters/month. Full curriculum ~4,768 characters.

## Technical Notes

- Uses Google Fonts: Amiri (Arabic), Quicksand (UI)
- Color scheme: Teal/gold/coral Islamic-inspired palette
- Long press duration: 500ms
- Practice items stored in JavaScript Set (session only)
- Progress tracking via localStorage
- Chunk size: 10 exercises per page
- Auto-hide transliteration after 2 seconds

## Deployment

- **Live URL:** https://tamborine996.github.io/ahsanul-qawaid/
- **Repository:** https://github.com/tamborine996/ahsanul-qawaid

## Session History

**2025-12-17:** Initial build
- Created 7-lesson structure
- Implemented long-press practice marking
- Fixed RTL direction for Arabic content
- Added tanween lessons per user request

**2025-12-18:** Full curriculum implementation
- Analyzed 27 WhatsApp images of physical Ahsanul Qawaid book
- Implemented all 28 lessons (3-30) with complete exercise data
- Added tap-to-reveal transliteration (hidden by default per user request)
- Added Practice Mode with fullscreen cycling navigation
- Added shuffle mode for randomizing exercises
- Added chunked exercises (10 per page with pagination)
- Added child-friendly "kidTip" explanations for each lesson
- Added progress tracking via localStorage
- Deployed to GitHub Pages

**2025-12-19:** Major UX overhaul
- Added Lesson 1 (Arabic Alphabet) with all 29 letters
- Renumbered lessons sequentially (1-29)
- Fixed Alif transliteration (added `sound` property to letters array)
- Added Web Speech API for TTS audio
- **Replaced tap/hold with explicit icons:**
  - 🔊 Speaker icon = play audio
  - ⭐ Star icon = bookmark for practice
  - Tap card = show transliteration (safe exploration)
- Grouped lessons into 7 collapsible categories with progress tracking
- Added onboarding overlay for first-time users
- Added celebration animation (confetti) on lesson completion
- Fixed practice mode: separate Hear/Show/Remove buttons below card
- Added PWA support (manifest.json, sw.js) for offline use
- Updated footer with icon legend

**2025-12-20:** Audio integration & navigation simplification
- Replaced grouped lesson navigation with compact header nav (◀ 1/29 ▶)
- Added hamburger menu (☰) with slide-out lesson list
- Integrated ElevenLabs audio (Hanafi voice) for Lessons 1-2
- Lesson 1: Letter names use English transliteration for correct pronunciation
- Disabled browser TTS fallback - only pre-recorded MP3s play
- Service worker cache versioning for updates (currently v6)
