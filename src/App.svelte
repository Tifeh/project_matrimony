<script>
	let name = '';
	let email = '';
	let meal = '';
	let guests = '';
	let attendance = true;

	$: console.log(attendance);

	function submitForm() {
		console.log(document.querySelector('#name').value)
		console.log(document.querySelector('#email').value)
		console.log(document.querySelector('#attendance').value)
		console.log(document.querySelector('#meal').value)
		console.log(document.querySelector('#guests').value)
	}

</script>

<style>
	.formContainer {
		width: 30rem;
		max-width: 90%;
		margin: auto;
		margin-top: 2rem;
	}

	h2 {
		text-align: center;
		margin-top: 5rem;
	}
</style>

<div id="carouselExampleControls" class="carousel slide" data-ride="carousel">
	<div class="carousel-inner">
		<div class="carousel-item active">
			<img src="https://www.theknotnews.com/wp-content/uploads/2018/07/Scotty-McCreery-Wedding-LEAD-1500x1200.jpg"
					 class="d-block w-100" alt="Carousel1">
		</div>
		<div class="carousel-item">
			<img src="https://www.theknotnews.com/wp-content/uploads/2018/07/Scotty-McCreery-Wedding-LEAD-1500x1200.jpg"
					 class="d-block w-100" alt="Carousel2">
		</div>
		<div class="carousel-item">
			<img src="https://image.freepik.com/free-photo/groom-kisses-bride-rose-petals_172134-33.jpg"
					 class="d-block w-100" alt="Carousel3">
		</div>
	</div>
	<a class="carousel-control-prev" href="#carouselExampleControls" role="button" data-slide="prev">
		<span class="carousel-control-prev-icon" aria-hidden="true"></span>
		<span class="sr-only">Previous</span>
	</a>
	<a class="carousel-control-next" href="#carouselExampleControls" role="button" data-slide="next">
		<span class="carousel-control-next-icon" aria-hidden="true"></span>
		<span class="sr-only">Next</span>
	</a>
</div>

<h2>Join Us</h2>
<div class="formContainer">
	<form on:submit|preventDefault={submitForm}>
	<div class="form-group">
		<label for="name">Name</label>
		<input type="text" class="form-control" id="name"
					 bind:this={name}/>
	</div>
	<div class="form-group">
	<label for="email">E-mail</label>
	<input type="text" class="form-control" id="email"
				 bind:this={email}/>
	</div>
	<div class="form-group">
		<label>
		<input type=radio name="attendance" id="attendance" value={true} bind:group={attendance} >
		Yes, I will be there
	</label>
		<label>
		<input type=radio name="attendance" id="attendance" value={false} bind:group={attendance}>
		Sorry, I can't come
	</label>
	</div>
	<div class="form-group">
		<label for="meal">Meal Preference</label>
		<input type="text" class="form-control" id="meal"
					 bind:this={meal}/>
	</div>
	<div class="form-group">
	<label for="guests">Number of Guests</label>
	<input type="text" class="form-control" id="guests"
				 bind:this={guests}/>
</div>
</form>

	<button type=submit on:click={submitForm}>RSVP</button>
</div>
