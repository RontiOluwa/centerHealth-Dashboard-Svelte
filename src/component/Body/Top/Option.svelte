<script>
    let list = [
		{ name: 'Now', type:'active' },
		{ name: 'Today' },
		{ name: 'Pass Week' },
		{ name: 'Pass Month' },
		{ name: 'Past 3 Months' },
	]
</script>
<div class="date-options">
    <ul>
        {#each list as option}
            <li class:active-date={option.type}>{option.name}</li>
        {/each}
    </ul>
</div>