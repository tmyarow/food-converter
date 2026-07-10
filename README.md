# Grams ⇄ Calories

A one-screen converter for the ten foods I actually eat. Type grams, read calories.
Type calories, read grams.

**→ [tmyarow.github.io/food-converter](https://tmyarow.github.io/food-converter/)**

Built for a phone lying flat on a kitchen counter, which drove most of the decisions:
the keypad is part of the page rather than the OS keyboard, so it never slides up
over the answer and the keys are large enough to hit with a knuckle. Add it to your
home screen and it opens full-screen and works with no network.

Tap delete to backspace; press and hold it to clear.

## The numbers

Calories per 100 g of edible portion — what actually lands on the scale.

| Food | cal / 100 g | Basis |
|---|---:|---|
| Banana | 89 | USDA |
| Grapes | 69 | USDA |
| Strawberries | 32 | USDA |
| Blueberries | 57 | USDA |
| Mango | 60 | USDA |
| Pineapple | 50 | USDA |
| Canned corn, drained | 81 | USDA |
| Canned black beans, drained & rinsed | 118 | USDA |
| Avocado, Hass | 167 | USDA |
| Panko chicken tenders, air-fried | 175 | calculated, see below |

Three of these involved a judgment call.

**Chicken tenders — calculated, not looked up.** Nothing in USDA matches homemade
panko tenders, so this is built from the recipe. 450 g of raw tenderloin is 495 cal.
The flour, egg, and panko that *actually adhere* add roughly 70 g and 207 cal —
dredging discards most of what goes in the bowls, which is the step people skip.
The air fryer then drives off about 22% of the water, concentrating what remains.
That's 715 cal over ~408 g finished, or **175 cal / 100 g**. Confidence band is
160–190 depending on how heavily you bread them. Pan-frying instead lands near 220,
because panko drinks oil.

**Black beans are brand-sensitive.** 118 is USDA's regular canned, drained and
rinsed. Low-sodium cans come in at 91 — a 30% spread on the same food. Check the can.

**Corn is 81 drained.** Weighed with the packing liquid it's about 62, because
you're mostly weighing water.

## Editing the data

All ten values live in one array near the top of the `<script>` in `index.html`.
Change a number, commit, and Pages redeploys.

## Layout

Everything is static and dependency-free — no build step, no framework, no network
requests at runtime.

```
index.html            the whole app: markup, styles, logic
sw.js                 offline cache (network-first for the page)
manifest.webmanifest  home-screen install metadata
mockups/              the three design directions this was chosen from
```
