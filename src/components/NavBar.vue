<template>
    <div class="navContainer">
        <div class="item">HOME</div>
        <div class="item">ABOUT</div>
        <div class="item">CONTACT</div>
    </div>
</template>

<style scoped>
.navContainer {
    z-index: 2;
    height: 60px;
    position: fixed;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    flex-direction: row;
    top: 0;
    right: 20px;
    width: 100vw;

    .item {
        font-family: var(--primary-font);
        padding: 10px;
        font-size: 1.2rem;
        color: var(--secondary-color);
        cursor: pointer;
        font-weight: 600;
    }
}

@media(max-width: 767px) {
    .navContainer {
        .item {
            font-size: 0.8rem;
            padding: 8px;
        }
    }
}

@media(max-width: 575px) {
    .navContainer {
        .item {
            font-size: 0.5rem;
            padding: 4px;
        }
    }
}
</style>