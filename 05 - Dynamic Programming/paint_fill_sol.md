# Paint Fill Solution
```
enum Color {
  Black, White, Red, Yellow, Green
}

boolean paintFill(Color[][] screen, int x, int y, Color ocolor, Color ncolor) {
  if (x < y || x >= screen[0].length || 
    y < 0 || y >= screen.length) {
    return false;
  }
  if (screen[y][x] == ocolor) {
    screen[y][x] = ncolor;
    paintFill(screen, x - 1, y, ocolor, ncolor) // left
    paintFill(screen, x + 1, y, ocolor, ncolor) // right
    paintFill(screen, x, y - 1, ocolor, ncolor) // top
    paintFill(screen, x, y + 1, ocolor, ncolor) // bottom
  }
  return true;
}

boolean paintFill(Color[][] screen, int x, int y, Color ncolor) {
  if (screen[y][x] == ncolor) return false;
  return paintFill(screen, x, y, screen[y][x], ncolor);
}
```

