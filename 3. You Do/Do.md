# You Do

Create four variables with the appropriate types to hold the following information:
- `x1` is `2`
- `x2` is `5`
- `y1` is `4`
- `y2` is `2`

In math class, we learn about the pythagorean method for calculating distance between two points `(x1, y1)` and `(x2, y2)`. This formula looks like this:

```
SQRT((x2-x1)^2 + (y2-y1)^2)
```

This calculates the diagonal distance between the two points. Run this calcuation and save it to a variable called `pythagoreanDistance`. Then print out the sentence `"The pythagorean distance between (#, #) and (#, #) is #."`.

In cities, we can't go diagonally because that would go through buildings, so we have another way to measure distance, which is called the **taxicab metric** (since this is the route a taxicab might want to follow). It is calculated as follows:

```
ABS(x2-x1) + ABS(y2-y1)
```

Run this calculation and save it to a variable called `taxicabDistance`. Then print out the sentence `"The taxicab distance between (#, #) and (#, #) is #."`.

Once you have gotten to just warnings, save the Java file and commit and push your changes via GitHub Desktop.
