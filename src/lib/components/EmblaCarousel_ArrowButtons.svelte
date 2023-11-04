<script type="text/javascript">
  import emblaCarouselSvelte from "embla-carousel-svelte";

  let emblaApi;
  let options = { loop: true };
  let plugins = [];

  let prevButtonEnabled = false;
  let nextButtonEnabled = false;

  const onInit = () => {
    emblaApi = event.detail;
    emblaApi.on("select", onSelect);
    emblaApi.on("reInit", onSelect);
    onSelect();
  };

  const onSelect = () => {
    if (!emblaApi) return;
    prevButtonEnabled = emblaApi.canScrollPrev();
    nextButtonEnabled = emblaApi.canScrollNext();
  };

  const scrollPrev = () => {
    if (emblaApi) emblaApi.scrollPrev();
  };

  const scrollNext = () => {
    if (emblaApi) emblaApi.scrollNext();
  };
</script>

<div class="section-header">
  arrow-btn, autoplay=off
</div>
<section class="embla">
  <div class="embla__viewport" use:emblaCarouselSvelte={{ options, plugins }} on:emblaInit={onInit}>
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
  <button
    class="embla__button embla__button--prev"
    on:click={scrollPrev}
    disabled={!prevButtonEnabled}
  >
    <svg class="embla__button__svg" viewBox="137.718 -1.001 366.563 644">
      <path d="M428.36 12.5c16.67-16.67 43.76-16.67 60.42 0 16.67 16.67 16.67 43.76 0 60.42L241.7 320c148.25 148.24 230.61 230.6 247.08 247.08 16.67 16.66 16.67 43.75 0 60.42-16.67 16.66-43.76 16.67-60.42 0-27.72-27.71-249.45-249.37-277.16-277.08a42.308 42.308 0 0 1-12.48-30.34c0-11.1 4.1-22.05 12.48-30.42C206.63 234.23 400.64 40.21 428.36 12.5z" />
    </svg>
  </button>
  <button
    class="embla__button embla__button--next"
    on:click={scrollNext}
    disabled={!nextButtonEnabled}
  >
    <svg class="embla__button__svg" viewBox="0 0 238.003 238.003">
      <path d="M181.776 107.719L78.705 4.648c-6.198-6.198-16.273-6.198-22.47 0s-6.198 16.273 0 22.47l91.883 91.883-91.883 91.883c-6.198 6.198-6.198 16.273 0 22.47s16.273 6.198 22.47 0l103.071-103.039a15.741 15.741 0 0 0 4.64-11.283c0-4.13-1.526-8.199-4.64-11.313z" />
    </svg>
  </button>
</section>
