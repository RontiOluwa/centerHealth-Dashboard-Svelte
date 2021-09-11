<script>
    import Option from './Option.svelte'
    export let date
</script>
<section class="section-top">
    <Option />
    <div class="date-text">
       {date} 
    </div>
    <div class="date-shift">
        <slot></slot>
    </div>
</section>