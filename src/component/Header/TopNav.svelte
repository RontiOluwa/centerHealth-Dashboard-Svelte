<script>
    export let username;
</script>
<div class="nav">
    <ul class="nav-left">
        <li><a href="/" class="active">Dashboard</a></li>
        <li><a href="/">Logbook</a></li>
        <li>
            <a href="/" class="insight">
                Insights
                <span class="insight-tooltiptext tooltiptext">You have unread insights!</span>
            </a>
        </li>
        <li><a href="/" class="team">My Team</a></li>
        <li><a href="/" class="disabled-text">Goals</a></li>
    </ul>
    <ul class="nav-right">
        <li><a href="/" class="messages"> </a></li>
        <li>
            <a href="/" class="setting">
                <img src="https://www.center.health/assets/images/app/misc/default-avatar-small.98d5d23e.png" alt=""/>
                <span class="username">
                    {username}
                </span>
            </a>
        </li>
    </ul>
</div>