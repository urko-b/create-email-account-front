<script>
    import Button from '../components/Button.svelte'
    import Input from '../components/Input.svelte'

    let username, password, email

    function signup() {
        
    }
</script>
<form on:submit|preventDefault={signup} class="lg:w-2/6 md:w-1/2 bg-gray-100 rounded-lg p-8 flex flex-col w-full mt-10 md:mt-0">
    <div class="flex justify-between">
        <h2 class="text-gray-900 text-lg font-medium title-font mb-5">
            Create Email account
        </h2>
    </div>
    <Input label="Email (example@sonofyahweh.foundation)" bind:value={email} type="email" required />
    <Input label="Password" bind:value={password} type="password" required />
    <Button>Create account</Button>
</form>
