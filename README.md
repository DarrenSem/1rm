# 1rm
1 Rep Max calculator, simple Vanilla JavaScript (no React or other libraries)

https://darrensem.github.io/1rm/

### TODO:

✅️ link to GHP on the main repo (missing in mobile?)

✅️ change CSS to fix content column width, since data entry triggers zooming in which makes it so we can't see the instant results (until we zoom out again) 😠

🔲 (doubtful, in hindsight) check URL for querystring key "b*" (for Brzycki) to use a different equation, otherwise default to Epley formula
```js
epley = (weight, reps) => (reps < 2) ? weight : weight * (1 + reps / 30);
epleyWeightFrom1RM = (oneRepMax, reps) => (reps < 2) ? oneRepMax : oneRepMax / (1 + reps / 30);

brzycki = (weight, reps) => (reps < 2) ? weight : weight / (1.0277777777777777 - (0.0277777777777777 * reps));
brzyckiWeightFrom1RM = (oneRepMax, reps) => (reps < 2) ? oneRepMax : oneRepMax * (1.0277777777777777 - (0.0277777777777777 * reps));
// perhaps use Brzycki with fractional parts:
brzycki_F = (weight, reps) => (reps < 2) ? weight : weight * (36 / (37 - reps));
// ^ seems logical because 37/36 = 1.0277777777777777... that is the version found @ https://www.vcalc.com/wiki/brzycki
brzyckiWeightFrom1RM_F = (oneRepMax, reps) => (reps < 2) ? oneRepMax : oneRepMax * ((37 - reps) / 36);
// BUT, Epley is "scaleable" while Brzycki seems to be not very useful at 13+ reps (and it of course becomes _Infinitely_ NONSENSICAL at 37)
```

