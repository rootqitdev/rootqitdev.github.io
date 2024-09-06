<script>
    import {Notifications, acts} from '@tadashi/svelte-notification'
    let text = "Bestellen"
    async function handleClick() {
        try {
            const response = await fetch('http://192.168.178.31:30002/Cappucino', {
                method: 'POST',
                redirect: 'follow',
            });

            if (!response.ok) {
                throw new Error('Network response was not ok');
            }

            const data = await response.json();
            console.log('Success:', data);
            text = "Bestellt!"
            acts.add({mode: 'success', message: '✓ Cappucino bestellt!'});
        } catch (error) {
            console.error('Error:', error);
            text = "Bestellt!"
            acts.add({mode: 'success', message: '✓ Cappucino bestellt!'});
        }
    }
</script>

<button on:click={handleClick}>
    <strong>{text}</strong>
</button>

<Notifications />

<svelte:head>
    <style>
        :root {
            --tadashi_svelte_notifications_width: 300px;
        }
    </style>
</svelte:head>
