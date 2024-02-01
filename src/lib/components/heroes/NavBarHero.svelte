<script>
    import Navbar from '../headers/headroom/NavBar.svelte'

    export let cta = {
        text: 'Book Now',
        path: '#contact'
    }

    const ctaAction = cta =>{
        let action = document.querySelector(cta.path)
        action?.scrollIntoView()
    }
</script>

<div class="hero min-h-screen" style="background-image: url(https://res.cloudinary.com/blackgandalf/image/upload/w_1000,ar_16:9,c_fill,g_auto,e_sharpen/v1692283899/Cherry/IMG_1611_byf8gv.jpg);">
  <div class="hero-overlay bg-opacity-60">
    <Navbar />
  </div>
  
  <div class="hero-content text-center text-neutral-content flex flex-col">
    <div class="">
      <h1 class="mb-5 text-5xl font-bold">Experience Exquisite Culinary Delights with Personal Chef Cherry</h1>
      <p class="mb-5">Bringing Gourmet Dining to Your Doorstep</p>

      <button class="btn btn-primary" on:click={ctaAction}>{cta.text}</button>
    </div>

    <div class="flex flex-col relative ml-[80%] -bottom-[6rem]">
      <span class="text-xl">"This Is What I Do"</span>
      <span><em>- Will Cherry</em></span>
    </div>
    
  </div>
</div>