
MOTION (test phase)
Animations live in the "Motion" CSS block at the end of the <style> tag and the last <script> block in index.html.
Delete both to switch them off. All motion is disabled for visitors who prefer reduced motion.
Effects: staggered load-in, scroll reveals, hero photo parallax, scroll progress bar, active nav underline,
tilt + zoom on wedding cards, magnetic buttons, wine-glass cursor (tilts as you move, spills if you move it too fast, refills when still; click to clink; hold still and a bottle appears to top you up, move and a waiter strolls in, stops to give you a look, then steals it, pulling one of 12 faces and quips each time; the censored swearing comes with a soft but clear bleep after the first click; about a third of visits a waitress storms in to fight him for the bottle), animated archive filtering, theme-toggle spin and color fade.

MUSIC PLAYER
Bottom-left player (play/pause, prev/next, seek, volume, mute). It tries to play at 27% volume the moment the page loads. If the browser blocks that, a speakeasy door appears: knocking (click, tap, Enter or Space) starts the music immediately, then a silhouette bouncer pulls the door open and steps aside.
Put MP3s in audio/ and edit the TRACKS list in the "MUSIC PLAYER" script near the bottom of index.html.
The last track is remembered; volume always starts at 27%. Only use music you own or have a license for.

CHEESE THIEVES
A wedge of cheese sits bottom-right. At random intervals a rat sprints in, swipes it and runs off (sometimes a second rat shows up too late). The cheese comes back a few seconds later.
Timings are in the "CHEESE THIEVES" script at the bottom of index.html (FIRST, EVERY, RESPAWN, SPEED, SECOND_ODDS). Disabled for visitors who prefer reduced motion.

WINE BAR DISPLAY
The wedding polaroids sit on a lacquered mahogany bar top with brass trim, a glass of red wine, a bottle, corks and wine-glass ring stains (CSS block "Wine bar display" in index.html; the bottle and corks are the .gf-prop elements).

BAR TOP IN 3D
The bar top is tilted slightly back into the room, with real wood grain, plank seams, knots, a thick brass-banded front edge and a floor shadow (CSS block "Bar top, in 3D" in index.html; change rotateX(2.6deg) to adjust the tilt).

THE LAB (feature test bench)
New section #lab (nav: "Lab") built by lab.css + lab.js. 15 demos: contact sheet + darkroom reveal, light-table loupe, before/after slider, film-strip scroll, bar-menu navigation + jukebox moods, recipe cards, bartender delivery, style quiz, client favorites -> email, venue map, booking calendar, photo of the day in the glass, shutter click + flash, photo-booth strip, secret door + cheese-thief rat.
All text/photos in it are placeholders. Set your email at the top of lab.js (HOST). To remove the Lab entirely: delete <section id="lab">, the Lab nav link, the lab.css <link> and the lab.js <script>.


FEATURES (added from the Lab; the Lab itself is gone)
------------------------------------------------------
Files: features.css + features.js (linked from index.html). Edit the CONFIG block at the top of features.js to change
your email, the map places, booked dates and the bar menu.

1. Contact sheet + darkroom: the Archive is a strip of film. Click a frame and it "develops" in the darkroom; swirl the cursor to
   clear the fog. Photos are listed in the FRAMES array in index.html (src, title, genre).
5. Bar menu: the site navigation itself is now a chalkboard-style bar menu pinned across the top of the page.
9. Favorites: heart any photo (archive, polaroids, viewer). The heart button in the nav opens "My picks" and mails the list to you.
10. Venue map: new "Where I've shot" section. Places are listed in PLACES in features.js.
11. Booking calendar: inside Contact. Put real unavailable dates in BOOKED and set DEMO_BOOKED=false (demo dates are made up).
15. Easter eggs: knock on the loose brick in the footer wall three times for the Back Room. The cheese-thief rat now also steals wedding polaroids.


WINE-GLASS CURSOR v2 (click clarity)
A ring + dot marker sits exactly on the pointer: that is the click point. The glass is drawn 16px right / 14px down (OFFX, OFFY
in the "Wine-glass cursor" block of the last-but-two <script>) so it never covers what you are about to click.
Over anything clickable the ring grows and turns red, the glass fades back, and a small label says what the click does
("Open photo", "Add to picks", "Develop photo", "Pick this date", link/button text...). Disabled things (booked or past dates)
and non-clickable photos stay neutral. Pressing shrinks the ring. CSS: "Cursor v2" block at the end of the <style> tag.
Labels: clickLabel() in the same script. Touch devices and reduced-motion visitors keep the normal cursor.


