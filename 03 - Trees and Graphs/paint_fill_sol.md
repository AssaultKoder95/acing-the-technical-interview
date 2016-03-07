# Paint Fill Solution

Flood fill Algorithm to implement fill() in paint

Idea: we replace the color of current pixel, then recur for 4 surrounding points. The following is detailed algorithm:
```
// A recursive function to replace previous color 'oldColor' at  '(x, y)'
// and all surrounding pixels of (x, y) with new color 'newColor' and
paintFill(screen[M][N], x, y, oldColor, newColor)
1) If x or y is outside the screen, then return.
2) If color of screen[x][y] is not same as oldColor, then return
3) Recur for north, south, east and west.
    paintFill(screen, x-1, y, oldColor, newColor);
    paintFill(screen, x+1, y, oldColor, newColor);
    paintFill(screen, x, y-1, oldColor, newColor);
    paintFill(screen, x, y+1, oldColor, newColor);
```

Java implementation:
```

boolean paintFill(int[][] screen, int x, int y, int oldColor, int newColor) {
  if (x < y || x >= screen[0].length ||
    y < 0 || y >= screen.length) {
    return false;
  }
  if (screen[y][x] == oldColor) {
    screen[y][x] = newColor;
    paintFill(screen, x - 1, y, oldColor, newColor) // left
    paintFill(screen, x + 1, y, oldColor, newColor) // right
    paintFill(screen, x, y - 1, oldColor, newColor) // top
    paintFill(screen, x, y + 1, oldColor, newColor) // bottom
  }
  return true;
}

boolean paintFill(int[][] screen, int x, int y, int newColor) {
  if (screen[y][x] == newColor) return false;
  return paintFill(screen, x, y, screen[y][x], newColor);
}
```
