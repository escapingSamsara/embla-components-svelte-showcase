<script type="text/javascript">
  import emblaCarouselSvelte from "embla-carousel-svelte";
  import Autoplay from "embla-carousel-autoplay";
  let options = { loop: true, draggable: true, axis: 'y', startIndex: 0 };// axis: 'x' | 'y' | 'both', x=default
  const autoplayOptions = {
    delay: 3000,
    stopOnInteraction: false,
    stopOnMouseEnter: true
  };
  let plugins = [Autoplay(autoplayOptions)];
</script>

<div class="section-header">
  autoplay=on (y-axis)
</div>
<section class="embla">
  <div class="embla__viewport" use:emblaCarouselSvelte={{ options, plugins }}>
    <div class="embla__container">
      <div class="embla__slide">
        <img
          class="embla__slide__img"
          src="https://placekitten.com/g/800/300"
          alt="alt"
        />
      </div>
      <div class="embla__slide">
        <img
          class="embla__slide__img"
          src="https://placekitten.com/g/800/300"
          alt="alt"
        />
      </div>
      <div class="embla__slide">
        <img
          class="embla__slide__img"
          src="https://placekitten.com/g/800/300"
          alt="alt"
        />
      </div>
    </div>
  </div>
</section>

<style lang="scss">
    .embla__container {
      display: flex;
      margin-left: -10px;
      flex-direction: column;
      height: 300px;
    }
</style>