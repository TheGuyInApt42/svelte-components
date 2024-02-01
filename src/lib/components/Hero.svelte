<div class="hero">
	<!--This feels like the wrong solution here :/ -->
	<fieldset class="hero-text">
		<legend class="border-text">Get Started</legend>
		<h1>Mr. Do It All</h1>
		<p>Customer Satisfaction is my attraction</p>
		<a href="#scroll2"><button>Get Free Quote</button></a>
	</fieldset>
</div>

<style>
	@import url('https://fonts.googleapis.com/css2?family=Baloo+Paaji+2:wght@400;700&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Montserrat&family=Varela+Round&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Abril+Fatface&family=IBM+Plex+Sans:wght@100;500&family=IBM+Plex+Serif:ital,wght@0,100;0,500;0,600;0,700;1,500;1,700&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght@900&display=swap');
	@import url('https://fonts.googleapis.com/css2?family=Gotu&display=swap');

	.hero-text {
		position: absolute;
		width: 20%;
		left: 5%;
		top: 25%;
		color: white;
		font-family: 'Montserrat', sans-serif;
		font-weight: 300;
		font-size: 22px;
	}
	.hero-text h1 {
		font-weight: 400;
		font-family: 'Varela Round', sans-serif;
		font-size: 46px;
	}
	.hero-text button {
		margin-top: 25px;
		border-radius: 10px;
		padding: 10px;
		font-size: 36px;
		border-radius: 10px;
		border: none;
		box-shadow: 0 6px 6px rgba(0, 0, 0, 0.25);
		font-size: 22px;
	}
	.hero-text button a {
		letter-spacing: 1.5px;
		font-family: 'Varela Round', sans-serif;
		color: #6f2a59;
	}
	.hero-text button:hover {
		transform: translate(1px, 1px);
		box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
		color: #4a1c3b;
	}

	.hero {
		width: 100%;
		height: 100%;
		background-size: cover;
		/*background-image: linear-gradient(to bottom left, rgba(0, 0, 0, 0.4), black), 
  url("/images/junk3.jpg");*/
		background-color: #9dc5c3;
		background-image: linear-gradient(315deg, #9dc5c3 0%, #5e5c5c 74%);
		background-position: center;
		filter: grayscale(40%);
		margin: 0;
		padding: 0;
		overflow: hidden;
	}

	.border-text {
		width: 160px;
		text-transform: uppercase;
		z-index: 1;
		font-size: 18px;
		letter-spacing: 1.8px;
		color: #deb221;
		text-align: left;
		overflow: hidden;
	}

	.hero-text {
		z-index: 0;
		width: 35%;
		top: 35%;
		font-family: 'IBM Plex Serif', serif;
		letter-spacing: 1.8px;
		position: relative;
		border: solid rgba(222, 178, 33, 0.3) 2px;
		padding-left: 40px;
		padding-right: 30px;
	}
	.hero-text p {
		margin: 0px;
	}
	.hero-text h1 {
		font-family: 'Abril Fatface', cursive;
		font-size: 52px;
		letter-spacing: 4px;
	}
	.hero-text button {
		position: relative;
		border: solid #deb221 3px;
		border-radius: 0;
		background-color: #212121;
		text-transform: uppercase;
		font-family: 'IBM Plex Serif', serif;
		letter-spacing: 2px;
		margin-left: 0;
		bottom: -40px;
		color: #deb221;
		font-size: 18px;
	}
	.hero-text button:hover {
		transform: translate(0px);
		box-shadow: 0px 2px 2px rgba(0, 0, 0, 0.25);
		color: #deb221;
		background-color: black;
		border: solid #deb221 3px;
	}




	@media only screen and (max-width: 600px) {

		.hero-text {
			top: 10px;
			margin: auto;
		}

		.hero-text h1 {
			font-size: 30px;
		}

		.hero-text p {
			font-size: 18px;
		}
	
		.hero-text button {
			font-size: 16px;
		}
	}
</style>
