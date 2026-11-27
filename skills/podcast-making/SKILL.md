---
name: podcast-making
description: Plan, script, record, edit, test and publish a podcast episode: technical settings, loudness, MP3 export, music rights and publishing. Use whenever someone mentions making a podcast or a podcast episode.
---

# Podcast making

A guide for making a podcast episode from idea to published file. It works for school projects, courses, company podcasts and hobby shows, for one host or several.

## 1. Ground rules

1. Start by asking: what is the podcast for (learning project, work, hobby), which phase is the user in, and what they want to begin with. Do not run through all phases on your own.
2. Learning mode: if the podcast is a school or course task, work WITH the user, not instead of them. Explain first, answer questions, let the user decide and do each step. Warn immediately about a dead end (editing in MP3, recording too loud, music without rights).
3. Production mode: if the user just wants the result, go faster, but still confirm each phase before moving on.
4. Write scripts and show notes in the language of the podcast and at the speaker's own language level, in spoken style.
5. Never delete recordings or takes. Move anything unwanted to a separate folder and let the user delete it.
6. Always lower the volume before playing test tones or a new export, especially with headphones.
7. Publishing is public: always ask before publishing, and let the user click Publish if they prefer.

## 2. Phases

### 2.1 Plan
- Topic, goal, target listener, length, format (solo, interview, conversation).
- Roles: who hosts, who brings which part. With several speakers, agree on the same technical settings before anyone records (see 3).
- Show name, episode name, season and episode number.

### 2.2 Script
- Structure: intro (jingle, who we are, what today), main parts, outro (thanks, credits, where to listen).
- Short sentences, spoken language. In learning mode the user writes or dictates; Claude corrects and explains.
- Add a credits line for music, sound effects and sources to the script and the show notes.

