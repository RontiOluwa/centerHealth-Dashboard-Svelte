<script>
    import Top from './Top/Top.svelte'
    import Card from '../Base/Card.svelte'
    import moment from 'moment';

    // Array containing List of cards
    const DEMO_EVENTS = [
        { value: 100, time: moment().format('LL'), day:'3', type:'success', unit:'events', title:'Total blood suger event' },
        { value: 155, time: moment().format('LL'), day:'150', type:'warning', unit:'mg/dL',  title:'Total blood suger' },
        { value: 83, time: moment().format('LL'), day:'80', type:'success',  unit:'%', title:'Event between 70 and 180' },
        { value: 211, time: moment().subtract(1, 'day').format('LL'), day:'3', type:'success', unit:'events', title:'Total blood suger event' },
        { value: 138, time: moment().subtract(1, 'day').format('LL'), day:'150', type:'warning', unit:'mg/dL',  title:'Total blood suger' },
        { value: 55, time: moment().subtract(1, 'day').format('LL'), day:'80', type:'success', unit:'%', title:'Event between 70 and 180' },
        { value: 183, time: moment().subtract(2, 'day').format('LL'), day:'3', type:'warning', unit:'events', title:'Total blood suger event' },
        { value: 103, time: moment().subtract(2, 'day').format('LL'), day:'150', type:'success', unit:'mg/dL',  title:'Total blood suger' },
        { value: 98, time: moment().subtract(3, 'day').format('LL'), day:'80', type:'warning', unit:'%', title:'Event between 70 and 180' }
    ];

    // Getting Todays Date in September 9, 2021 format
    let activeDate = moment().format('LL')
    const previousDate = () => {
        let count = 0;
        // Looping through the Card List Array
        DEMO_EVENTS.forEach(function (Item) {
            // Checking if array contains data for the previous day
            if(moment(activeDate).subtract(1, 'day').format('LL') === Item.time) {
                count ++;
            }
        });
        if(count > 0) {
            // Changing date value if array contain data for the previous day
            activeDate = moment(activeDate).subtract(1, 'day').format('LL')
        }
	}
    const nextDate = () => {
        let count = 0;
        // Looping through the Card List Array
        DEMO_EVENTS.forEach(function (Item) {
            // Checking if array contains data for the next day
            if(moment(activeDate).add(1, 'day').format('LL') === Item.time) {
                count ++;
            }
        });
        if(count > 0) {
             // Changing date value if array contain data for the next day
            activeDate = moment(activeDate).add(1, 'day').format('LL')
        }
	}
</script>
<div class="main-container">
    <div class="section">
        <Top date={activeDate}>
            <span class="previous" on:click={previousDate}> </span>
            <span class="next" on:click={nextDate}> </span>
        </Top>
    </div>
    <div class="card-section">
        {#each DEMO_EVENTS as event}
            {#if event.time === activeDate}
                <Card title={event.title} figure={event.value} unit={event.unit} day={event.day} type={event.type} />
            {/if}
        {/each}
    </div>
</div>