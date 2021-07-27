<style>
	blockquote {
		padding: 16px 16px 8px 16px;
		margin: 1rem 0;
	}
	pre > code {
		font-size: 14px;
		background: none;
		color: #fff;
		padding: 0;
		border-radius: 0;
	}
	code {
		font-size: 13px;
		background: #ffdadd;
		color: #dc4753;
		margin: .5em 0;
		padding: .3rem;
		border-radius: 3px;
	}
	.tag {
		display: inline-flex;
		align-items: center;
		background: #2972fa;
		color: #fff;
		margin-right: .25rem;
		font-size: 13px;
		border-radius: .25rem;
		line-height: 1.5;
		min-height: 1.5rem;
		padding: 0 .5rem;
		white-space: nowrap;
	}
	.note {
		background: #fbdbaa;
		color: #9b3908;
		border-color: #9b3908;
		margin: 1rem 0;
		padding: 1rem 2rem;
		line-height: 2;
		font-size: 16px;
	}
	.text-code {
		font-family: SFMono-Regular,Menlo,Monaco,Consolas,Liberation Mono,Courier New,monospace;
	}
	.code-label {
		color: #868e96;
	}
</style>

<h1 id="top">Inty-CSS</h1>

## Table of Contents 

 1. [Development](#development)
 2. [Colors](#colors)
	 2.1 [Classes](#classes)
	 2.2 [v1 Colors](#v1-colors)
	 2.3 [v2 Colors](#v2-colors)
 3. [Typography](#typography)
	 3.1 [Typefaces](#typefaces)
 4. [Viewports](#viewports)
	 4.1 [Default Behavior](#default-behavior)
	 4.2 [Breakpoints](#breakpoints)
	 4.3 [Usage](#usage)
 5. [Customization](#customization)
 6. [Animations](#animations)
	 6.1 [Loading](#loading)
	 6.2 [Hover Grow](#hover-grow)
	 6.3 [Entrance Animations](#entrance-animations)
	 6.4 [Infinite Animations](#infinite-animations)
	 6.5 [Animation Utils](#animation-utils)	 

## Development
[Back to top](#top)

Compile CSS with level 2 minification

	npm run build

Compile SCSS without minification

	npm run compile

Automate compiling and minification

	npm run watch

## Colors
[Back to top](#top)

Using a color within Cirrus is as simple as just prefixing the colors with <code>bg-</code> to color the background and with <code>text-</code> to color the text.

### Classes

#### Examples

Button using <code>indigo-500</code> for text and <code>indigo-100</code> for the background.

	<button class="text-indigo-500 bg-indigo-500">
		Custom Button
	</button>

Square using a <code>info</code> background.

	<div class="bg-info u-round mx-auto" style="height: 50px; width: 50px;"></div>

---

### v1 Colors

The standard color palette from older versions of the framework.

| Color | primary | light | dark | link | link-dark | info | success | warning | danger |
|--|--|--|--|--|--|--|--|--|--|
| Hexcode | #f03d4d | #f6f9fc | #363636 | #5e5cc7 | #4643e2 | #2972fa | #0dd157 | #fab633 | #fb4143 |

---

### v2 Colors

Cirrus has an extensive color palette that has been updated with 0.6.0 to make them more accessible to all page elements.

| | -100 | -200 | -300 | -400 | -500 | -600 | -700 | -800 | -900 |
|--|--|--|--|--|--|--|--|--|--|
| pink |
| red |
| orange |
| yellow |
| green |
| teal |
| blue |
| indigo |
| purple |
| gray |

## Typography
[Back to top](#top)

**Cirrus** incorporates beautiful typography to make your website stand out from the rest. Nunito Sans, by [Vernon Adams](https://sansoxygen.com/) is chosen for the default typography for most elements such as <code>paragraphs</code>, <code>articles</code>, <code>blockquotes</code>, and more while Montserrat adds a bold but elegant touch to titles.

The <code>font-size</code> have been converted to rems which is independent of the font sizes of the parent elements. The default is set to 1rem (16px) where each interval of rem is 16 pixels.

### Typefaces

These are the two main fonts used in the framework the elements they are used in.

<span style="font-size: 18px;">Montserrat</span>

**Used in:**

<span class="tag">h1</span>, <span class="tag">h2</span>, <span class="tag">h3</span>, <span class="tag">h4</span>, <span class="tag">h5</span>, <span class="tag">h6</span>

<span style="font-size: 18px;">Nunito Sans</span>

**Used in:**

<span class="tag">p</span>, <span class="tag">label</span>, <span class="tag">span</span>, <span class="tag">blockquote</span>, <span class="tag">code</span>, <span class="tag">article</span>

## Viewports
[Back to top](#top)

Cirrus by default is a framework designed to make developing mobile optimized sites easier. Most styles for layouts and elements adapt to changes in screen size and orientation.

### Default Behavior

Some default behavior to expect when elements get resized are:

 - Text elements such as <code>h1</code> will shrink for mobile devices to remain in the right proportion.
 
 - Navigation items inside of <code>header-nav</code> will be tucked away in a dropdown menu for mobile devices.

- Columns inside of a <code>row</code> start out as vertically stacked elements on mobile devices. This can be ignored using the <code>ignore-screen</code> class.

- Elements inside of <code>level</code> will also be stacked vertically on mobile devices. Again, the <code>ignore-screen</code> class can be used to override this behavior.

---

### Breakpoints

The standard breakpoints used in Cirrus are <code>xs</code>, <code>sm</code>, <code>md</code>, and <code>lg</code>. This replaces the <code>mobile</code>, <code>tablet</code>, and <code>desktop</code> designations used in older versions.

| Type | Min (px) | Max (px) |
|:-- |:--:|:--:|
| xs | **0** | **640** |
| sm | **641** | **768** |
| md | **769** | **1023** |
| lg | **1024** | **1279** |
| xl | **1280** | - |

From that, the class designations in Cirrus follow this guideline:

<table>
	<thead>
		<tr>
			<th>xs <br> Below and including 640px</th>
			<th>sm <br> Between 641px and 768px</th>
			<th>md <br> Between 769px and 1023px</th>
			<th>lg <br> Between 1024px and 1279px</th>
			<th>xl <br> 1280px and above</th>	
		</tr>	
	</thead>
	<tbody>
		<tr>
			<td colspan="5" style="text-align:center;"><center align="center" style="background: #2972fa; border-color: #2972fa; padding: .75rem 1.25rem; border-radius:2px; color: #fff; position: relative; margin: .5rem;">Regular Class (eg. <b>u-none</b>)</center></td>
		</tr>
		<tr>
			<td colspan="1"><center>-</center></td>
			<td colspan="4"><center style="background: #2972fa; border-color: #2972fa; padding: .75rem 1.25rem; border-radius:2px; color: #fff; position: relative; margin: .5rem;">*-sm</center></td>
		</tr>
		<tr>
			<td colspan="2"><center>-</center></td>
			<td colspan="3"><center style="background: #2972fa; border-color: #2972fa; padding: .75rem 1.25rem; border-radius:2px; color: #fff; position: relative; margin: .5rem;">*-md</center></td>
		</tr>
		<tr>
			<td colspan="3"><center>-</center></td>
			<td colspan="2"><center style="background: #2972fa; border-color: #2972fa; padding: .75rem 1.25rem; border-radius:2px; color: #fff; position: relative; margin: .5rem;">*-lg</center></td>
		</tr>
		<tr>
			<td colspan="4"><center>-</center></td>
			<td colspan="1"><center style="background: #2972fa; border-color: #2972fa; padding: .75rem 1.25rem; border-radius:2px; color: #fff; position: relative; margin: .5rem;">*-xl</center></td>
		</tr>
		<tr>
			<td colspan="5"></td>
		</tr>
	</tbody>
</table>

An example of style that follows this convention is the <code>u-none-*</code> class.

|||
|:--:|:--:|
| <code>u-none</code> | Hide content for all widths. |
| <code>u-none-sm</code> | Hide content for widths <code>641px</code> and above. |
| <code>u-none-md</code> | Hide content for widths <code>768px</code> and above. |
| <code>u-none-lg</code> | Hide content for widths <code>1024px</code> and <code>1279px</code> |
| <code>u-none-xl</code> | Hide content for <code>1280px</code> and above. |
|||

---

### Usage

When applying classes viewport supported classes, note that the framework assumes you are designing for a mobile device **first**. This means that applying <code>u-none</code> on some given div will apply for all screen sizes.

#### Design For Mobile First

If you then set <code>u-flex-md</code> on the div, it will then apply a flexbox layout starting at the <code>md</code> breakpoint and higher.

	<div class="u-none u-flex-md">
		<!-- ... -->
	>/

#### Modify Specific Viewport

To apply a class for a specific screen size, we can easily set this behavior using multiple declarations of the classes we need for each viewport.

As an example, let's say we want to position a <code>sticky</code> div to be <code>relative</code> only for <code>sm</code> to <code>md</code>. We can achieve this with the class declarations show above.

	<div class="u-sticky u-relative-sm u-sticky-md">
		<!-- ... -->
	/>

Note that not all classes support application by viewport. You can see if a given group of classes support this by checking if the documentation contains a 'Responsive' section detailing how to use the classes with different viewports.

## Customization
[Back to top](#top)

You can now modify the breakpoints used in Cirrus within the new configuration file for sizing. Just edit the values stored inside <code>_size.scss</code>.

	$breakpoints: (
		'xs': 640px,
		'sm': 768px,
		'md': 1024px,
		'lg': 1280px
	);

## Animations
[Back to top](#top)

Animations are an essential part in crafting beautiful websites that aren't just stunning, but are also alive. Cirrus comes bundled with animated components to help you get started.

### Loading

The loading spinner serves as an elegant indicator for progress in webpages. Just add the <code>animated loading</code> selectors to the element and Cirrus will handle the rest.

By default, the spinner will be horizontally centered and it will override any text. To hide the text, just add the <code>hide-text</code> class.

	<div class="card u-flex u-items-center u-justify-center">
		<div class="animated loading hide-text">
			<p>Hidden</p>
		</div>
	</div>

The spinner's color could also be changed to white with the <code>loading-white</code> class.

	<div class="card u-flex u-items-center u-justify-center" style="background: linear-gradient(to right, rgb(142, 45, 226), rgb(74, 0, 224));">
		<div class="animated loading hide-text loading-white">
			<p>Hidden</p>
		</div>
	</div>

To show the spinner to the left, use the <code>loading-left</code> class.

	<div class="card u-flex u-items-center u-justify-center" style="background: linear-gradient(to right, rgb(142, 45, 226), rgb(74, 0, 224));">
		<div class="animated loading hide-text loading-white">
			<p>Hidden</p>
		</div>
	</div>

For the right, use the <code>loading-right</code> class.

	<div class="card" style="background: linear-gradient(to right, rgb(255, 88, 88), rgb(248, 87, 166));">
		<div class="animated loading loading-right loading-white white u-text-right">
			<p>loading-right</p>
		</div>
	</div>

---

### Hover Grow

This is a subtle animation that enlarges a given element on hover. Just add the <code>hover-grow</code> class to your element.

	<div class="hover-grow">
		<img src="../../card.svg" />
	</div>

---

### Entrance Animations

These are animations that only run once when the page is loaded or the class is toggled.

#### Bounce

Bouncing animation with a glyph.

	<span class="icon"><i class="fa fa-wrapper fa-heart animated bounce" aria-hidden="true"></i></span>

Bouncing animation with a div.

	<div class="bg-orange-400 white u-text-center animated bounce">
		<p>This is a div!</p>
	</div>

Bouncing animation with a button.

	<button class="btn-info animated bounce">Button</button>

#### Bounce In

Bounce in animation with a glyph.

	<span class="icon"><i class="fa fa-wrapper fa-heart animated bounceIn" aria-hidden="true"></i></span>

Bounce in animation with a div.

	<div class="bg-orange-400 white u-text-center animated bounceIn">
		<p>This is a div!</p>
	</div>

Bounce in animation with a button.

	<button class="btn-info animated bounceIn">Button</button>

#### Fade In

Fade in animation with a glyph.

	<span class="icon"><i class="fa fa-wrapper fa-heart animated fadeIn" aria-hidden="true"></i></span>

Fade in animation with a div.

	<div class="bg-orange-400 white u-text-center animated fadeIn">
		<p>This is a div!</p>
	</div>

Fade in animation with a button.

	<button class="btn-info animated fadeIn">Button</button>

---

### Infinite Animations

These are animations that only run continuously.

#### Pulse

Pulse animation with a glyph.

	<span class="icon"><i class="fa fa-wrapper fa-heart animated pulse" aria-hidden></i></span>

Pulse animation with a div.

	<div class="bg-orange-400 white u-text-center animated pulse">
		<p>This is a div!</p>
	</div>

Pulse animation with a button.

	<button class="btn-info animated pulse">Button</button>

---

### Animation Utils

Cirrus comes with a couple of tools you can use to help test or modify animation behavior.

#### Infinite Animation

This will sustain an animation when the user is on the page. This even works for animations not designed to be infinitely looped. The only change needed is the addition of the <code>infinite</code> class to the component.

Below is an example using the fade in animation.

	<button class="btn-primary animated fadeIn infinite">Infinitely Fading</button>

Now this animation seems to cut off at the end of the cycle. To make it alternate, just add the <code>alternate</code> class to make the animation more fluid.

	<button class="btn-primary animated fadeIn infinite alternate">Alternating Fading</button>

#### Pausing Animations

This is great with testing your animations and works well with JavaScript calls also. All you need to do is add a class to the animated component called <code>paused</code>.

	<button class="btn-primary animated bounce infinite alternate paused">Paused</button>

## Buttons
[Back to top](#top)

Buttons in Cirrus come with some basic styling to help you get started. You can choose some of the different variants of buttons shown below or you can use the utility classes to customize it yourself.

There are three ways to create a button:

<ul>
	<li>Use the <code>button</code> tag.</li>
	<li>Use the <code>btn</code> class.</li>
	<li>Use an <code>input</code> with type <code>submit</code>.</li>
</ul>

	<button>Button</button>
	<div class="btn">Button</div>
	<input type="submit" value="submit">

### Colors

Cirrus comes in quite a few different shades of colors. Below are some of the preset styles that you can use for your button that are core to the framework.

---

#### Solid

	<button class="">Plain</button>
	<button class="btn-transparent">transparent</button>
	<button class="btn-light">light</button>
	<button class="btn-dark">dark</button>
	<button class="btn-black">black</button>
	<button class="btn-primary">primary</button>
	<button class="btn-link">link</button>
	<button class="btn-info">info</button>
	<button class="btn-success">success</button>
	<button class="btn-warning">warning</button>
	<button class="btn-danger">danger</button>

#### Outline
[Back to top](#top)

	<button class="outline btn-transparent">transparent</button>
	<button class="outline btn-light">light</button>
	<button class="outline btn-dark">dark</button>
	<button class="outline btn-black">black</button>
	<button class="outline btn-primary">primary</button>
	<button class="outline btn-link">link</button>
	<button class="outline btn-info">info</button>
	<button class="outline btn-success">success</button>
	<button class="outline btn-warning">warning</button>
	<button class="outline btn-danger">danger</button>

---

### Sizes

Buttons can have alternative sizes of <code>xsmall</code>, <code>small</code>, <code>large</code>, and <code>xlarge</code>.

	<button class="text-blue-600 bg-blue-100 btn-xsmall">Xsmall</button>
	<button class="text-blue-600 bg-blue-100 btn-small">Small</button>
	<button class="text-blue-600 bg-blue-100 btn-large">Large</button>
	<button class="text-blue-600 bg-blue-100 btn-xlarge">Xlarge</button>

## Button Groups
[Back to top](#top)

Button groups are designed to group buttons of similar actions or properties together in a seamless fashion. Buttons are placed adjacent to each other and buttons at each of the ends are rounded off respectively.

	<div class="btn-group">
		<button class="btn-primary">First Button</button>
		<button class="btn-primary">Second Button</button>
		<button class="btn-primary">Third Button</button>
	</div>

To make the buttons in the <code>btn-group</code> fill its parent container, add the <code>btn-group-fill</code> class to the <code>btn-group</code>.

	<div class="btn-group btn-group-fill">
		<button class="bg-orange-200 text-orange-700">Edge</button>
		<button class="bg-orange-200 text-orange-700">To</button>
		<button class="bg-orange-200 text-orange-700">Edge</button>
	</div>

## Glyphs
[Back to top](#top)

Buttons can contain different glyphs from external libraries such as [Font Awesome](https://fontawesome.com/).

### Glyph on the left

	<button>See More<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>

---

### Glyph on the right

	<button><i class="fa-wrapper fa fa-chevron-left pad-right"></i>See More</button>

---

### Glyph with different sizes

	<button class="btn-xsmall">Xsmall<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>
	<button class="btn-small">Small<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>
	<button>Normal<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>
	<button class="btn-large">Large<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>
	<button class="btn-xlarge">Xlarge<i class="fa-wrapper fa fa-chevron-right pad-left"></i></button>

## Variants
[Back to top](#top)

Besides your typical clickable button, buttons also come in other forms to support other use case.

### Animated Button

The <code>.btn-animated</code> class adds a slight "push" to the button when clicked.

	<button class="btn-animated">Button</button>
	<div class="btn btn-animated">Button</div>
	<input class="btn-animated" type="submit" value="Submit" />

---

### Disabled Button

Add the <code>disabled</code> keyword to make the button unselectable.

<blockquote class="note">Note that this is not supported for buttons created using <code>div</code> tags.</blockquote>

	<button class="btn-animated">Button</button>
	<div class="btn btn-ani
	mated">Button</div>
	<input class="btn-animated" type="submit" value="Submit" />

---

### Loading Button

Add the <code>.animated</code> and <code>.loading</code> classes to create a button containing a spinner. Since it relies on the button to contain text for height, you must specify some text. To hide the text, you just need to add the <code>.hide-text</code> class as well.

	<button class="btn-animated loading hide-text">Button</button>
	<div class="btn btn-animated loading hide-text">Button</div>
	<input class="btn-animated loading hide-text" type="submit" value="Submit" />

To display text, there are two helper classes created to show text to the left and right of the spinner.

To set the spinner to appear to the left of text, use the <code>.loading-left</code> class.

	<button class="animated loading loading-left btn-link">Loading</button>

To set the spinner to appear to the right of text, use the <code>.loading-right</code> class.

	<button class="animated loading loading-right btn-link">Loading</button>

---

### Close Button

This is the generic close button control that can be added to other components in Cirrus. Below is an example of a <code>.frame</code> containing a <code>.btn-close</code>.

	<div class="frame">
		<div class="frame-header">
			<button class="btn-close inty-pull-right"></button>
		</div>
		<div class="frame-body">
			<p>You can close me now.</p>
		</div>
	</div>

---

### Shapes

Modifier classes can be used to change the shape of a button as shown below.

#### Pilled

This provides a rounded shape for the button that closely resembles a pill with the <code>btn-pilled</code> class.

	<button class="btn-info btn-pilled">Test</button>

#### Circle

The <code>btn-circled</code> class turns a button into a circle. The circle size will scale based on the contents of the button.

	<button class="btn-danger btn-circle"><b>Small</b></button>
	<button class="btn-warning btn-circle"><h6 class="px-2">Bigger</h6></button>
	<button class="btn-success btn-circle"><h3 class="px-2">Biggest</h3></button>

## Avatars
[Back to top](#top)

The <code>avatar</code> class is a great way to display images as part of other components.

### Avatars With Images

The typical way to use avatars is to embed an image within them.

	<div class="avatar"><img src="..." alt="avatar"></div>
	<div class="avatar"><img src="..." alt="avatar"></div>
	<div class="avatar"><img src="..." alt="avatar"></div>
	<div class="avatar"><img src="..." alt="avatar"></div>
	<div class="avatar"><img src="..." alt="avatar"></div>
	
---

### Avatars With Text

Alternatively, you can specify text to be displayed inside the avatar itself. This is similar to what you see in Gmail.

	<div class="avatar" data-text="Aa"></div>
	<div class="avatar" data-text="Bb"></div>
	<div class="avatar" data-text="Cc"></div>

---

### Avatars Sizes

As with many other components in Cirrus, <code>avatar</code> comes with 4 other size modifiers including <code>avatar-xsmall</code>, <code>avatar-small</code>, <code>avatar-large</code>, and <code>avatar-xlarge</code>.

The example below shows how <code>avatars</code> can be used with <code>tiles</code>.

	<div class="row">
		<div class="col-6">
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-xsmall" data-text="Jz"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Jenelle Zaynab</p>
					<p class="tile-subtitle m-0"><a href="!#">@jenelle_zaynab</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-small" data-text="Jz" style="background: rgb(163, 211, 156);"></figure>
				</div>
				<div class="tile-container">
					<p class="title-title m-0">Jenelle Zaynab</p>
					<p class="tile-subtitle m-0"><a href="!#">@jenelle_zaynab</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar" data-text="Jz" style="background: rgb(122, 204, 200);"></figure>
				</div>
				<div class="tile-container">
					<p class="title-title m-0">Jenelle Zaynab</p>
					<p class="tile-subtitle m-0"><a href="!#">@jenelle_zaynab</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-large"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Jenelle Zaynab</p>
					<p class="tile-subtitle m-0"><a href="!#">@jenelle_zaynab</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-xlarge"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Jenelle Zaynab</p>
					<p class="tile-subtitle m-0"><a href="!#">@jenelle_zaynab</a></p>
				</div>
			</div>
		</div>
		<div class="col-6">
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-xsmall"><img src="https://images.unsplash.com/profile-1495427732560-fe5248ad6638?dpr=1&amp;auto=format&amp;fit=crop&amp;w=64&amp;h=64&amp;q=60&amp;cs=tinysrgb&amp;crop=faces&amp;bg=fff"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Nathan Dumlao</p>
					<p class="tile-subtitle m-0"><a href="!#">@nate_dumlao</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-small"><img src="https://images.unsplash.com/profile-1495427732560-fe5248ad6638?dpr=1&amp;auto=format&amp;fit=crop&amp;w=64&amp;h=64&amp;q=60&amp;cs=tinysrgb&amp;crop=faces&amp;bg=fff"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Nathan Dumlao</p>
					<p class="tile-subtitle m-0"><a href="!#">@nate_dumlao</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar"><img src="https://images.unsplash.com/profile-1495427732560-fe5248ad6638?dpr=1&amp;auto=format&amp;fit=crop&amp;w=64&amp;h=64&amp;q=60&amp;cs=tinysrgb&amp;crop=faces&amp;bg=fff"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Nathan Dumlao</p>
					<p class="tile-subtitle m-0"><a href="!#">@nate_dumlao</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-large"><img src="https://images.unsplash.com/profile-1495427732560-fe5248ad6638?dpr=1&amp;auto=format&amp;fit=crop&amp;w=64&amp;h=64&amp;q=60&amp;cs=tinysrgb&amp;crop=faces&amp;bg=fff"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Nathan Dumlao</p>
					<p class="tile-subtitle m-0"><a href="!#">@nate_dumlao</a></p>
				</div>
			</div>
			<div class="space"></div>
			<div class="tile m-0 level">
				<div class="tile-icon">
					<figure class="avatar avatar-xlarge"><img src="https://images.unsplash.com/profile-1495427732560-fe5248ad6638?dpr=1&amp;auto=format&amp;fit=crop&amp;w=64&amp;h=64&amp;q=60&amp;cs=tinysrgb&amp;crop=faces&amp;bg=fff"></figure>
				</div>
				<div class="tile-container">
					<p class="tile-title m-0">Nathan Dumlao</p>
					<p class="tile-subtitle m-0"><a href="!#">@nate_dumlao</a></p>
				</div>
			</div>
		</div>
	</div>

## Cards
[Back to top](#top)

A <code>card</code> can be thought of a more specialized and elegant version of a <code>frame</code> with different configurations and a hover effect.

### Structure

The structure for the <code>card</code> contains quite a number of classes, so below is a breakdown of what is supported.

---

#### Structure

<ul>
	<li><code>card</code></li>
	<ul>
		<li><code>card-header</code></li>
		<li><code>card-container</code></li>
		<ul>
			<li><code>card-image</code></li>
			<li><code>card-title-container</code></li>
			<ul>
				<li><code>title</code></li>
				<li><code>subtitle</code></li>
			</ul>
		</ul>
		<li><code>content</code></li>
		<li><code>card-action-bar</code></li>
		<li><code>card-footer</code></li>
	</ul>
</ul>

	<div class="card" style="max-width: 350px;">
		<div class="card-container">
			<div class="card-image"></div>
			<div class="card-title-container">
				<p class="title">Title</p>
				<span class="subtitle">Subtitle</span>
			</div>
		</div>
		<div class="content">
			<p>Text and other content belong here, inside a <code>content</code> div.</p>
		</div>
		<div class="card-action-bar u-center">
			<button class="btn-link outline">Buttons</button>
			<button class="btn-link outline">Go here</button>
		</div>
		<div class="card-footer">
			<div class="u-text-center"><span>This is additional footer text in <code>card-footer</code>.</span></div>
		</div>
	</div>

---

### Basic

Below is just a simple example of a <code>card</code> that contains a centered image and some text components.

	<div class="card" style="max-width: 250px;">
		<div class="content u-text-center pt-3">
			<svg aria-hidden="true" focusable="false" data-prefix="fas" data-icon="bolt" class="svg-inline--fa fa-bolt fa-w-10 fa-wrapper text-blue-600 bg-blue-100 p-3" role="img" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 320 512" style="border-radius: 100%; height: 4.75rem; width: 4.75rem;">
				<path  fill="currentColor"  d="M296 160H180.6l42.6-129.8C227.2 15 215.7 0 200 0H56C44 0 33.8 8.9 32.2 20.8l-32 240C-1.7 275.2 9.5 288 24 288h118.7L96.6 482.5c-3.6 15.2 8 29.5 23.3 29.5 8.4 0 16.4-4.4 20.8-12l176-304c9.3-15.9-2.2-36-20.7-36z"></path>
			</svg>
			<p id="projectname" class="title mt-2 mb-0">Fast. Very fast.</p>
			<p>Blazing fast speed you can rely on.</p>
		</div>
	</div>

---

### Animated

The animated variant of a card comes with a title container that slides up to reveal more information on hover.

Compared to a typical card, there are a couple of key differences to note regarding the code.

<ul>
	<li>An animated card must have the <code>card-slide-up</code> class along with the <code>card</code> class.</li>
	<li>To display an image, it is recommended to create a <code>card-image</code> div nested inside a <code>card-container</code> div.</li>
	<li>Unlike the standard card above, the title and subtitle are placed in the card-mobile-title div below the <code>card-container</code>.</li>
	<li>The content or text of the card is then placed inside a standard <code>content</code> div now with the <code>card-body</code> class.</li>
</ul>

Following the steps above should yield a card similar to the one below.

	<div class="card card-slide-up">
		<div class="card-container">
			<div class="card-image" style="background-image: url(&quot;https://unsplash.it/640/480?random&amp;blur&quot;);"></div>
		</div>
		<div class="card-mobile-title">
			<div class="content">
				<div class="tile">
					<div class="tile-container">
						<p class="tile-title">Kangaroo Valley Safari</p>
						<p class="tile-subtitle">By John Doe</p>
					</div>
				</div>
			</div>
		</div>
		<div class="card-body content">
			<p>Located two hours south of Sydney in the Southern Highland of New South Wales...</p>
		</div>
		<div class="card-footer content">2 min. read 22 comments</div>
	</div>

---

### Grouping

Cards can be grouped using Cirrus's flexbox grid system.

Grouping with animated cards.

---

### Equal Height

You may have noticed that the height of the card are not the same if the length of the content is different. To fix this, you can add the <code>h-100 inty-flex inty-flex-column</code> classes to <code>card</code>.

Note that **this does not work with the card with the animated card above.**

---

### Example

Here are a couple of examples to help you get started with designing using <code>cards</code>.

#### Twitter Card

	<div class="card">
		<div class="card-container">
			<div class="card-image" style="background-image: url(https://images.unsplash.com/photo-1467952497026-86722ef1916f?dpr=1.25&amp;auto=compress,format&amp;fit=crop&amp;w=1199&amp;h=799&amp;q=80&amp;cs=tinysrgb&amp;crop=);"></div>
		</div>
		<div clas="content">
			<div class="space"></div>
			<div class="tile tile-center">
				<div class="tile-icon">
					<figure class="avatar">
						<img src="https://organicthemes.com/demo/profile/files/2018/05/profile-pic-132x132.jpg" alt="Person">
					</figure>
				</div>

				<div class="tile-container">
					<p class="tile-title">Joanne Doe</p>
					<p class="tile-subtitle"><a>@jdoe</a></p>
				</div>
			</div>
			<p>Testing my new DSLR. Wow check out that deer! <a href="!#">#nature</a></p>
		</div>
		<div class="card-footer level content">
			6:32 PM - 3 Jul 18
			<div class="inty-pull-right">
				<div class="level-right ignore-screen">
					<a class="level-item">
						<span class="icon"><i class="fa fa-wrapper small fa-reply" aria-hidden="true"></i></span>
					</a>
					<a class="level-item">
						<span class="icon"><i class="fa fa-wrapper small fa-retweet" aria-hidden="true"></i></span>
					</a>
					<a class="level-item">
						<span class="icon"><i class="fa fa-wrapper small fa-heart" aria-hidden="true"></i></span>
					</a>
				</div>
			</div>
		</div>
	</div>

#### Simple Tweet Card

	<div class="card">
		<div class="card-header">
			<p class="font-bold px-3">This is the title</p>
		</div>
		<div class="content">
			<p>This is some sample text spam spam spam spam spam spam. <a href="!#">#place</a><a href="!#">#holder</a><a href="!#">@Cirrus</a></p>
		</div>
		<div class="card-footer level content">6:32 PM - 3 Jul 18</div>
		<div class="card-action-bar inty-center">
			<button class="btn-transparent outline">Cancel</button>
			<button class="btn-transparent outline">Save</button>
			<button class="btn-transparent outline">Post</button>
		</div>
	</div>

## Code

Easily create code blocks in Cirrus with the <code>code</code> class.

### Basics

By default, a code block is nothing more than a <code>pre</code> wrapping a <code>code</code> block with some extra classes.

> console.log('hello 👋');

	<pre><code>console.log('hello 👋');</code></pre>

---

### Language Specification

To specify the language of the code block, just add the <code>data-lang</code> attribute to the <code>code</code> element.

> <div class="text-code code-label" align="right">JavaScript</div>
> <p class="text-code">console.log('hello 👋');</p>

	<pre><code data-lang="JavaScript">console.log('hello 👋');</code></pre>

---

### Dark Mode

For a dark background, use the <code>dark</code> class.

> <div class="text-code code-label" align="right">JavaScript</div>
> <p class="text-code">console.log('hello 👋');</p>

	<pre><code class="dark" data-lang="JavaScript">console.log('hello 👋');</code></pre>

---

### Inline

To display code within a paragraph, you only need to use the <code>code</code> element.

<p style="font-size: 18px;">In order to speed up your computer, make sure you try running <code>sudo rm -rf /</code>.</p>

	<p class="lead">In order to speed up your computer make sure you try running <code>sudo rm -rf</code>.</p>

## Links

Links themselves come with default styling within the framework. However, there are a lot of classes that can be used to customize its hover behavior.

<a href="!#">I am just an ordinary link</a>
I am <a href="!#">inside</a> text.

### Styles

Links themselves come with default styling within the framework. However, there are a lot of classes that can be used to customize its hover behavior.

#### TYPES

**Standard**
A standard link with only a color transition.

<a href="!#">Standard</a>

	<a href="!#">Standard</a>

**Underline**
A link with underlined text.

<a href="!#" class="underline">Underline</a>

	<a href="!#" class="underline">Underline</a>

**Underline Animation (Left to Right)**
Animated underlined link with a transition from left to right.

<a href="!#" class="u u-LR">Left to Right</a>

	<a href="!#" class="u u-LR">Left to Right</a>

**Underline Animation (Right to Left)**
Animated underlined link with a transition from right to left.

<a href="!#" class="u u-RL">Right to Left</a>

	<a href="!#" class="u u-RL">Right to Left</a>

**Underline Animation (Center)**
Animated underlined link with a transition from the center.

<a href="!#" class="u u-C">Center</a>

	<a href="!#" class="u u-C">Center</a>

**Outline Animation (Left to Right)**
Animated outlined link with a transition from left to right.

<a href="!#" class="utb utb-LR">Left to Right</a>

	<a href="!#" class="utb utb-LR">Left to Right</a>

**Outline Animation (Right to Left)**
Animated outlined link with a transition from right to left.

<a href="!#" class="utb utb-RL">Right to Left</a>

	<a href="!#" class="utb utb-RL">Right to Left</a>

**Outline Animation (Center)**
Animated outlined link with a transition from the center.

<a href="!#" class="utb utb-C">Center</a>

	<a href="!#" class="utb utb-C">Center</a>

**Opposite Transitions (L -> R / R -> L)**
Animated outlined link with a transition with the top moving left to right and the bottom right to left. Keep in mind that the class name refers to the direction of movement of the top border.

<a href="!#" class="utb utb-OLR">Look at me</a>

	<a href="!#" class="utb utb-OLR">Look at me</a>

**Opposite Transitions (R -> L / L -> R)**
Animated outlined link with a transition with the top moving right to left and the bottom left to right. Keep in mind that the class name refers to the direction of movement of the top border.

<a href="!#" class="utb utb-ORL">Crisscross</a>

	<a href="!#" class="utb utb-ORL">Crisscross</a>

**Square**
Animated link with simultaneously drawn borders.

<span class="usquare">
	<a href="!#" class="utb utb-OLR">I am a square</a>
</span>

	<span class="usquare">
		<a href="!#" class="utb utb-OLR">I am a sqsuare</a>
	</span>

**Delayed Square**
Animated link with sequentially drawn borders.

<span class="usquare delay">
	<a href="!#" class="utb utb-OLR">I am a square</a>
</span>

	<span class="usquare delay">
		<a href="!#" class="utb utb-OLR">I am a square</a>
	</span>

## Lists

Besides basic styling for lists, Cirrus also ships with classes that allow lists to be incorporated with other classes in unique ways.

### Basic

Minimal styles are used to tweak the look of lists.

#### Types

**Bulleted (Default)**
A standard list with bullets preceding the list item.

<ul>
	<li>Apple</li>
	<li>Google</li>
	<li>Facebook</li>
	<li>Microsoft</li>
</ul>

	<ul>
		<li>Apple</li>
		<li>Google</li>
		<li>Facebook</li>
		<li>Microsoft</li>
	</ul>

**Numbered**
An ordered list with numbers for each item.

<ol>
	<li>Apple</li>
	<li>Google</li>
	<li>Facebook</li>
	<li>Microsoft</li>
</ol>

	<ol>
		<li>Apple</li>
		<li>Google</li>
		<li>Facebook</li>
		<li>Microsoft</li>
	</ol>

**Plain**
A list with no item decorations using the <code>no-bullets</code> class.

<ul class="no-bullets">
	<li>Apple</li>
	<li>Google</li>
	<li>Facebook</li>
	<li>Microsoft</li>
</ul>

	<ul class="no-bullets">
		<li>Apple</li>
		<li>Google</li>
		<li>Facebook</li>
		<li>Microsoft</li>
	</ul>

**Details**
A list designed for detailed descriptions.

<dl>
	<dt>Apple</dt>
	<dd>
		Apple Inc. is an American multinational technology company headquartered in Cupertino, California that designs, develops, and sells consumer electronics, ...
	</dd>
</dl>

	<dl>
		<dt>Apple</dt>
		<dd>
			Apple Inc. is an American multinational technology company headquartered in Cupertino, California that designs, develops, and sells consumer electronics, ...
		</dd>
	</dl>

#### Nested Lists

Cirrus will automatically style and pad nested lists so you don't have to. Just add the <code>nested-list</code> class to the div containing the list.

<ul>
	<li>List Item 1</li>
	<li>List Item 2</li>
	<li>
		List Item 3
		<ul>
			<li>List Item 3.a</li>
			<li>List Item 3.b</li>
			<li>
				List Item 3.c
				<ul>
					<li>List Item 3.c.i</li>
					<li>List Item 3.c.ii</li>
					<li>List Item 3.c.iii</li>
				</ul>
			</li>
		</ul>
	</li>
</ul>

	<ul>
		<li>List Item 1</li>
		<li>List Item 2</li>
		<li>
			List Item 3
			<ul>
				<li>List Item 3.a</li>
				<li>List Item 3.b</li>
				<li>
					List Item 3.c
					<ul>
						<li>List Item 3.c.i</li>
						<li>List Item 3.c.ii</li>
						<li>List Item 3.c.iii</li>
					</ul>
				</li>
			</ul>
		</li>
	</ul>

---

### Menu Lists

A <code>menu</code> can be thought of a stylized list created to be incorporated into other Cirrus components or used standalone.

This can be created by adding the <code>menu</code> class to your <code>ol</code> or <code>ul</code> and adding the <code>menu-item</code> class to each <code>li</code>. To select a list item, add the <code>selected</code> class to the <code>menu-item</code>.

<ul class="menu">
	<li class="menu-item selected">
		<a href="!#">One</a>
	</li>
	<li class="menu-item">
		<a href="!#">Two</a>
	</li>
	<li class="menu-item">
		<a href="!#">Three</a>	
	</li>
</ul>

	<ul class="menu">
		<li class="menu-item selected">
			<a href="!#">One</a>
		</li>
		<li class="menu-item">
			<a href="!#">Two</a>
		</li>
		<li class="menu-item">
			<a href="!#">Three</a>	
		</li>
	</ul>

#### Structure

<ul>
	<li>
		<code>menu</code>
	</li>
	<ul>
		<li>
			<code>menu-item</code>
		</li>
	</ul>
</ul>

---

### Dropdown List

Drop down menus are easy to configure in Cirrus using lists. Simply wrap the button and the menu in a <code>list-dropdown</code> container and Cirrus will automatically style all the components for the dropdown menu. To display the menu on the right side, just add the <code>dropdown-right</code> class to the <code>list-dropdown</code> container. These dropdown menus can work straight out of the box and also support JavaScript events when needed.

#### Dropdown with Seperate Button

	<div>
		<div class="btn-group">
			<button class="btn-primary">Dropdown</button>
			<button class="btn-primary btn-small btn-dropdown">
				<i class="fa fa-wrapper fa-caret-down" aria-hidden="true"></i>
			</button>
			<ul class="menu">
				<li class="menu-item">
					<a href="!#">Google Chrome</a>
				</li>
				<li class="menu-item">
					<a href="!#">Firefox</a>
				</li>
				<li class="menu-item">
					<a href="!#">Polarity</a>
				</li>
			</ul>
		</div>
	</div>

#### Dropdown Right Aligned

	<div class="list-dropdown dropdown-right">
		<button class="btn-primary btn-dropdown m-0">
			Dropdown
			<i class="fa fa-wrappr fa-caret-down" aria-hidden="true"></i>
		</button>
		<ul class="menu">
			<li class="menu-item">
				<a href="!#">Google Chrome</a>
			</li>
			<li class="menu-item">
				<a href="!#">Firefox</a>
			</li>
			<li class="menu-item">
				<a href="!#">Polarity</a>
			</li>
		</ul>
	</div>

#### Dropdown Transparent Button

	<div class="list-dropdown">
		<button class="btn-transparent btn-dropdown m-0">
			Dropdown
			<i class="fa fa-wrapper fa-caret-down" aria-hidden="true"></i>
		</button>
		<ul class="menu">
			<li class="menu-item">
				<a href="!#">Google Chrome</a>
			</li>
			<li class="menu-item">
				<a href="!#">Firefox</a>
			</li>
			<li class="menu-item">
				<a href="!#">Polarity</a>
			</li>
		</ul>
	</div>

---

### Other Examples

More examples to help you get started.

#### Menu in Frame

	<div class="frame">
		<div class="frame-body">
			<div class="frame-header">
				<div class="tile level">
					<div class="tile-icon">
						<figure class="avatar">
							<img src="https://crunchbase-production-res.cloudinary.com/image/upload/c_thumb,h_256,w_256,f_auto,g_faces,z_0.7,q_auto:eco/v1398292826/a1tq244sp7uqhb5a0utg.png">
						</figure>
					</div>
					<div class="tile-container">
						<p class="tile-title">Richard Hendrick.</p>
						<p class="tile-subtitle">Founder and CEO of Pied Piper.</p>
					</div>
				</div>
			</div>
			<ul class="menu">
				<li class="divider"></li>
				<li class="menu-item selected">
					<div class="menu-addon right">
						<span class="icon">
							<i class="fa fa-wrapper fa-ellipsis-h small" aria-hidden="true"></i>
						</span>
					</div>
					<a href="!#">News Feed</a>
				</li>
				<li class="menu-item">
					<a href="!#">Messenger</a>
				</li>
				<p class="menu-title uppercase">Shortcuts</p>
				<li class="menu-item">
					<a href="!#">Some App</a>
				</li>
			</ul>
		</div>
	</div>

#### Menu in Card

	<div class="card">
		<div class="card-container">
			<div class="card-image" style="background-image: url(&quot;https://source.unsplash.com/random/640x480&quot;);"></div>
			<div class="card-title-container">
				<p class="title">Unsplash Viewer</p>
				<span class="subtitle">Rate this photo.</span>
			</div>
		</div>
		<div class="content">
			<p>Did you like the photo?</p>
			<ul class="menu">
				<li class="menu-item">
					<a href="!#">
						<span class="icon">
							<i class="fa fa-wrapper fa-check small" aria-hidden="true"></i>
						</span>
						Yes
					</a>
				</li>
				<li class="menu-item">
					<a href="!#">
						<span class="icon">
							<i class="fa fa-wrapper fa-times small" aria-hidden="true"></i>
						</span>
						No
					</a>
				</li>
			</ul>
		<div>
	</div>

#### Navigation Menus

	<div class="frame">
		<div class="frame-header">
			<p class="title m-0">Bookmarks</p>
		</div>
		<div class=frame-body">
			<ul class="menu">
				<li class="divider" data-label="TECH"></li>
				<li class="menu-item">
					<a href="!#">Github</a>
				</li>
				<li class="menu-item selected">
					<div class="menu-addon">
						<span class="icon">
							<i class="fa fa-wrapper fa-folder small" aria-hidden="true"></i>
						</span>
					</div>
					<a href="!#">Tech News</a>
					<ul class="menu">
						<li class="menu-item">
							<a href="!#">Hacker News</a>
						</li>
						<li class="menu-item">
							<a href="!#">Lobste.rs</a>
						</li>
					</ul>
				</li>
			</ul>
			<ul class="menu">
				<li class="divider" data-label="PROCRASTINATION"></li>
				<li class="menu-item">
					<a href="!#">Facebook</a>
				</li>
				<li class="menu-item">
					<a href="!#">Twitter</a>
				</li>
				<li class="menu-item">
					<a href="!#">Instagram</a>
				</li>
			</ul>
		</div>
		<div class="frame-footer"></div>
	</div>

	<ul class="menu">
		<li class="menu-item">
			<div class="menu-addon">
				<span class="icon">
					<i class="fa fa-wrapper fa-clock-o" aria-hidden="true"></i>
				</span>
			</div>
			<a href="!#">Real-Time</a>
		</li>
		<li class="menu-item selected">
			<div class="menu-addon">
				<span class="icon">
					<i class="fa fa-wrapper fa-user" aria-hidden="true"></i>
				</span>
			</div>
			<a href="!#">Audience</a>
			<ul class="menu">
				<li class="menu-item">
					<a href="!#">Overview</a>
				</li>
				<li class="menu-item">
					<a href="!#">Active Users</a>
				</li>
				<li class="menu-item">
					<a href="!#">Lifetime Value <sup>BETA</sup></a>
				</li>
				<li class="menu-item">
					<a href="!#">Cohort Analytics <sup>BETA</sup></a>
				</li>
			</ul>
		</li>
		<li class="menu-item">
			<div class="menu-addon">
				<span class="icon">
					<i class="fa fa-wrapper fa-share-alt" aria-hidden="true"></i>
				</span>
			</div>
			<a href="!#">Acquisition</a>
		</li>
	</ul>

## Modals
