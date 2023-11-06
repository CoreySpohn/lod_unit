# lod_unit
This is set up to make it easy to keep coronagraph information in λ/D space with an astropy unit called `lod`. It makes it easy to convert into angular units with an astropy Equivalency relationship `lod_eq`.

Typical use will look something like:
```
import astropy.units as u
from lod_unit.lod_unit import lod, lod_eq

diam = 10*u.m
lam = 500*u.nm
separation_lod = 3 * lod
separation_lod.to(u.arcsec, lod_eq(lam, diam))
>> <Quantity 0.03093972 arcsec>

separations_as = [0.1, 0.5, 1]*u.arcsec
separations_as.to(lod, lod_eq(lam, diam))
>> <Quantity [ 9.69627362, 48.48136811, 96.96273622] λ/D>
```
