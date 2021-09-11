<script>
	import TopNav from './TopNav.svelte'
	import Title from './Title.svelte'

</script>
<main>
    <div class="header">
        <div class="container">
            <TopNav username="Olaoluwa Ojedapo"/>
            <Title title="Dashboard"/>
            <slot></slot>
        </div>
    </div>
</main>