### 2.3 Record
- Quiet room, soft surfaces, same distance to the microphone for the whole recording.
- Test-read one sentence as in the episode and watch the meter: speech peaks about -12 to -6 dBFS. Green is good, yellow is near the top, red risks clipping.
- Too quiet: move closer or raise the input level in the system sound settings. Too loud: lower the input BEFORE recording. Clipping at 0 dBFS cannot be repaired.
- Do not plan to boost a quiet recording later: gain raises the background noise as much as the voice.
- Record at 24-bit (headroom) in a lossless format (WAV or the editor's own project format).
- Remote recording: each speaker records their own track locally if possible, with the same settings.

### 2.4 Edit
Examples use Audacity; the principles apply to any audio editor.
- Check that the project rate matches the chosen sample rate (in Audacity, bottom-left corner).
- Edit in lossless format only. Never edit an MP3 and export again: each lossy encode loses quality.
- Even out volume between parts and between voices by measuring LUFS, not by ear.
- Keep peaks below -1 dBFS.
- Voice frequency map for EQ: 80-250 Hz voice fundamentals and warmth; 2-5 kHz presence and consonants (intelligibility, do not cut); 5-20 kHz sibilance (S sounds). Laptop speakers cannot play below about 100 Hz, so check bass in headphones.

### 2.5 Music and sound effects
- Use only audio the user has the rights to. Podcast platforms remove episodes with audio the publisher has no rights to.
- Check the license of every track: commercial use allowed? Attribution required? Changes allowed?
- Example, Pixabay license: free, can be changed, attribution not required but appreciated. Not allowed: distributing the track as-is without creative work, use in a trademark or business name, misleading or illegal use. Content can still carry third-party rights; the user is responsible for checking.
- Good practice: credit artist, track and source in the show notes even when not required, and save the track page link and a screenshot of the license as proof of rights.

### 2.6 Export MP3
Export is the LAST step, from the lossless project. Audacity settings:
- Channels: Mono for speech. If both channels are identical, mix down to mono first for better quality at the same bitrate.
- Sample rate: the same as the project.
- Bit rate mode: Constant (CBR). Suits streaming and gives a predictable file size.
- Quality: 96 kbps mono (excellent speech) or 64 kbps mono (smaller file). If stereo music matters: 128 kbps CBR (reasonable) or 192 kbps CBR (very good).
- Do not use the default Preset/Standard (VBR, meant for stereo music).
- Keep embedded artwork and ID3 tags small.
- File size: bytes = bitrate x seconds / 8 (96 kbps x 600 s = 7.2 MB).

### 2.7 Test the file
Load the export in a file checker (Ljudlabbet part 5, see 4) and go through:
1. Format (MP3 or WAV gives the most information).
2. Bitrate: CBR or VBR, as intended?
3. Channels: mono, stereo or joint stereo.
4. Real length.
5. Integrated loudness: about -14 LUFS for Spotify, -16 LUFS for Apple Podcasts. Check the target of the platform you use.
6. Peak level: a few dB below 0 dBFS.
7. Clipping: any clipping marker means fix it in the project and export again.
8. Loudness over time: no big jumps between parts or voices.
Save the result (screenshot or copied text). After each change, export and test again.

### 2.8 Publish
Example, Spotify for Creators:
- The show must be hosted on Spotify; verify the account by email before the first episode.
- Formats: MP3, M4A or WAV, mono or stereo. No size limit, but big files process slower and can fail on a weak connection.
- Web: New episode > Select a file. Mobile: Podcast > + > Select a file.
- Details: title, description (show notes with credits), Content checks, under Additional details season and episode number and episode artwork.
- Publish date: Now, or Schedule (local time). Change a scheduled episode: web 3 dots > Revert to draft; mobile edit icon > Edit schedule. The X in the top-right corner saves a draft.
- Upload error: check the file type, that the file plays on the device, and browser support.
Other hosts work similarly; check their current help pages for formats and loudness targets.

### 2.9 Report (school or course projects)
Offer a short report: purpose, process, technical choices with reasons (sample rate, mono, bitrate, LUFS), rights for music, the file test result, reflection. Follow the format the school or course requires.

## 3. Technical reference

| Setting | Choose | Why |
|---|---|---|
| Sample rate | 44.1 kHz (audio only) or 48 kHz (with video); ONE rate everywhere | Both cover hearing to 20 kHz (Nyquist: max frequency < rate / 2). 8 kHz = telephone, too flat. 96 kHz = double size, no audible gain |
| Bit depth | 24-bit for recording, 16-bit enough for playback | About 6 dB dynamic range per bit (16-bit 96 dB, 24-bit 144 dB) |
| Channels | Mono for speech | Speech in mono needs about half the bitrate of stereo |
| Bitrate | 64-96 kbps CBR mono | Common for podcasts; music in stereo 128-256 kbps |
| Speech peaks | -12 to -6 dBFS | Headroom |
| Ceiling | below -1 dBFS | No clipping |
| Loudness | -14 LUFS Spotify, -16 LUFS Apple | Platforms normalise anyway; check each platform |

Three kinds of decibel: dB SPL (sound pressure in the room), dBFS (digital level, 0 = maximum, everything else negative), LUFS (perceived loudness over the whole episode).
Hearing safety: long exposure above about 85 dB(A) can damage hearing.

## 4. Sources and learning labs
For users who want to understand the theory, not just do the steps. The Ljudlabbet labs are in Swedish, run in the browser and send nothing anywhere; if a lab does not work, try Chrome.
- Ljudlabbet overview: https://ljudlabbet.vercel.app/
- 1 Frequency: https://ljudskolan.vercel.app/ljud/Ljudlabbet_1_Frekvens.html
- 2 Decibel: https://ljudskolan.vercel.app/ljud/Ljudlabbet_2_Decibel.html
- 3 Sample rate: https://ljudskolan.vercel.app/ljud/Ljudlabbet_3_Samplingsfrekvens.html
- 4 Bitrate: https://ljudskolan.vercel.app/ljud/Ljudlabbet_4_Bitrate.html
- 5 Test your file: https://ljudskolan.vercel.app/ljud/Ljudlabbet_5_Testa_din_ljudfil.html
- Audacity MP3 export options: https://manual.audacityteam.org/man/mp3_export_options.html
- Pixabay license summary: https://pixabay.com/service/license-summary/
- Spotify, publishing audio episodes: https://support.spotify.com/se/creators/article/publishing-audio-episodes/
