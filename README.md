# vue-animate for Vue.js

修改自 [vue2-animate](https://github.com/asika32764/vue2-animate)，方便文件引入

## 安装

```shell
npm install --save @wjtools/vue-animate

# OR

yarn add @wjtools/vue-animate
```

```js
require('vue-animate/dist/vue-animate.min.css')
```

## SASS/SCSS

```scss
$animationDuration: 0.5s; // specify animation duration. Default value: 1s
@import "<PATH_TO_SOURCE>/src/sass/vue-animate.scss";
```

## 用法

Use [Vue.js transitions](http://vuejs.org/guide/transitions.html "Vue.js Transitions") as you normally would, but for the transition name you will use one of [Animate.css animations](https://github.com/daneden/animate.css#basic-usage "animations") **removing** the ***In/Out*** from the name.

For example, if I want to use *fadeInLeft* and *fadeOutLeft* on my element, I'll write:

```html
<transition-group name="fadeLeft" tag="ul">
    <li v-for="item in items" :key="item.id">
        {{ item }}
    </li>
</transition-group>
```
enter/leave is already written in the stylesheet, so just remove *In/Out* from the name and you're golden.

### Custom Transition Classes

Animate.css's original classnames are supported on enter/leave transitions. So if you're going to use [Custom Transition Classes](http://vuejs.org/guide/transitions.html#Custom-Transition-Classes "Custom Transition Classes"), you can either add *-enter/-leave* to the classes:

```html
<transition
  name="custom-classes-transition"
  enter-active-class="bounceLeft-enter"
  leave-active-class="bounceRight-leave"
>
  <p v-if="show">hello</p>
</transition>
```
  Or use the regular *In/Out* syntax:

```html
<transition
  name="bounce"
  enter-active-class="bounceInLeft"
  leave-active-class="bounceOutRight"
>
  <p v-if="show">hello</p>
</transition>
```

### Custom Animation Duration

```html
<transition name="fade">
  <p v-if="show" style="animation-duration: 0.3s">hello</p>
</transition>
```

## 支持的动画
  Not all [Animate.css animations](https://github.com/daneden/animate.css#basic-usage "animations") are supported at the moment. Here is a list of what's in vue2-animate (aka - *what you can put in the transition="x"* attribute) as of right now:

### Bounce
  * `bounce`
  * `bounceDown`
  * `bounceLeft`
  * `bounceRight`
  * `bounceUp`

### Fade
  * `fade`
  * `fadeDown`
  * `fadeDownBig`
  * `fadeLeft`
  * `fadeLeftBig`
  * `fadeRight`
  * `fadeRightBig`
  * `fadeUp`
  * `fadeUpBig`

### Rotate
  * `rotate`
  * `rotateDownLeft`
  * `rotateDownRight`
  * `rotateUpLeft`
  * `rotateUpRight`

### Slide
  * `slideDown`
  * `slideLeft`
  * `slideRight`
  * `slideUp`

### Zoom
  * `zoom`
  * `zoomDown`
  * `zoomLeft`
  * `zoomRight`
  * `zoomUp`
