# triangle-algorithm
##You'll need
- [Processing 2.2.1](https://processing.org/)
- [Python Mode for Processing](https://github.com/jdf/processing.py)

Be sure to switch to the python mode, when you execute the given codes in Processing.

##triangle in circle
![](images/1.png) ![](images/2.png)  ![](images/3.png)





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