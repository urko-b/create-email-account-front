<script>
	import Tailwindcss from './Tailwind.svelte';
    import Router from 'svelte-spa-router'
    import SignUp from './routes/SignUp.svelte'
    import { Modals, closeModal, openModal } from 'svelte-modals'
    import ModalComponent from "./components/TOSModal.svelte";


    function handleClick() {
        openModal(ModalComponent, { title: "Terms of Service" })
    }
</script>

<Tailwindcss />

<div class="container flex flex-col justify-center items-center w-screen h-screen mx-auto">
    <h1>Create new mail account</h1>
    <Router routes={{
        '/': SignUp
    }} />

<p class="text-xs text-gray-500 mt-3" >
    <button class="rounded bg-blue-500 py-2 px-2 text-white font-bold"  on:click={handleClick}>
        See TOS.
    </button>
</p>
<Modals>
    <div slot="svelte-modal" on:click={closeModal}></div>
</Modals>
</div>