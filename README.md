# lod_unit
This is set up to make it easy to keep coronagraph information in lambda/D space with an astropy unit called `lod`, while providing `lod_eq` an easy way to convert between angular units

Typical use will look something like
```
import astropy.units as u
from lod_unit.lod_unit import lod, lod_eq

diam = 10*u.m
lam = 500*u.nm
separation_lod = 3 * lod
separation_lod.to(u.arcsec, lod_eq(lam, diam))
>> <Quantity 0.03093972 arcsec>

separation_as = 0.1*u.arcsec
separation_as.to(lod, lod_eq(lam, diam))
>> <Quantity 9.69627362 lambda/D>
```

