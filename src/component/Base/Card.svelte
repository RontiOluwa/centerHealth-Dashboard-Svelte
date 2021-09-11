<script>
    export let title;
    export let figure;
    export let unit;
    export let day;
    export let type;
    console.log(figure)
</script>
<div class="card">
    <div class="card-text">
        {title} 
    </div>
    <div class="card-value">
        <div class="card-data">
            {figure}
            <span class="unit">
                {unit}
            </span>
        </div>
        <div class="card-date">
            Previous day - <span class={type}>{day}</span>
        </div>
    </div>
</div>  