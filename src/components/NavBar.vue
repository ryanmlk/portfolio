<template>
    <div class="navContainer">
        <div class="item">HOME</div>
        <div class="item">ABOUT</div>
        <div class="item">CONTACT</div>
    </div>
</template>

<style scoped>
.navContainer {
    margin-top: 20px;
    position: fixed;
    display: flex;
    justify-content: flex-end;
    flex-direction: row;
    top: 0;
    right: 20px;
    width: 100vw;

    .item {
        font-family: var(--primary-font);
        padding: 10px;
        font-size: 1.2em;
        color: var(--secondary-color);
        cursor: pointer;
        font-weight: 600;
    }
}
</style>