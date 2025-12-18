# Qaida Project - Development Notes

## Project Context

Interactive Qaida app for a 6-year-old learning Arabic (non-native speaker) to prepare for Quran reading. Parent-guided learning with mother.

## Key Decisions

- **Single HTML file** - No build process, just serve and use
- **No progress tracking** - Fresh each session, per user preference
- **Long-press to mark practice items** - Visual bookmark for items child struggles with
- **RTL layout** - Arabic reads right-to-left
- **Removed letter forms lesson** - User didn't want isolated/initial/medial/final forms displayed

## Ahsanul Qawaid Curriculum Reference

Full curriculum has 29 lessons (source: equranschool.com):
- Lessons 1-3: Letters and forms
- Lessons 4-6: Fatha, Kasra, Damma
- Lessons 7-9: Tanween (Fathatain, Kasratain, Dammatain)
- Lessons 10-19: Madd, Sukoon, Leen letters
- Lessons 20-29: Tashdeed, Shaddah combinations, advanced rules

**Currently implemented:** Lessons 1, 4-9 equivalent (letters + harakat + tanween)

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
- Practice items stored in JavaScript Set (not persisted)

## Session History

**2025-12-17:** Initial build
- Created 7-lesson structure
- Implemented long-press practice marking
- Fixed RTL direction for Arabic content
- Added tanween lessons per user request
