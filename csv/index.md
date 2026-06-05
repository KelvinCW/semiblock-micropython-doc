# CSV files

**CSV** (comma-separated values) is a simple spreadsheet-style text format: each
line is a row, and commas separate the columns. The CSV category has blocks for
reading a file into a list, writing rows out, and appending new rows.

The blocks open a file and use Python's built-in `csv` module (imported inside the
`with` block for you). File-name fields are inserted **verbatim**, so quote them
(e.g. `"data.csv"`).

## What you will learn

- [Read, write, append](read-write.md)

## A quick taste

```python
with open("log.csv", "a", newline='') as file:
	import csv
	writer = csv.writer(file)
	writer.writerow(["val1", "val2"])
```

## Next

Continue to [Read, write, append](read-write.md)
