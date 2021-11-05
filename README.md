# Image Manipulations

Today we will be learning about the `tint` function in p5 and how we can use a slider to adjust the images that we are creating!

`tint(v1, v2, v3, [alpha])` causes the image to be drawn with a color fill. `v1`, `v2`, and `v3` represent the RGB values between 0 and 255. `alpha` is an optional transparency value between 0 and 255.

```javascript
var img

function preload() {
	img = loadImage(“rabbit.png”)
}

function draw() {
	// Adjusts the tint to be greenish-blue
	tint(0, 153, 204)
	image(img, 50, 50, 100, 200)
}
```

We can also incorporate sliders in order to allow the user to control the tint on the page. The p5 documentation on [sliders can be found here.](https://p5js.org/reference/#/p5/createSlider)

To create a slider, we need to use the `createSlider` command. We can use the `.position(x, y)` to place the slider on the page. We can use the `.value()` command to get the current value of the slider.

```javascript
var slider;
function setup() {
	// Makes a slider that ranges from 0 to 255 and starts at 100.
	slider = createSlider(0, 255, 100)
	// Places the slider at (50, 50)
	slider.position(50, 50) 
}

function draw() {
	// Gets the values of the slider
	var val = slider.value()
	// Assigns the sliders value to the blue tint value
	tint(0, 0, val)
	image(img, 50, 50, 100, 200) 
}

```

## Tasks for Today
1. Load the rabbit image using function preload, imageLoad, and image commands. Set the images tint to blue 

![](/assets/Challenge1.png)

2. Load the tree image using `function preload` and `imageLoad`. Render two trees on the page using the `image` command. Set the image tint for one tree to some amount of red.  Set the images tint for another tree to some amount of green. 

![](/assets/Challenge2.png)

3. Make a forest of trees! Have each row be a slightly different tint. Bonus, play with the transparency to make some of the trees more see through.

![](/assets/Challenge3.png)

4. Hide several creatures within your forest - play with opacity if you want them to be super camouflaged!

5. Add a slider to your page. Use the value of the slider to update the tint value for one of the trees

![](/assets/Challenge5.gif)

6. Add three sliders to the page. One should adjust the red value. One the green. One the blue.

7. Add multiple tree images to an array, and select a random tree to draw each time. This should result in a forest of many different trees if you have done it correctly!