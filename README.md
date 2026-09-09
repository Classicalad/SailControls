# Sail Controls — an International 14 trim model

An interactive model of what every string on an i14 actually does to the shape of the
sails, and why the right answer changes as the breeze builds.

**[index.html](index.html)** — open it in any browser. Single file, no build
step, no dependencies. Fonts load from Google Fonts; everything else runs offline.

## What it does

Eleven controls drive a live aerodynamic model — nine on the rig, two on the kite:

| | |
|---|---|
| **Mainsheet** | leech tension and angle of attack together — the traveller-less problem |
| **Boom vang** | leech tension independent of sheet angle; bends the mast |
| **Cunningham** | drags the draft forward against what load does to it |
| **Outhaul** | depth in the bottom third |
| **Jib sheet** | angle of attack, jib leech, and slot width |
| **Jib lead** | how load splits between leech and foot |
| **Cap shrouds** | overall rig tension → forestay sag; compression → bend |
| **Lowers (mid-mast)** | how far the middle of the mast can bow forward |
| **Forestay** | length, so rake — and it bleeds tension back out of the caps |
| **Kite sheet** | flown on the edge of collapse: ease to the curl, then stop |
| **Kite tack line** | how high the tack floats — projected area deep, straight luff reaching |

The kite is up on Reaching and Downwind and stowed Upwind, where its two controls
grey out.

There is deliberately no kite halyard control. It is two-blocked and stays there — an
asymmetric tensions its luff between head and tack, so anything less just lets the luff
sag. Easing the halyard to fly the sail clear of the rig is a symmetric-kite technique
from boats that genuinely run dead square, and it does not transfer to a skiff.

Rig tension and rake are *derived*, not controls, because that is how the boat works: you
adjust three wires and those two things are what you are left with.

Two views: the rig in side elevation (mast bend against a straight reference, forestay sag,
standing rigging, boom angle, luff wrinkles, foot depth) and three horizontal slices seen
from above at head, middle and foot — camber, draft position, twist, the apparent wind
angle at that height, and a leech telltale that streams, hooks or lifts.

Every slider carries a target mark for the current breeze. Drag the wind slider and watch
all nine marks migrate. That migration is the point of the whole thing.

### The demonstration

Set your trim for ten knots, press **Let the breeze build**, and touch nothing. The wind
ramps to 22 with every string frozen:

> Draft has walked from 46% to 55% aft, the leech has gone from 8.1° to 16.0° of twist, and
> you are holding 254% of what two people on the wire can carry.

Then **Now re-tune it** puts the draft back to 47%, camber from 11.2% to 8.8%, and the load
from 325% down to 223%. Same wind, same sails. That is the argument for tension, and it
falls out of the model rather than being asserted.

## About the model

Simplified relationships chosen so the couplings between controls are visible and correct
in direction — pressure scales with wind², load moves draft aft and opens the leech, sag
rounds the jib entry, mast bend flattens the lower main and takes luff round out of it,
tension holds shape. It is not a velocity prediction program.

The kite is flown the way a kite is actually flown. Nothing in the code says "ease to
the curl" — but run a search for the fastest kite trim at any wind speed and it lands on
a luff angle about 2-3° below the collapse point, in every mode, every time. Downwind the
binding constraint is not heel but burying the bow, and the model is built that way.

It was checked numerically rather than by eye. At the recommended settings across 4–25
knots, draft stays pinned near 46% while camber falls 11.9% → 7.6% and twist traces a U
(10.2° light, 7.8° powered, 21.2° survival) — the U is emergent, not hardcoded. A
coordinate search confirms the coaching advice sits within ~7% of the model's own optimum
in every mode and wind strength, so the score and the advice never contradict each other.
The righting limit is calibrated so the boat is fully powered around 12 knots and
overpowered from about 14.

**Absolute numbers are illustrative.** It is a development class and every 14 is rigged
differently. Take the directions from this and the numbers from your own tuning chart.
