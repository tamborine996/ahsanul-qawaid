# Ahsanul Qawaid - Interactive Arabic Learning

An interactive web app for children learning to read Arabic in preparation for Quran recitation.

**Live App:** https://tamborine996.github.io/ahsanul-qawaid/

## Overview

Based on the Ahsanul Qawaid methodology, this app covers the complete curriculum in 29 lessons organized into 7 categories:

- **Letters** - Arabic alphabet (29 letters)
- **Basic Vowels** - Fatha, Kasra, Damma
- **Tanween** - Fathatain, Kasratain, Dammatain
- **Madd (Stretching)** - With Alif, Waw, Ya + standing vowels
- **Sukoon & Leen** - No-vowel marks and soft letters
- **Shaddah** - Doubling letters
- **Advanced Rules** - Phrases, Noon Sakin, Waqf, Huroof Muqatta'at

## Features

- **29 Lessons** - Complete Ahsanul Qawaid curriculum
- **Grouped navigation** - Lessons organized into collapsible categories with progress
- **Audio playback** - Tap the 🔊 speaker icon to hear pronunciation
- **Practice bookmarks** - Tap the ⭐ star icon to save items for practice
- **Tap-to-reveal** - Tap any card to see the transliteration
- **Practice Mode** - Fullscreen review of bookmarked items with Hear/Show/Remove buttons
- **Celebration** - Confetti animation when completing lessons
- **Shuffle mode** - Randomize exercise order
- **Progress tracking** - Completed lessons saved automatically
- **PWA support** - Installable, works offline
- **Mobile-friendly** - Works on phones, tablets, and computers

## How to Use

1. **Open the app** at https://tamborine996.github.io/ahsanul-qawaid/
2. **First-time users** see an onboarding screen explaining the icons
3. **Expand a category** (Letters, Basic Vowels, etc.) to see lessons
4. **Select a lesson** to start learning
5. **Tap any card** to see how it's pronounced (transliteration)
6. **Tap 🔊** (speaker icon) to hear the audio
7. **Tap ⭐** (star icon) to bookmark items for practice
8. **Click "Practice"** to review all bookmarked items
9. **Click "Shuffle"** to randomize the exercise order
10. **Mark as Complete** to celebrate and track progress

## Running Locally

```bash
cd Qaida
npx serve
```

Then open http://localhost:3000

## Lessons

| Category | Lessons | Topics |
|----------|---------|--------|
| Letters | 1 | Arabic Alphabet (29 letters) |
| Basic Vowels | 2-4 | Fatha, Kasra, Damma |
| Tanween | 5-7 | Fathatain, Kasratain, Dammatain |
| Madd (Stretching) | 8-14 | Madd with Alif/Waw/Ya, Standing vowels, Sukoon |
| Sukoon & Leen | 15-17 | Sukoon combinations, Silent letters, Hamzah |
| Shaddah | 18-19 | Doubling letters |
| Advanced Rules | 20-29 | Madd rules, Phrases, Noon Sakin, Waqf, Huroof Muqatta'at |

## Future Work

- Professional audio recordings (current TTS has limitations with complex Arabic)
