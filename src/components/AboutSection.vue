<template>
    <section>
        <div class="leftSection">
            Test
        </div>
        <div class="rightSection">
            Test Right
        </div>
    </section>
</template>

<style scoped>
    section {
        background-color: var(--secondary-color);
        border-radius: 10px 10px 0px 0px;
        display: flex;
        flex-direction: row;
        color: var(--primary-color);
        font-size: 24px;
        font-family: arial_rounded;
    }

    .leftSection {
        flex: 1;
    }
    .rightSection {
        flex: 1;
    }
</style>