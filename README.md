# Cookoff

A live scoreboard and party app for a three-team cooking competition. Open it at https://hemenace.github.io/Cookoff/ on any phone or computer. Every device stays in sync.

## The competition

- Three teams, three kitchens, two hours on the clock.
- Each team makes an entree, a drink, and a dessert or side.
- Every team has to use fresh ginger, zucchini, canned cranberry sauce and cream cheese.
- Judges score each dish from 1 to 10, for a maximum of 30 points.
- Each person has a goal of 5 drinks. Every drink left unfinished costs the team 1 point.
- Every 15 minutes, each team spins the challenge wheel. A failed challenge costs 5 points.

## What the site does

**Leaderboard.** Live standings with each team's judges' total, drink count, spins and penalties.

**My team.** Pick your team to log drinks, write down your menu, and spin the challenge wheel.

**Challenge wheel.**
- Only one person per team can spin at a time, and everyone on that team watches the same spin.
- When the wheel lands, a popup shows the challenge and a description. It stays up until you tap Got it.
- Some challenges get given to another team. That team gets a banner across the top of their screen and a sound.
- Power 15 starts a 15-minute timer that plays a sound every minute so everyone takes a sip.
- Mark each challenge Done or Failed.

**Alerts.**
- The top of the screen flashes and chimes when a spin is due.
- Sound clips play for given challenges, Power 15 sips, wheel results and time running out.

**Judging.** Judges pick a 1 to 10 score for each dish. With more than one judge, the scores are averaged.

**Setup.**
- Start or pause the shared 2-hour clock.
- Set the number of judges.
- Edit the wheel slots and descriptions, and choose sounds.
- Clear the test data before the event.

**Discord layout.** Under Setup > This screen, a computer can leave the middle of the screen open for the Discord video window, with the app split on both sides. A size slider makes everything bigger or smaller. These settings only change the one device.

## How it's built

The whole app is one file, `index.html`, hosted on GitHub Pages. Scores, spins and the clock sync live through a free Firebase Realtime Database. The `sounds/` folder holds the audio clips.
