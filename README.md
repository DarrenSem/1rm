# 1rm-test
1 Rep Max calculator ugly proof of concept in Vanilla JavaScript

https://darrensem.github.io/1rm-test/

### TODO:

✅️ link to GHP on the main repo (missing in mobile?)

✅️ change CSS to fix content column width, since data entry triggers zooming in which makes it so we can't see the instant results (until we zoom out again) 😠

🔲 check URL for querystring key "b*" (for Brzycki) to use a different equation, otherwise default to Epley formula
```js
epley = (weight, reps) => (reps < 2) ? weight : weight * (1 + reps / 30);
epleyWeightFrom1RM = (oneRepMax, reps) => (reps < 2) ? oneRepMax : oneRepMax / (1 + reps / 30);

brzycki = (weight, reps) => (reps < 2) ? weight : weight / (1.0278 - 0.0278 * reps);
brzyckiWeightFrom1RM = (oneRepMax, reps) => (reps < 2) ? oneRepMax : oneRepMax * (1.0278 - 0.0278 * reps);
```
