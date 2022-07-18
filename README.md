# W&I Library

This CSS library is meant to be used in conjunction with [Compassion.com's Site MVP CSS](https://www.compassion.com/css/site-mvp.css) 

## Table of Contents

- [Settings](#settings)
	- [Breakpoints](#breakpoints)
  - [Colors](#colors)
- [Grid](#grid)
	- [Container](#container)
	- [Row](#row)
	- [Column](#column)
- [Components](#components)
	- [Feature](#feature)
- [Utilities](#utilities)
  - [Aspect Ratios](#aspect-ratios)
  - [Background Colors](#background-colors)
  - [Box Shadow](#box-shadow)
  - [Display](#display)
  - [Flex](#flex)
    - [Align Items](#align-items)
    - [Align Self](#align-self)
    - [Justify Content](#justify-content)
    - [Order](#order)
    - [Wrap](#wrap)
  - [Overflow](#overflow)
  - [Spacing](#spacing)
    - [Spacing Axis](#spacing-axis)
    - [Spacing Units](#spacing-units)
    - [Margin](#margin)
    - [Padding](#padding)
    - [Gutter](#gutter)
  - [Text](#text)
    - [Text Alignment](#text-alignment)
    - [Text Color](#text-color)
    - [Text Decoration](#text-decoration)
    - [Text Line Heights](#text-line-heights)
    - [Font Sizes](#font-sizes)
    - [Font Weights](#font-weights)

## Settings

Settings are used throughout the library to populate color, grid, spacing, display and alignments options.

### Breakpoints

The library comes with 6 distinct breakpoints. These breakpoints are used throughout the project for other tools, objects, components and utilities.

| Breakpoint | REM     | PX     |
|------------|---------|--------|
| xs         | 22.5rem | 360px  |
| sm         | 32.5rem | 520px  |
| md         | 45rem   | 720px  |
| lg         | 62.5rem | 1000px |
| xl         | 80rem   | 1280px |
| xxl        | 100rem  | 1600px | 

Breakpoints are used as a modifier for other stylings. For instance, you may want to have an element show a different text color on mobile opposed to the desktop version. To do this, you would add the breakpoint modifier to the class.

```html
<div class="text-white text-md-black"></div>
```

The above markup would show white text for devices under the `md` breakpoint width, but black text for devicdes over the `md` breakpoint width.

---

### Colors

Below is a list of commonly used colors in the library that are used to transform backgrounds, typography and other color-related attributes.

|                                                                  | name      | hex       |
|------------------------------------------------------------------|-----------|-----------|
| ![#000](https://via.placeholder.com/15/000/000000?text=+)        | black     | `#000000` |
| ![#005eb8](https://via.placeholder.com/15/005eb8/000000?text=+)  | blue      | `#005eb8` |
| ![#F1F9FF](https://via.placeholder.com/15/F1F9FF/000000?text=+)  | blue100   | `#F1F9FF` |
| ![#D1E4F2](https://via.placeholder.com/15/D1E4F2/000000?text=+)  | blue200   | `#D1E4F2` |
| ![#4BA3E4](https://via.placeholder.com/15/4BA3E4/000000?text=+)  | blue500   | `#4BA3E4` |
| ![#00386d](https://via.placeholder.com/15/00386d/000000?text=+)  | blue900   | `#00386d` |
| ![#20556B](https://via.placeholder.com/15/20556B/000000?text=+)  | dark-teal | `#20556B` |
| ![#FFB500](https://via.placeholder.com/15/FFB500/000000?text=+)  | gold      | `#FFB500` |
| ![#425563](https://via.placeholder.com/15/425563/000000?text=+)  | gray      | `#425563` |
| ![#f9f9f9](https://via.placeholder.com/15/f9f9f9/000000?text=+)  | gray100   | `#f9f9f9` |
| ![#CCCCCC](https://via.placeholder.com/15/cccccc/000000?text=+)  | gray200   | `#CCCCCC` |
| ![#D8D8D8](https://via.placeholder.com/15/D8D8D8/000000?text=+)  | gray300   | `#D8D8D8` |
| ![#798894](https://via.placeholder.com/15/798894/000000?text=+)  | gray500   | `#798894` |
| ![#425563](https://via.placeholder.com/15/425563/000000?text=+)  | gray700   | `#425563` |
| ![#C13E2D](https://via.placeholder.com/15/C13E2D/000000?text=+)  | red       | `#C13E2D` |
| ![#0086BF](https://via.placeholder.com/15/0086BF/000000?text=+)  | teal      | `#0086BF` |
| ![#FFFFFF](https://via.placeholder.com/15/FFFFFF/000000?text=+)  | white     | `#FFFFFF` |
| ![#ffd100s](https://via.placeholder.com/15/ffd100/000000?text=+) | yellow    | `#ffd100` |


---

## Grid

### Container

The container object is used to "contain" content within a bounds, and provide a gutters for the content.

```html
<div class="container">
	...
</div>
```

This object has varients based on the [breakpoint widths](#breakpoints).

```html
<!-- XL container-->
<div class="container-xl">
	...
</div>

<!-- LG container -->
<div class="container-lg">
	...
</div>
```

### Row

This object is a flex container, intended for use in conjunction with the [Container](#container) and [Column](#column) objects.

```html
<div class="row">
	...
</div>
```

### Column

This object adds right and left gutters, while flexing to certain percantages of a base 12 grid.

```html
<div class="row">
	<!-- Full width -->
	<div class="col-12">
		...
	</div>
</div>
```

The column can be adjusted based on particualr breakpoints. (<a href="#breakpoints">See breakpoints</a>)

```html
<div class="row">
	<!-- Full width, then 4/12 width at medium viewport -->
	<div class="col-12 col-md-4">
		...
	</div>

	<!-- Full width, then 8/12 width at medium viewport -->
	<div class="col-12 col-md-8">
		...
	</div>
</div>
```

## Components

### Feature

The feature is used in the hero spot of the page or in an area that you want to draw attention.

```html
<div class="feature bg-gray text-white">
  <div class="feature__background">
    <!-- DESKTOP IMAGE -->
    <img class="feature__background-image d-none d-lg-block" src="{{imagePath}}" />
    <!-- TABLET IMAGE -->
    <img class="feature__background-image d-none d-md-block d-lg-none" src="{{imagePath}}" />
    <!-- MOBILE IMAGE -->
    <img class="feature__background-image d-md-none" src="{{imagePath}}" />
  </div>
  <div class="feature__content">
    <!-- CONTENT GOES HERE -->
    <div class="container-xl p-y-5 p-md-y-8">
      <div class="row">
        <div class="col-12 col-md-6">
          <h1>This is a feature section</h1>
        </div>
      </div>
    </div>
  </div>
</div>
```

---

## Utilities

### Aspect Ratios

If you need an element to fit a certain aspect ratio, this is the utility for you. The class is formatted as such: `aspect-{ratio}`.

| Name       | Ratio                                 |
|------------|---------------------------------------|
| sqaure     | 1:1                                   |
| standard   | 4:3                                   |
| wide       | 16:9                                  |
| letterbox  | 2.35:1                                |
| responsive | Conforms to size of parent container. |

```html
<div class="aspect-square">
  <img src="{src}" alt="A sqaure image" />
</div>

<div class="aspect-wide aspect-md-responsive">
  <img src="{src}" alt="An image that is responsive above the md breakpoint and 16:9 below it." >
</div>
```

### Background Colors

You can apply a background color to an element by giving it a class of `bg-{colorName}`.

```html
<div class="bg-gray"><!--CONTENT HERE --></div>
```

The above markup would produce a `<div>` with a gray background. (<a href="#colors">See colors</a>)

You may also set a background color to transparent by using the class name `bg-transparent`.

This can be modified by adding the breakpoint modifier to the class name. `bg-md-gray` would give a gray background to the element only at or above the `md` breakpoint. (<a href="#breakpoints">See breakpoints</a>)

### Box Shadow

```html
<div class="box-shadow-1"></div>
```

You can affect the box shadow property of an element by choosing an option below:

| name | value                                  |
|------|----------------------------------------|
| none | box-shadow: none                       |
| 1    | box-shadow: 0 3px 6px rgba(0,0,0,.15)  |
| 2    | box-shadow: 0 3px 12px rgba(0,0,0,.15) |
| 3    | box-shadow: 0 3px 25px rgba(0,0,0,.15) |

### Display

```html
<!-- A link displayed as a block -->
<a class="d-block">Link</a>
```

You can modify the display property of an element by using on the following options:


| name           | description                      |
|----------------|----------------------------------|
| d-none         | sets the display to none         |
| d-block        | sets the display to block        |
| d-flex         | sets the display to flex         |
| d-grid         | sets the display to grid         |
| d-inline       | sets the display to inline       |
| d-inline-block | sets the display to inline-block |
| d-inline-flex  | sets the display to inline-flex  |

```html
<div class="d-none d-lg-block">Woot woot</div>
```

The above markup would be hidden for viewports below `lg`, but displayed as black for `lg` viewports and above.

### Flex

Flex options can be modified.

#### Align Items

```html
<div class="row align-items-center">
  <!-- FLEXED CONTENT -->
</div>
```

| name                   | description                                |
|------------------------|--------------------------------------------|
| align-items-center     | align items of flex container to center    |
| align-items-flex-start | align items of flex container to beginning |
| align-items-flex-end   | align-items of felx container to end       |

#### Align Self

```html
<div class="row">
  <div class="col-12 align-self-center"></div>
</div>
```

| name                  | description             |
|-----------------------|-------------------------|
| align-self-center     | align self to center    |
| align-self-flex-start | align self to beginning |
| align-self-flex-end   | align self to end       |

#### Justify Content

```html
<div class="row justify-content-center">
  <!-- FLEXED CONTENT -->
</div>
```

| name                       | description                                    |
|----------------------------|------------------------------------------------|
| justify-content-center     | justify content of flex container to center    |
| justify-content-flex-start | justify content of flex container to beginning |
| justify-content-flex-end   | justify content of felx container to end       |

#### Order

```html
<div class="row">
  <!-- order-1 will be shown second -->
  <div class="col-6 order-1"></div>
  <!-- order-0 will be shown first -->
  <div class="col-6 order-0"></div>
</div>
```

The order of a flex container can be modified.

| name | description            | 
|------|------------------------|
| 0    | order will be set to 0 |
| 1    | order will be set to 1 |
| 2    | order will be set to 2 |
| 3    | order will be set to 3 |
| 4    | order will be set to 4 |
| 5    | order will be set to 5 |


#### Wrap

```html
<div class="flex-nowrap"><!-- FLEX WILL NOT WRAP --></div>
```

| name   | description                           |
|--------|---------------------------------------|
| nowrap | items in flex box will not wrap       |
| wrap   | items in flex box will wrap (default) |

### Overflow

Set the oveflow property of an element.

```html
<div class="overflow-auto"></div>
```

| name   | description                          |
|--------|--------------------------------------|
| auto   | sets the overflow property to auto   |
| hidden | sets the overflow property to hidden |

### Rounded

```html
<div class="rounded-1"></div>
```

Will set a rounded edge for the element.

| name   | value                 |
|--------|-----------------------|
| none   | border-radius: 0      |
| 1      | border-radius: .25rem |
| 2      | border-radius: .5rem  |
| 3      | border-radius: 1rem   |
| circle | border-radius: 50%    |


### Spacing

Set padding and margins for an element.

#### Spacing Axis

| name | description    |
|------|----------------|
| t    | top            |
| b    | bottom         |
| tb   | top and bottom |
| r    | right          |
| l    | left           |
| rl   | right and left |

#### Spacing Units

| name | value  |
|------|--------|
| 0    | 0rem   |
| 1    | .25rem |
| 2    | .5rem  |
| 3    | .75rem |
| 4    | 1rem   |
| 5    | 2rem   |
| 6    | 3rem   |
| 7    | 4rem   |
| 8    | 5rem   |

#### Margin

```html
<div class="m-2">
  <!-- ALL MARGIN AXIS ARE SET TO SPACING UNIT 2 -->
</div>
<div class="m-rl-2">
  <!-- MARGIN RIGHT AND LEFT SET TO SPACING UNIT 2 -->
</div>
```

You can also set margin to negative by adding an `n` modifier to the spacing unit number.

```html
<div class="m-rl-n2">
  <!-- MARGIN RIGHT AND LEFT SET TO NEGATIVE SPACING UNIT 2 -->
</div>
```

#### Padding

```html
<div class="p-rl-n2">
  <!-- PADDING RIGHT AND LEFT SET TO NEGATIVE SPACING UNIT 2 -->
</div>
```

#### Gutter

Gutter is the space between columns and the row.

| name | description                                                               |
|------|---------------------------------------------------------------------------|
| 1    | row margin left and right of -0.5rem, column padding left/right of 0.5rem |
| 2    | row margin left and right of -1rem, column padding left/right of 1rem     |
| 3    | row margin left and right of -1.5rem, column padding left/right of 1.5rem |
| 4    | row margin left and right of -2rem, column padding left/right of 2rem     |

### Text

#### Text Alignment

| name        | description         |
|-------------|---------------------|
| text-left   | text aligned left   |
| text-center | text aligned center |
| text-right  | text aligned right  |

#### Text Color

See [color variables](#colors) above for a complete list of colors.

```html
<div class="text-blue">Blue text goes here.</div>
```

#### Text Decoration

| name              | description          |
|-------------------|----------------------|
| text-line-through | line through word    |
| text-none         | no text decoraitions |
| text-underline    | underline word       |

#### Text Line Heights

| name               | value |
|--------------------|-------|
| text-line-height-1 | 1em   |
| text-line-height-2 | 1.3em |
| text-line-height-3 | 1.8em |

#### Font Sizes

| name      | value   |
|-----------|---------|
| text-1    | .875rem |
| text-2    | 1rem    |
| text-3    | 1.25rem |
| text-4    | 1.5rem  |
| text-5    | 1.75rem |
| text-6    | 2rem    |
| text-7    | 2.5rem  |
| text-8    | 3rem    |
| text-9    | 4rem    |
| text-10   | 5rem    |

#### Font Weights

| name           | value            |
|----------------|------------------|
| text-lighter   | font-weight: 400 |
| text-normal    | font-weight: 500 |
| text-bold      | font-weight: 700 |
| text-400       | font-weight: 400 |
| text-500       | font-weight: 500 |
| text-700       | font-weight: 700 |