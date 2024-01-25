<script lang="ts">
export default {
    props: {
        progressWidth: {
            type: String,
            required: true,
            default: '0%'
        }
    }
}
</script>

<template>
    <div class="skillContainer">
        <slot name="skill" class="skill" />
        <div class="levelBar">
            <div class="progress" :style="{ width: progressWidth }" />
        </div>
    </div>
</template>

<style scope>
.skillContainer {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
    font-size: 24px;

    .skill {
        width: 40%;
        font-family: arial_rounded;
    }

    .levelBar {
        width: 60%;
        background-color: white;
        height: 15px;
        border-radius: 5px;

        .progress {
            background-color: var(--primary-color);
            border-radius: 5px;
            height: 100%;
        }
    }
}

@media(max-width: 1199px) {
    .skillContainer {
        width: 45%;
        font-size: 20px;
    }
}

@media(min-height: 850px) and (min-width: 550px) {
    .skillContainer {
        width: 100%;
        font-size: 20px;
    }
}

@media(max-width: 991px) {
    .skillContainer {
        font-size: 18px;

        .skill {
            width: 45%;
            font-family: arial_rounded;
        }

        .levelBar {
            width: 55%;
            height: 12px;
        }
    }
}

@media(max-width: 767px) {
    .skillContainer {
        width: 100%;
        font-size: 22px;

        .skill {
            width: 40%;
        }

        .levelBar {
            width: 60%;
            height: 15px;
        }
    }
}

@media(max-width: 575px) {
    .skillContainer {
        font-size: 18px;

        .skill {
            width: 45%;
        }

        .levelBar {
            width: 55%;
            height: 12px;
        }
    }
}
</style>