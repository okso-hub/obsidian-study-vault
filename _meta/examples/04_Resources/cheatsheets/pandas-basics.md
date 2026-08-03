---
type: note
status: active
created: 2026-09-20
tags: [python, pandas, cheatsheet]
moc: ["[[programming]]"]
---

# Pandas — daily-driver cheatsheet

## Loading
```python
import pandas as pd
df = pd.read_csv("data.csv", parse_dates=["date"], dtype={"id": "int32"})
```

## Inspect
```python
df.info()            # types + null counts
df.describe()        # numeric summary
df.head(); df.sample(5)
df.memory_usage(deep=True) / 1e6   # MB per column
```

## Selection
```python
df.loc[:, ["a", "b"]]          # by label
df.iloc[10:20, :3]             # by position
df.query("a > 5 and b == 'x'") # readable filter
df[df["a"].isin([1, 2, 3])]
```

## Group / aggregate
```python
df.groupby("category").agg(
    mean_price=("price", "mean"),
    n=("id", "count"),
).reset_index()
```

## Joins
```python
pd.merge(left, right, on="id", how="left", validate="many_to_one")
```

## Common gotchas
- `SettingWithCopyWarning` → use `.loc[]` on the left side.
- `df.apply()` is slow on rows — try `.map()`, `.replace()`, vectorised NumPy instead.
- `pd.NA` vs `np.nan` — inconsistent behaviour across dtypes; stick to one.
