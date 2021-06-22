#note

## responsive img: srcset

```html
<div class="box">
  <img
    src="/files/16797/clock-demo-200px.png"
    alt="Clock"
    srcset="
      /files/16864/clock-demo-200px.png 1x,
      /files/16797/clock-demo-400px.png 2x
    "
  />
</div>
```

## layout: css grid/flex (probably flex for layout grid for the little galler)

section could be something like:

```html
<div class="section reverse">
  <img class="section__img" srcset... />
  <div class="section__content">
    <h2 class="section__title"></h2>
    <p class="section__paragraph"></p>
    <a href="#" class="section__btn"></a>
  </div>
</div>
```

```scss
//probably only set this for desktop
.section {
  display: flex;

  &__img,
  &__content {
    flex: 50%; //or 100% we'll see
  }
}
.reverse {
  flex-direction: row-reverse;
}
```

## testimonials cards

```html
<article class="section--testimonial card">
  <img class="card__profile" />
  <p class="card__text"></p>
  <div class="card__customer">
    <!-- <h3> or <h4> -->
    <h3 class="customer__name"></h3>
    <p class="customer__occupation"></p>
  </div>
</article>
```

## gallery

```html
<div class="section section--gallery">
  <img class="section--gallery__img" srcset... />
  <img class="section--gallery__img" srcset... />
  <img class="section--gallery__img" srcset... />
  <img class="section--gallery__img" srcset... />
</div>
```

```scss
.section--gallery {
  max-width: 100vw;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  &__img {
    width: 100%;
    object-fit: cover;
    object-position: center;
    background-size: 100%;
  }
}

@media only screen and (max-width: 1220px) {
  .gallery {
    grid-template-columns: repeat(2, 1fr);
  }
}
```