ENTRY DOOR AUDIO (knock + door)
audio/knock.mp3 is knocking only, 4.46 s (the "FBI! Open up!" voice was cut off the end). The door shakes once per knock for the
full 4.46 s (keyframes "gfKnockDoor", harder pounding shakes more). KNOCK_LEN in the gate script must equal the clip length in ms.
audio/door-open.mp3 (2.9 s, synthesized, no license needed) starts the instant the knocking ends and is timed to the door:
  +0.00 s peephole slides open   +0.55 s latch click + creak as the door cracks
  +1.00 s hinge creak as it swings wide   +2.10 s wooden thud as it reaches the stop
To use your own door sound, replace the file and adjust DOOR_DELAY / DOOR_VOL (same script). The FBI voice option was removed.


TICKET STUBS (Weddings section)
The wedding polaroids are now "Admit Two" tickets lying on the bar top: photo on the left, a perforated edge with punched notches,
then the number, family name, place and date. Hearts, the darkroom viewer on click, tilt, and the rat that steals one all still work.
CSS: "Ticket stubs" block at the end of the <style> tag. Ticket numbers are the <div class="tk-no"> lines in each <article>.
Per-photo crop: the object-position lines in that CSS block. On phones the ticket stacks (photo on top).

Archive pinboard: the archive grid is now cream polaroids pinned to a dark board (CSS block "Archive pinboard" in index.html). Only photos listed in FRAMES appear; wedding photos stay in the Weddings section.

Map: dark teal palette (complement of the red theme) in dark and light mode; CSS block "Map: teal" in index.html.

Map v4: real US Census boundaries (us-atlas states-10m): exact coast, Great Lakes, state lines and Hawaii inset, pre-projected into features.js (GEO). Hand-placed extras: mountain marks, city dots, labels, compass.

Taylors: added as ticket No. 005 in Weddings (images/hero.jpg, Cathedral Park, Portland · November 2025). It was removed from the archive list since it is a wedding photo, so the archive now shows only the portrait and the Editorial chip is gone until you add archive photos.

Wait staff swearing is now rare (about 1 in 100): see CURSE in index.html (0 = never, 1 = old behaviour).

Entry gate: the door is gone. The gate is now a neon OPEN sign (CSS "Entry gate" block + showGate() in index.html). One tap: the sign stutters on, its red glow floods the screen, then the room fades in (about 3.5s). The buzz uses the built-in synthesized neon sound; audio/knock.mp3 and audio/door-open.mp3 were removed because nothing uses them now.

Theme: the site always starts in dark mode (saved light preference is ignored; the toggle lasts only for the visit).

Bottle/waiter pacing: after each visit the bottle rests a random 8-25 seconds before it can come back (REST_MIN / REST_MAX in index.html).

Gallery buttons: "View gallery", "All wedding galleries" and "Browse the full archive" no longer jump to the top of the page. By default they open the photo viewer on the right photo. To link them to real gallery pages, paste the addresses into GALLERY_LINKS, WEDDINGS_URL and ARCHIVE_URL at the top of features.js (they open in a new tab).

Galleries: clicking a wedding (its photo or "View gallery") opens that wedding's own gallery with all its photos at once; click a photo to see it large, "All photos" returns. The darkroom/developer effect is gone from the viewer. Each wedding currently has one photo (its card photo). To add more, put the files in images/ and list them under that couple's name in GALLERY_PHOTOS at the top of features.js.

Ho Family gallery: images/ho-01..08.jpg (converted from Sony ARW, 2000px max) are listed in GALLERY_PHOTOS in features.js.
Sangils gallery: images/sangil-01..12.jpg; Taylors gallery: images/taylor-01..10.jpg (listed in GALLERY_PHOTOS in features.js).
Favicon: icons/ (favicon.svg, favicon.ico, PNG sizes) linked in index.html head. Logo = cream viewfinder corners around a red G.
Archive: portrait removed from FRAMES (still used in About). Board shows a "coming soon" note until you add photos to FRAMES.
Back Room: knock the loose brick in the footer wall 3 times, then enter a passcode. Edit BACKROOM at the top of features.js (default passcode: gunframe, empty shelf).
Sangils gallery now also has images/sangil-13..22.jpg.
Taylors gallery now also has images/taylor-11..17.jpg.
Sangils gallery: removed sangil-05.jpg (duplicate of the edited crying shot sangil-15.jpg).
Taylors taylor-11.jpg: house number retouched out.

== FINAL ROUGH DRAFT (Nov 18 2026) ==
Galleries: Le, Sandovals, Sangils (22), Ho (9), Taylors (18). Archive empty (coming-soon note). Back Room passcode: gunframe (empty shelf).
Favicon updated: round wine G (option 7).
