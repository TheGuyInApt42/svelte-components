<script>

  import { onMount } from 'svelte';
  import Headroom from './Headroom.svelte';

  let menu;
let mobile = false;

export let navLinks = [
    {
			path: '#about',
			label: 'About',
	},
        {
			path: '#services',
			label: 'Services',
		},
         {
			path: '#gallery',
			label: 'Gallery',
		},
        {
			path: '#contact',
			label: 'Contact',
		},
]

  onMount(async() =>{
		menu = document.querySelector('#menu')
		const mobileDevice = window.matchMedia('(max-width: 768px)');
		mobileDevice.addEventListener('change', handleDeviceChange);
		function handleDeviceChange(e) {
			if (e.matches) mobile = true;
			else mobile = false;

		}
		// Run it initially
		handleDeviceChange(mobileDevice);

	})



	function toggleMenu(){
		if (mobile){
			menu.classList.toggle('hidden')
			menu.classList.toggle('w-full')
			menu.classList.toggle('h-screen')
		}
	}

</script>

<Headroom>
<div class="navbar bg-base-100">
  <div class="flex-1">
    <a href="/" class="btn btn-ghost normal-case text-xl">Will Cherry</a>
  </div>
  <nav class="flex-none">
    <ul id="menu" class="hidden fixed top-0 right-0 px-10 py-16 bg-white z-40  md:menu md:menu-horizontal 
					md:relative md:flex md:p-0 md:bg-transparent md:flex-row md:space-x-6">
      <!-- Close Mobile Menu-->
      <li class="md:hidden z-90 fixed top-4 right-6">
						<a href="#" class="text-right text-black text-4xl"
							on:click={toggleMenu}>&times;</a>
					</li>

        {#each navLinks as link}
            <li>
                <a href={link.path} on:click={toggleMenu}>{link.label}</a></li>

        {/each}

    </ul>
  </nav>

  <!-- This is used to open the menu on mobile devices -->
			<div class="flex items-center md:hidden">
				<button class="text-black  text-4xl font-bold  hover:opacity-100 duration-300 fixed top-4 right-6"
					on:click={toggleMenu}>
					&#9776;
				</button>
			</div>
</div>
</Headroom>

<style>
	@media screen and (max-width: 768px){
		#menu{
			padding-top: 8rem;
			
		}

		#menu li{
			font-size: 24px;
		
		}
	}


</style>