<script>
    import Button from '../components/Button.svelte'
    import Input from '../components/Input.svelte'

    const API_URL =process.env.API_URL;
    let password= "", user_name = ""

    async function signup() {
        try {
            console.log(API_URL)
            const response = (await fetch(`${API_URL}/user`, {
                method:'POST',
                body: JSON.stringify({"user_name": user_name, "password": password}),
                headers: {
                    "content-type": "application/json"
                }
            })).json();
            console.log('response', response)
        } catch (error) {
            console.error('signup: %s', error)
        }
    }
</script>
<form on:submit|preventDefault={signup} class="lg:w-2/6 md:w-1/2 bg-gray-100 rounded-lg p-8 flex flex-col w-full mt-10 md:mt-0">
    <div class="flex justify-between">
        <h2 class="text-gray-900 text-lg font-medium title-font mb-5">
            Create Email account
        </h2>
    </div>
    <Input label="Email (example@sonofyahweh.foundation)" bind:value={user_name} type="email" required />
    <Input label="Password" bind:value={password} type="password" required />
    <Button on:click="{signup}" >Create account</Button>
</form>
