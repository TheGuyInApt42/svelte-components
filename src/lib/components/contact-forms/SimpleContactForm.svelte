<script>
	import dayjs from 'dayjs';
	import * as yup from 'yup';

	let date = new Date();

    //Props
    export let formUrl = 'https://getform.io/f/32cad38b-b77b-481e-8313-5b4d57fb06e1'
    export let emailAddress = 'chefwillcherry@gmail.com'
    /* export let socialLinks = [
        {
            icon: "Facebook",
            path: "#"
        },
        {
            icon: "Facebook",
            path: "#"
        },
        {
            icon: "Facebook",
            path: "#"
        },

    ]  */



	async function sendForm (data) {
		console.log(data);
		const res = await fetch(formUrl, {
			method: 'POST',
			body: JSON.stringify({
				data
			})
		})
		
		const json = await res.json()
		result = JSON.stringify(json)
		console.log(result);
	}

	
    
    let values = {
        email: "",
        firstName: "",
        lastName: "",
        subject: "",
        message: "",
    };

	let errors = {};

	const schema = yup.object().shape({
      email: yup.string().required("Email is required")
        .email("Email is invalid"),
      firstName: yup.string().required("First Name is required"),
      lastName: yup.string(),
      subject: yup.string(),
      message: yup.string().required("Message is required")
    });

	const handleSubmit = async () => {
        try {
          await schema.validate(values, { abortEarly: false });
		  sendForm(values)
          alert(JSON.stringify(values, null, 2));
          errors = {};
        } catch (err) {
          errors = err.inner.reduce((acc, err) => {
			console.log(errors);
            return { ...acc, [err.path]: err.message };
          }, {});
        }
      };

</script>

<section class="mt-16 text-center px-8 pb-8" id="contact">
	<h2 class="text-3xl pb-6 font-bold">Contact Me</h2>
	<h3 class="text-2xl pb-20">I would love to hear from you!</h3>

	<div class="flex justify-center gap-24 md:gap-48 flex-col md:flex-row">
		<!-- Email-->
		<div class="flex flex-col">
			<h4 class="mb-4">Contact</h4>
			<p>{emailAddress}</p>

			<!-- Social Links-->
			<div class="flex flex-col items-center justify-center mt-8">
				<h4>Socials</h4>
				<div class="flex gap-4 mt-4">
					<!-- Facebook -->
					<a href="#">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="24"
							height="24"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
							class="lucide lucide-facebook"
							><path d="M18 2h-3a5 5 0 0 0-5 5v3H7v4h3v8h4v-8h3l1-4h-4V7a1 1 0 0 1 1-1h3z" /></svg
						>
					</a>

					<!-- Instagram-->
					<a href="#">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="24"
							height="24"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
							class="lucide lucide-instagram"
							><rect width="20" height="20" x="2" y="2" rx="5" ry="5" /><path
								d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"
							/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5" /></svg
						>
					</a>

					<!-- Youtube -->
					<a href="#">
						<svg
							xmlns="http://www.w3.org/2000/svg"
							width="24"
							height="24"
							viewBox="0 0 24 24"
							fill="none"
							stroke="currentColor"
							stroke-width="2"
							stroke-linecap="round"
							stroke-linejoin="round"
							class="lucide lucide-youtube"
							><path
								d="M2.5 17a24.12 24.12 0 0 1 0-10 2 2 0 0 1 1.4-1.4 49.56 49.56 0 0 1 16.2 0A2 2 0 0 1 21.5 7a24.12 24.12 0 0 1 0 10 2 2 0 0 1-1.4 1.4 49.55 49.55 0 0 1-16.2 0A2 2 0 0 1 2.5 17"
							/><path d="m10 15 5-3-5-3z" /></svg
						>
					</a>
				</div>
			</div>
		</div>

		<!-- Form -->
		<form action={formUrl} method="POST" class="flex flex-col md:w-1/2">
            <!-- First Name-->
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">First Name</span>
				</label>
			<input type="text"  minlength="2" maxlength="20" name="First Name" pattern="[A-Za-z]{2,20}" class="input input-bordered  w-full md:max-w-xs" bind:value={values.firstName}/>
			</div>
			{#if errors.firstName}
			<span class="flex items-center font-medium tracking-wide text-red-500 text-xs mt-1 ml-1">
			{errors.firstName}
		</span>
		{/if}
            
            <!-- Last Name -->
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">Last Name</span>
				</label>
            <input type="text" pattern="[A-Za-z]{1,20}" maxlength="20" name="Last Name" class="input input-bordered w-full md:max-w-xs" bind:value={values.lastName}/>
			</div>
			{#if errors.lastName}
			<span class="flex items-center font-medium tracking-wide text-red-500 text-xs mt-1 ml-1">
			{errors.lastName}
		</span>
		{/if}

			<input type="hidden" name="_gotcha" style="display:none !important">
            
            <!-- Email -->
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">Email</span>
				</label>
            <input type="email" name="email" class="input input-bordered w-full md:max-w-xs" required bind:value={values.email}/>
			</div>
			{#if errors.email}
			<span class="flex items-center font-medium tracking-wide text-red-500 text-xs mt-1 ml-1">
			{errors.email}
		</span>
		{/if}
            
            <!-- Subject -->
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">Subject</span>
				</label>
            <input type="text" pattern="[A-Za-z]{1,32}" maxlength="32" name="subject" class="input input-bordered w-full md:max-w-xs" bind:value={values.subject}/>
			</div>
			{#if errors.subject}
			<span class="flex items-center font-medium tracking-wide text-red-500 text-xs mt-1 ml-1">
			{errors.subject}
		</span>
		{/if}
            
            <!-- Message-->
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">Message</span>
				</label>
            <textarea maxlength="100" name="message" class="textarea textarea-bordered md:max-w-xs"  required bind:value={values.message}/>
			</div>
			{#if errors.message}
			<span class="flex items-center font-medium tracking-wide text-red-500 text-xs mt-1 ml-1">
			{errors.message}
		</span>
		{/if}
            
            <div class="form-control w-full md:max-w-xs">
				<label class="label">
					<span class="label-text">Event Date:</span>
				</label>
				<input
					class="input input-bordered w-full md:max-w-xs"
					bind:value={date}
					type="date"
					id="eventDate"
					min={dayjs(date).format('YYYY-MM-DD')}
					required
					name="date"
				/>
			</div>
			<!-- Referral-->
            <span class="self-start my-4">How did you hear about me?</span>
			<div class="form-control md:max-w-xs">
				<label class="label cursor-pointer">
					<span class="label-text">Google</span>
					<input type="radio" name="referral" class="radio checked:bg-blue-500" value="Google" />
				</label>
			</div>
			<div class="form-control md:max-w-xs">
				<label class="label cursor-pointer">
					<span class="label-text">Instagram</span>
					<input type="radio" name="referral" class="radio checked:bg-blue-500" value="Instagram" />
				</label>
			</div>
			<div class="form-control md:max-w-xs">
				<label class="label cursor-pointer">
					<span class="label-text">Referral</span>
					<input type="radio" name="referral" class="radio checked:bg-blue-500" value="Referral" />
				</label>
			</div>
			<div class="form-control md:max-w-xs">
				<label class="label cursor-pointer">
					<span class="label-text">Brochure</span>
					<input type="radio" name="referral" class="radio checked:bg-blue-500" value="Brochure" />
				</label>
			</div>

			<button class="btn btn-primary md:max-w-xs" >Submit</button>
		</form>
	</div>
</section>
