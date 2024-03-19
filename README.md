# Olive-dresser
Do you feel my heart?

![buh](https://github.com/nicolasbaez/Olive-dresser/blob/main/xp030.gif)
```javascript
setup = (_) => createCanvas((w = 500), w, WEBGL);
draw = (_) => {
  h = w / 2;
  rotateX(w);
  clear();
  c = noise(w) * h;
  stroke(c, 0, h - c);
  beginShape(TRIANGLES);
  for (i = 0; i <= PI; i += 0.05)
    for (j = 0; j < 2 * PI; j += 0.05) {
      r = noise(i, j, w) * w * 0.5;
      vertex(r * sin(i) * cos(j), r * sin(i) * sin(j), r * cos(i));
    }
  endShape();
  w -= 0.01;
};

keyPressed = (_) => {
  if (key === "s") {
    saveGif("xp030.gif", 628, { delay: 0, units: "frames" });
  }
};
