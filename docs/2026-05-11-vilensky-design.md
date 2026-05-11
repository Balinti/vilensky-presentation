# Moshe Vilensky Presentation — Design Spec

**Date:** 2026-05-11
**Audience:** Adult community crowd, cultural evening
**Runtime:** 25-30 min
**Language:** Hebrew (slides + content). Code/dev docs in English.
**Output:** Standalone HTML deck, manually presented.

## Goals

Present Moshe Vilensky (1910-1997) and his songs with embedded audio so the presenter never has to leave the deck. Anecdotes lean piquant for an adult crowd: the Damari romance, the Polish-guy-writing-Yemenite-music paradox, professional rivalries, character quirks.

## Tech

- Plain HTML + CSS + vanilla JS, single `index.html`
- Navigate with ← / →, space = play/pause, F = fullscreen
- One slide per section, all in one file (no SPA routing)
- GSAP for slide-in animations (borrowed from hyperframes patterns)
- Audio: `<audio>` element per slide, autoplay on activation, stop on leave
- Works offline, fully portable

## File layout

```
vilensky-presentation/
├── index.html
├── styles.css
├── deck.js
├── songs/        # MP3 clips, 30-45s each, sourced via yt-dlp + ffmpeg
├── images/       # photos, posters, stamps
└── docs/
    └── 2026-05-11-vilensky-design.md
```

## Slide list (16 slides)

| # | Slide | Song | Anecdote angle |
|---|---|---|---|
| 1 | Cover | — | Title, dates, portrait |
| 2 | Warsaw → TA | — | Childhood, conservatory, immigration 1932 |
| 3 | HaMatatah era | — | Satirical theater, Alterman, marriage to Berta |
| 4 | כלניות (1944) | Damari | First Li-La-Lo hit, she was 20 |
| 5 | בכרם תימן | Damari | Polish guy writes Yemenite music |
| 6 | גדליה רבע איש | Matateh era | Pre-state satire |
| 7 | היו זמנים | Chizbatron | Army troupes, War of Independence touring |
| 8 | מול הר סיני (1956) | Damari | Suez crisis, national-mood music |
| 9 | כשהיינו ילדים | Yarkoni | The Yarkoni–Damari rivalry, he wrote for both |
| 10 | סתיו (1962) | Esther Ofarim | Won Sopot first prize, returned to Poland |
| 11 | The Damari romance | Damari signature | The open secret, husband's unsent letter |
| 12 | Radio years | Almagor song | Kol Israel 1961-78, "Edna Goren's number?" quip |
| 13 | פלאפל / playful side | playful song | Street food, neighborhoods, "I wish" McCartney |
| 14 | Late Damari reunion | Damari late | Partnership outlasted the romance |
| 15 | Stroke & silence | — | Lost piano, kept composing, died 1997 |
| 16 | Legacy | — | Israel Prize 1983, 1000+ songs, 2009 stamp |

## Visual style

Mix (option D): vintage/sepia for slides 1-3, 15-16 (bio + legacy); brighter, readable Hebrew sans-serif for song slides 4-14. RTL layout. Heebo for body, Frank Ruehl for vintage sections. Large photos, large song titles, anecdote body text comfortable to read from the back of a community room.

## Risks

- **Song availability:** yt-dlp + YouTube. Personal/educational use is standard but technically copyrighted material — clip length 30-45s mitigates.
- **Image rights:** Wikipedia/Wikimedia where possible. Period photos generally public-domain or commonly attributed.
- **Damari's daughter name:** Hebrew sources say נאוה (Nava); one English source said Naomi (likely error). Going with Nava.
- **Anecdote accuracy:** All anecdotes sourced from Wikipedia, Maariv, Mako articles. Where contested, will hedge in the slide language ("רומן שמעולם לא הוכח" / "סוד גלוי").

## Non-goals

- Self-playing video (presenter is human)
- TTS narration (presenter narrates)
- Backend / server (offline deck)
- Mobile responsiveness (presented on laptop/projector)
