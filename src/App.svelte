<script>
	import Header from './component/Header/Header.svelte'
	import Body from './component/Body/Base.svelte'
	import Modal from './component/Base/Modal.svelte'


	let showModal = false;
	const toggleModal = () => {
		showModal = !showModal
	}
</script>

<Modal {showModal} on:click={toggleModal} title="Log Event" day="Today" time="8:50AM"/>
<main>
	<Header>
		<div class="add-event" on:click={toggleModal}></div>
	</Header>
	<Body />
</main>