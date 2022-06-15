# CSS Transforms

The *transform* property comes in two different settings, two-dimensional and three-dimensonial. Each of these come with their own individual properties and values. 

**Transform Syntax**

transform property followed by the value. For example: 

```
div {
    -webkit-transform: scale(1.5);
     -moz-transform: scale(1.5);
       -o-transform: scale(1.5);
          transform: scale(1.5);
}
```
the transform property has multiple vendor prefixes to gain the best support across all browsers. The un-prefixed declaration comes last to overwrite the prefixed versions, should a browser fully support the transform property. 

# 2D Transforms

Elements may be distorted, or transformed, on both a 2 dimensional plane or 3 dimensional plane. 2D transforms work on the x and y axes, known as horizontal and vertical axes. 3D transforms work on both the x and y axes, as well as the Z axis. These 3D transforms help define not only the length and width of an element, but also the depth. We'll start by discussing how to transform elements on a 2D plane and then on 3D planes. 

**2D rotate**

The rotate value provides the ability to rotate an element from 0 to 360 degrees. Using a positive value will rotate an element clockwise, and using a negative value will rotate the element counterclockwise. The default point of rotation is the center of the element, 50% 50%, both horizontally and vertically. Later we will discuss how you can change this default point of rotation.

HTML: 
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS:
```
.box-1 {
  transform: rotate(20deg);
}
.box-2 {
  transform: rotate(-55deg);
}
```

**2D scale**

Using the scale value within the transform property allows you to change the appeared size of an element. The default scale value is 1, therefore any value between .99 and .01 makes an element appear smaller while any value greater than or equal to 1.01 makes an element appear larger.

HTML: 
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
```

CSS:
```
.box-1 {
  transform: scale(.75);
}
.box-2 {
  transform: scale(1.25);
}
```

It is possible to scale only the height or width of an element using the *scaleX and scaleY* values. The scaleX value will scale the width of an element while the scaleY value will scale the height of an element. To scale both the height and width of an element but at different sizes, the x and y axis values may be set simultaneously. To do so, use the scale transform declaring the x axis value first, followed by a comma, and then the y axis value. For example: 

HTML: 
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

CSS:
```
.box-1 {
  transform: scaleX(.5);
}
.box-2 {
  transform: scaleY(1.15);
}
.box-3 {
  transform: scale(.5, 1.15);
}
```
**2D Translate**

The translate value works a bit like that of relative positioning, pushing and pulling an element in different directions without interrupting the normal flow of the document. Using the translateX value will change the position of an element on the horizontal axis while using the translateY value will change the position of an element on the vertical axis.

As with the scale value, to set both the x and y axis values at once, use the translate value and declare the x axis value first, followed by a comma, and then the y axis value.

The distance values used within the translate value may be any general length measurement, most commonly pixels or percentages. Positive values will push an element down and to the right of its default position while negative values will pull an element up and to the left of its default position.

HTML: 
```
<figure class="box-1">Box 1</figure>
<figure class="box-2">Box 2</figure>
<figure class="box-3">Box 3</figure>
```

CSS:
```
.box-1 {
  transform: translateX(-10px);
}
.box-2 {
  transform: translateY(25%);
}
.box-3 {
  transform: translate(-10px, 25%);
}
```

**2D Skew**

The last transform value in the group, skew, is used to distort elements on the horizontal axis, vertical axis, or both. The syntax is very similar to that of the scale and translate values. Using the skewX value distorts an element on the horizontal axis while the skewY value distorts an element on the vertical axis. To distort an element on both axes the skew value is used, declaring the x axis value first, followed by a comma, and then the y axis value.%p

The distance calculation of the skew value is measured in units of degrees. Length measurements, such as pixels or percentages, do not apply here.