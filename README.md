# triangle-algorithm
##You'll need
- [Processing 2.2.1](https://processing.org/)
- [Python Mode for Processing](https://github.com/jdf/processing.py)

Be sure to switch to the python mode, when you execute the given codes in Processing.

##triangle in circle
![](images/1.png) ![](images/2.png)  ![](images/3.png)
```python
wdth=500
hght=500
x1=100
y1=100
x2=250
y2=350
x3=450
y3=100
outsideRadius = 150
insideRadius = 100

c=color(int(random(0,255)),int(random(0,255)),int(random(0,255)),50)

def setup():
    size(wdth,hght)
    background(205)
    x = wdth / 2
    y = hght / 2

def draw() :
 
    numPoints = int(map(mouseX, 0, width, 6, 60))
    angle = 109
    angleStep = 360.0 / numPoints

    beginShape(TRIANGLE_STRIP)
    for i in range(numPoints):
        x = width / 2
        y = height / 2
        px = x + cos(radians(angle)) * outsideRadius
        py = y + sin(radians(angle)) * outsideRadius
        angle += angleStep
        vertex(px, py)
        px = x + cos(radians(angle)) * insideRadius
        py = y + sin(radians(angle)) * insideRadius
        vertex(px, py)
        angle *= angleStep*100
    endShape()

def mousePressed():
    redraw()
```




##triangle stripes
![](images/a.png) ![](images/b.png)  ![](images/c.png)
```python
outsideRadius = 150
insideRadius = 100

def setup():
    size(500, 500)
    background(204)
    x = width / 2
    y = height / 2

def draw():
    background(204)
    
    numPoints = int(map(mouseX, 0, width, 6, 60))
    angle = 109
    angleStep = 360.0 / numPoints

    beginShape(TRIANGLE_STRIP)
    for i in range(numPoints):
        x = width / 2
        y = height / 2
        px = x + cos(radians(angle)) * outsideRadius
        py = y + sin(radians(angle)) * outsideRadius
        angle += angleStep
        vertex(px, py)
        px = x + cos(radians(angle)) * insideRadius
        py = y + sin(radians(angle)) * insideRadius
        vertex(px, py)
        angle *= angleStep*100
    endShape()
```

###License

The MIT License (MIT)

Copyright (c) 2015 Rosaplankton

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
