<script>
    export let showModal = false
    export let title
    export let day
    export let time
    let icon = [
		{ name: '1' },
		{ name: '2' },
		{ name: '3' },
		{ name: '4' },
		{ name: '5' },
		{ name: '6' },
	]
</script>
{#if showModal}
    <div class="back-drop" on:click|self>
        <div class="modal">
            <div class="close-modal" on:click|self></div>
            <div class="modal-body">
                <div class="top">
                    <a href="/" class="back-Btn"> </a>
                    <span>{title}</span>
                </div>
                <div class="set-date">
                    <div class="day">{day}</div>
                    <div class="time">{time}</div>
                </div>
                <div class="icons">
                    <ul>
                        {#each icon as list}
                            <li><a href="/">{list.name}</a></li>
                        {/each}
                    </ul>
                </div>
                <button>Submit</button>
            </div>
        </div>
    </div>
{/if}