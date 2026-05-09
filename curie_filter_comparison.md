# Curie Second-Filter Removal: Quick Results Comparison

This compares the GitHub version with the second field-stabilization filter against the current local version without that filter.

Definitions:

- With filter: `HEAD:curie/proc.py`, using the field-ready cut and a common retained field window.
- Without filter: current local `curie/proc.py`, using all loops and Method II evaluated per loop at `0.98 Hmax(T)`.

## Bottom Line

| Quantity | With filter | Without filter | Change |
|---|---:|---:|---:|
| Series A weighted method mean | 213.9 K | 197.7 K | -16.2 K |
| Report headline uncertainty | +/- 12.3 K | +/- 18.3 K | +6.0 K |
| Conservative all-drive envelope | +/- 19.6 K | +/- 26.1 K | +6.5 K |

Compared with the old report prose value `216(10) K`, the updated no-filter report value is `198(18) K`. The center moves down by about `18 K`, and the uncertainty increases.

## Series A Half-Height Methods

| Method | With filter | Without filter | Change |
|---|---:|---:|---:|
| M0 | 216.4 +/- 0.8 K | 196.9 +/- 1.8 K | -19.5 K |
| Msat | 214.8 +/- 1.0 K | 204.0 +/- 1.5 K | -10.8 K |
| M0_ext | 199.1 +/- 1.7 K | 169.4 +/- 3.3 K | -29.7 K |

## All-Series Method Means

| Series | With filter | Without filter | Change |
|---|---:|---:|---:|
| A | 213.9 K | 197.7 K | -16.2 K |
| B | 202.9 K | 196.0 K | -6.9 K |
| C | 236.5 K | 229.1 K | -7.3 K |

## Data Included

| Series | With filter loops and T range | Without filter loops and T range | Added loops |
|---|---:|---:|---:|
| A | 141 loops, 180.8-273.3 K | 172 loops, 82.9-273.3 K | +31 |
| B | 155 loops, 159.1-273.2 K | 179 loops, 83.1-273.2 K | +24 |
| C | 177 loops, 221.3-273.3 K | 251 loops, 110.7-273.3 K | +74 |

## Interpretation

Removing the second filter adds the early low-temperature loops back into the normalization. That changes the dynamic range of each normalized magnetization curve, so the half-height crossing shifts substantially lower.

The shift is largest in Series A and especially in the extrapolated-tail method (`M0_ext`). The no-filter version is therefore more conservative but less internally consistent: the method spread in Series A grows from `9.5 K` to `18.3 K`, which drives the larger final uncertainty.

Short version: the filtered version gives a higher and tighter transition estimate; the no-filter version gives a lower, broader estimate because it includes the early low-temperature loops instead of discarding them as field-settling data.
