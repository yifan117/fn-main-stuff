<script lang='ts'>

    import Account from "svelte-material-icons/AccountCircle.svelte"
    import Complete from "svelte-material-icons/CheckboxMarkedCircle.svelte"
    import Incomplete from "svelte-material-icons/CheckboxBlankCircleOutline.svelte"
    import Search from "svelte-material-icons/Magnify.svelte"
    import Plus from "svelte-material-icons/Plus.svelte"
    import ChevronDown from "svelte-material-icons/ChevronDown.svelte"
    import Cog from "svelte-material-icons/Cog.svelte"
    import Sun from "svelte-material-icons/WhiteBalanceSunny.svelte"
    import Moon from "svelte-material-icons/MoonWaxingCrescent.svelte"

    var today = new Date();
    var dd = String(today.getDate()).padStart(2, '0');
    var ddT = String(today.getDate() + 1).padStart(2, '0');
    var mm = String(today.getMonth() + 1).padStart(2, '0');
    var yyyy = String(today.getFullYear());

    let listContents = [
        { task: 'Design Website' },
        { task: 'Design Website' },
        { task: 'Design Website' }
    ];

</script>

<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Prompt">

<div class="page">
    <div class="nav-bar">
        <div class="icons">
            <div class="Account">
                <Account size="36px"/>
            </div>

            <div class="Sun">
                <Sun size="36px"/>
            </div>

            <div class="Cog">
                <Cog size="36px"/>
            </div>        </div>

        <div class="date-search">
            <div class="date">
                <p>Today</p>
                <p class="dateP">{dd}/{mm}/{yyyy}</p> 

                <div class="chevron-icon">
                    <ChevronDown size="20px"/>
                </div>
            </div>

            <div class="search-icon">
                <Search size="36px"/>
            </div>
        </div>
    </div>

    <div class="body-container">
        <div class="list-container">
            <div class="list">
                <div class="date">
                    <p>Today</p>
                    <p class="dateP">{dd}/{mm}/{yyyy}</p>

                    <div class="chevron-icon">
                        <ChevronDown size="20px"/>
                    </div>
                </div>

                <div class="content">
                    {#each listContents as listContent}
                    <div class="list-object-container">
                        <Incomplete size="24px"/>

                        <div class="list-object">
                            {listContent.task}
                        </div>

                        <Plus size="34px"/>
                    </div>
                    {/each}

                    <div class="spec-list-object-container">
                        <div class="specc-list-object-container">
                            <Incomplete size="24px"/>

                            <div class="list-object">
                                Design Website
                            </div>

                            <Plus size="34px"/>
                        </div>

                            <div class="spec-sub-container">

                                <div class="spec-sub-list-object-container">
                                    <Complete size="24px"/>
            
                                    <div class="spec-sub-list-object">
                                        Design Header
                                    </div>
                                </div>

                                {#each listContents as listContent}
                                <div class="spec-sub-list-object-container">
                                    <Incomplete size="24px"/>
            
                                    <div class="spec-sub-list-object">
                                        {listContent.task}
                                    </div>
                                </div>
                                {/each}
                            </div>
                    </div>
                </div>

                <button class="add">
                    <Plus size="20px"/>
                    Add Task
                </button>
            </div>

            <div class="list">
                <div class="date">
                    <p>Tomorrow</p>
                    <p class="dateP">{ddT}/{mm}/{yyyy}</p>

                    <div class="chevron-icon">
                        <ChevronDown size="20px"/>
                    </div>
                </div>

                <div class="content">
                    {#each listContents as listContent}
                    <div class="list-object-container">
                        <Incomplete size="24px"/>

                        <div class="list-object">
                            {listContent.task}
                        </div>

                        <Plus size="34px"/>
                    </div>
                    {/each}

                    <div class="spec-list-object-container">
                        <div class="specc-list-object-container">
                            <Incomplete size="24px"/>

                            <div class="list-object">
                                Design Website
                            </div>

                            <Plus size="34px"/>
                        </div>

                            <div class="spec-sub-container">
                                {#each listContents as listContent}
                                <div class="spec-sub-list-object-container">
                                    <Incomplete size="24px"/>
            
                                    <div class="spec-sub-list-object">
                                        {listContent.task}
                                    </div>
                                </div>
                                {/each}

                                <div class="spec-sub-list-object-container">
                                    <Complete size="24px"/>
            
                                    <div class="spec-sub-list-object">
                                        Design Header
                                    </div>
                                </div>
                            </div>
                    </div>
                </div>

                <button class="add">
                    <Plus size="20px"/>
                    Add Task
                </button>
            </div>
        </div>
    </div>
</div>

<style>

* {
    font-family: 'Prompt';
    color: #C2C2D7;
}

.body-container {
    display: flex;
    padding: 40px;
}

.page {
    background: #1B1C32;
    height: 100vh;
    gap: 32px;
}

.nav-bar {
    background: rgba(255, 255, 255, 0.04);
    display: flex;
    align-items: center;
    justify-content: space-between;
    padding: 12px 32px;
    gap: 50px;
}

.icons {
    display: flex;
    color: #C2C2D7;
    gap: 50px;
}

.date-search {
    display: flex;
    align-items: center;
    width: 100%;
    justify-content: space-between;
}

.Account:hover, .Sun:hover, .Cog:hover, .search-icon:hover, .chevron-icon:hover {
    opacity: 30%;
    cursor: pointer;
}

p {
    display: flex;
    font-style: normal;
    font-weight: 600;
    font-size: 24px;
    margin: 0px;
}

.dateP {
    display: flex;
    height: fit-content;
    opacity: 30%;
}

.date {
    display: flex;
    align-items: center;
    gap: 10px;
    padding: 6px 10px;
}

.chevron-icon {
    display: flex;
}

.list-container {
    width: 100vw;
    display: flex;
    height: 100%;
}

.list {
    display: flex;
    width: 100%;
    height: 80%;
    flex-direction: column;
    align-items: center;
    padding: 30px;
    gap: 10px;
    justify-content: space-around;
}

button {
    border: 2px solid #C2C2D7;
    background: rgba(255, 255, 255, 0.09);
    gap: 10px;
    padding: 5px 20px;
    cursor: pointer;
    border-radius: 11px;
    display: flex;
    align-items: center;
    text-align: center;
    align-self: center;
    align-content: center;
    justify-content: center;
}

.list-object-container {
    border-left: 2px solid #C2C2D7;
    display: flex;
    padding: 0px 12px;
    gap: 9px;
    align-items: center;
    justify-content: center;
    width: 90%;
}

.spec-list-object-container {
    border-left: 2px solid #C2C2D7;
    display: flex;
    flex-direction: column;
    padding: 0px 12px;
    gap: 9px;
    align-items: center;
    justify-content: center;
    width: 90%;
}

.list-object {
    justify-content: center;
}

.specc-list-object-container {
    display: flex;
    padding: 0px 12px;
    gap: 9px;
    align-items: center;
    justify-content: center;
    width: 100%;
}

.content {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    gap: 10px;
}
.list-object {
    border: 2px solid #C2C2D7;
    border-radius: 9px;
    display: flex;
    gap: 10px;
    padding: 0px 10px;
    width: 100%;
}

.body-container {
    height: 90%;
}

.sub-container {
    width: 93%;
}

.sub-list-object-container {
    border-left: 2px solid #C2C2D7;
    display: flex;
    padding: 0px 12px;
    gap: 9px;
    align-items: center;
    justify-content: center;
    width: 90%;
}

.sub-list-object {
    border: 2px solid #C2C2D7;
    border-radius: 9px;
    display: flex;
    gap: 10px;
    padding: 0px 10px;
    width: 100%;
}

.spec-sub-container {
    width: 93%;
    display: flex;
    flex-direction: column;
    align-items: flex-end;
    gap: 9px;
}

.spec-sub-list-object-container {
    display: flex;
    padding: 0px 12px;
    gap: 9px;
    align-items: center;
    width: 90%;
}

.spec-sub-list-object {
    border: 2px solid #C2C2D7;
    border-radius: 9px;
    display: flex;
    gap: 10px;
    justify-content: center;
    padding: 0px 10px;
    width: 100%;
}
</style>