<script>
  import EmblaCarousel_ArrowButtons from "$lib/components/EmblaCarousel_ArrowButtons.svelte";
  import Embla_Carousel_AutoScroll_X from "$lib/components/Embla_Carousel_AutoScroll_X.svelte";
  import Embla_Carousel_AutoScroll_Y from "$lib/components/Embla_Carousel_AutoScroll_Y.svelte";
</script>

<div class="main-wrapper">
  <div class="main-content-container">
  <h1>Embla Carousel Components</h1>
  </div>
  <div class="embla-components-container">
    <div class="component-container">
      <EmblaCarousel_ArrowButtons/>
    </div>
    <div class="component-container">  <Embla_Carousel_AutoScroll_X/></div>
    <div class="component-container"> <Embla_Carousel_AutoScroll_Y/></div>
    <div class="component-container link-box">
<p>Embla Carousel SvelteKit (get-started):</p>
      <br>
      <a href="https://www.embla-carousel.com/get-started/svelte/"
         rel="norefferer noopener"
         target="_blank">Click me</a>
    </div>
  </div>
</div>


<style lang="scss">
  .main-wrapper{
    min-height: 100vh;
    width: 100%;
    padding: 2rem;
    display: grid;
    grid-template-rows: 100px 1fr;
    grid-template-columns: 1fr;
    place-content: center;
  }
.main-content-container{
  display: grid;
  place-content: center;
}
  .embla-components-container{
    display: grid;
    place-content: center;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: auto;
    gap: 10px;
    border-radius: 10px;

    @media (max-width: 800px){
      grid-template-columns: 1fr;
      grid-template-rows: auto;
    }

    .component-container{
      height: 100%;
      width: 100%;
      border: 2px solid grey;
      border-radius: 10px;  display: grid;
      place-content: center;
      min-width: 400px;
      min-height: 300px;
      position: relative;
    }
  }

.link-box{
  font-family: "League Spartan", sans-serif;
font-weight: bold;
  font-size: 1.25rem;

  p,a{
    width: 100%;
    text-align: center;
    text-decoration: none;
  }
  a{
    color: #00adb5;
    &:hover{
      color: #9b9b9b;}
  }
}

</style>



