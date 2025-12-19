# Qaida Project - Development Notes

## Project Context

Interactive Qaida app for a 6-year-old learning Arabic (non-native speaker) to prepare for Quran reading. Parent-guided learning with mother.

## Key Decisions

- **Single HTML file** - No build process, just serve and use
- **Progress tracking** - Completed lessons saved to localStorage
- **Explicit icon actions** - Speaker icon for audio, star icon for bookmarking (replaced tap/hold)
- **Tap card = show transliteration** - Safe exploration without accidental sounds
- **RTL layout** - Arabic reads right-to-left
- **Grouped lesson navigation** - 29 lessons organized into 7 collapsible categories
- **PWA support** - Installable, works offline

## Ahsanul Qawaid Curriculum Reference

Full curriculum has 29 lessons (source: equranschool.com):
- Lessons 1-3: Letters and forms
- Lessons 4-6: Fatha, Kasra, Damma
- Lessons 7-9: Tanween (Fathatain, Kasratain, Dammatain)
- Lessons 10-19: Madd, Sukoon, Leen letters
- Lessons 20-29: Tashdeed, Shaddah combinations, advanced rules

**Currently implemented:** Full curriculum - Lessons 3-30 (all content from physical book)

## Audio Resources Found

For future audio implementation:
- [Internet Archive - Arabic Alphabet Audio](https://archive.org/details/ArabicAlphabetAudio) - Audio embedded in PDF
- [Arabic Reading Course](https://www.arabicreadingcourse.com/learn-the-arabic-alphabet.php) - MP3 download available
- [eQuran School](https://www.equranschool.com/learn-arabic-alphabets) - Streaming audio

Note: Licensing unclear for most resources. For proper tajweed pronunciation, recording by a teacher may be preferable.

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
