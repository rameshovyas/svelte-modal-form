<script>
	
	import Modal from './Modal.svelte';
	import ContactForm from './ContactForm.svelte';

	let contacts=[];

	let showModal = false;	
	
	const toggleModal = () =>{
		showModal = !showModal;
	}

	const addContact = (e) =>{
		//console.log(e.detail);
		const contact = e.detail;
		contacts = [...contacts, contact];
		console.log(contacts);
	}

</script>

<Modal {showModal} isPromo={true} on:click={toggleModal}>
	<ContactForm on:addContact={addContact}/>
</Modal>

<main>
	<button on:click={toggleModal}>
		Click to show Modal
	</button>
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h1 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 4em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>