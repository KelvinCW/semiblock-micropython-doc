# Read, write, append

These three blocks move data between your program and a CSV file. File-name
fields are inserted **verbatim**, so quote them (e.g. `"data.csv"`).

## The `csvRead` block

- **Label:** read a CSV into a list.
- **Inputs:** `varName` (default `data`), `fileName` (default `file.csv`).

It collects every row into a list named by `varName`:

```python
data = []
with open(file.csv, 'r') as file:
	import csv
	reader = csv.reader(file)
	for row in reader:
		data.append(row)
```

With a quoted file name (`"file.csv"`) each `row` is itself a list of column
values.

## The `csvWrite` block

- **Label:** write rows to a CSV (replacing the file).
- **Inputs:** `fileName` (default `file.csv`), `data` (default
  `[["col1", "col2"], ["val1", "val2"]]`).

It writes a list of rows all at once:

```python
with open(file.csv, 'w', newline='') as file:
	import csv
	writer = csv.writer(file)
	writer.writerows([["col1", "col2"], ["val1", "val2"]])
```

## The `csvAppend` block

- **Label:** add a single row to the end of a CSV.
- **Inputs:** `fileName` (default `file.csv`), `data` (default
  `["val1", "val2"]`).

```python
with open(file.csv, 'a', newline='') as file:
	import csv
	writer = csv.writer(file)
	writer.writerow(["val1", "val2"])
```

## Worked example

With quoted file names:

```python
with open("log.csv", "w", newline='') as file:
	import csv
	writer = csv.writer(file)
	writer.writerows([["time", "temp"], ["10:00", "21"]])

data = []
with open("log.csv", 'r') as file:
	import csv
	reader = csv.reader(file)
	for row in reader:
		data.append(row)
print(data)
```

> Tip: `writerows` (plural) takes a list of rows; `writerow` takes one row. Use
> append to add readings over time without erasing old data.

## Next

Continue to [Hardware](../hardware/index.md)
