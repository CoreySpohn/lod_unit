# lod_unit
This is set up to make it easy to keep coronagraph information in lambda/D space, while providing an easy way to convert to angular units

Typical use will look something like
```
import astropy.units as u
from lod_unit.lod_unit import lod, lod_eq

psf_separation = [10, 15]*lod

telescope_diameter = 10*u.m
wavelength = 500*u.nm
psf_separation.to(u.arcsec, lod_eq(wavelength, telescope_diameter))
```

