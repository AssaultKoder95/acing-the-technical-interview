# Paint Fill
Implement the "paint fill" function that one might see on many image editing programs. That is, given a screen (represented by a two dimensional array of colors), a point, and a new color, fill in the surrounding area until the color changes from the original color

Input:
```
       screen[M][N] = {{1, 1, 1, 1, 1, 1, 1, 1},
                      {1, 1, 1, 1, 1, 1, 0, 0},
                      {1, 0, 0, 1, 1, 0, 1, 1},
                      {1, 2, 2, 2, 2, 0, 1, 0},
                      {1, 1, 1, 2, 2, 0, 1, 0},
                      {1, 1, 1, 2, 2, 2, 2, 0},
                      {1, 1, 1, 1, 1, 2, 1, 1},
                      {1, 1, 1, 1, 1, 2, 2, 1},
                      };
x = 4, y = 4, newColor = 3
The values in the given 2D screen indicate colors of the pixels.
x and y are coordinates of the brush, newColor is the color that
should replace the previous color on screen[x][y] and all surrounding
pixels with same color.
```
Output:
```
Screen should be changed to following.
       screen[M][N] = {{1, 1, 1, 1, 1, 1, 1, 1},
                      {1, 1, 1, 1, 1, 1, 0, 0},
                      {1, 0, 0, 1, 1, 0, 1, 1},
                      {1, 3, 3, 3, 3, 0, 1, 0},
                      {1, 1, 1, 3, 3, 0, 1, 0},
                      {1, 1, 1, 3, 3, 3, 3, 0},
                      {1, 1, 1, 1, 1, 3, 1, 1},
                      {1, 1, 1, 1, 1, 3, 3, 1},
                      };
```
