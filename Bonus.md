Load the file [exams.csv](https://gist.githubusercontent.com/l8doku/17179b523dde077b67834ca1a78edebf/raw/b21350957dabde120c3aca3f08cd63073c7f1b3b/exams.csv) into a data frame. Use this data frame in the following tasks.

The maximum number of points you can get for this task is 10.

However, scoring is not fixed. Quality of code matters, so just getting the correct result is not enough to get the maximum score. Splitting code into functions, increasing reusability and extensibility, good plot formatting (legends, axis labels, possibly animation) all lead to better scores.

Additionally, if you already have many points for workshops, solving this task may not be necessary for you. Points will be normalized at the end, so those who already have many points, will get a score close to maximum anyway.

## Task 1. Closest point.

You also have a list of 3 points with 3 numerical values:

```python
measurement_points = np.array([
    [60, 90, 40],
    [50, 60, 100],
    [30, 60, 80]
])
```

Use columns `math score`, `reading score` and `writing score` and find which of the measurement points is closest to each data point.

Create a new list and save indices of the closest measurement points in it for each corresponding data point.

A method `df.to_numpy()` might be useful in this task


## Task 2. Separate means.

Solve task 1 and get a list of closest measurement points.

Split your data into three groups corresponding to each measurement point.

Compute means of `math score`, `reading score` and `writing score` for each group separately.

Plot a scatterplot of `math score` and `reading score`. Draw the three groups in three different colors.

Draw mean points on the scatterplot as a separate type of marker. For example, points themselves may be dots `'.'` and the mean points may be squares `'s'`.

## Task 3. K-Means clustering.

Use the mean points from task 2 as new measurement points.

Repeat task 1 (finding closest points) and task 2 (finding means of separate groups) several times. Optionally, you may repeat this until means stop changing, but 5 times should be enough.

Plot 3 scatterplots:
1. `math score` vs `reading score`
2. `reading score` vs `writing score`
3. `math score` vs `writing score`

On all 3 plots mark the final groups with colors.
