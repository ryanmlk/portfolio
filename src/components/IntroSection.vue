<script setup lang="ts">
import gsap from 'gsap';
import { Rive } from "@rive-app/canvas";
</script>

<script lang="ts">
export default {
    mounted: function () {
        new Rive({
            src: "/images/dev.riv",
            canvas: document.getElementById("hero") as HTMLCanvasElement,
            autoplay: true,
        })

        gsap.to(".hero", {
            alpha: 1,
            delay: 1,
            duration: 1,
        });
    },
    methods: {
        // where the animation will start from
        beforeEnter(el: any) {
            el.style.opacity = '0'
            el.style.transform = 'translateY(-100px)'
        },
        // where the animation will end up
        enter(el: any) {
            gsap.to(el, {
                duration: 1,
                y: 0,
                opacity: 1,
            })
        }
    }
}
</script>

<template>
    <section class="root">
        <transition appear @before-enter="beforeEnter" @enter="enter">
            <div class="leftSection">
                <h2>HI I'M</h2>
                <h1>RYAN</h1>
                <p>Full-stack software engineer with a passion for learning and creating elegant software solutions</p>
            </div>
        </transition>
        <div class="rightSection">
            <canvas className="hero" id="hero" width="600" height="600" />
        </div>
    </section>
</template>


<style scoped>
.root {
    width: 100%;
    height: 100vh;
    height: 100svh;
    display: flex;
    flex-direction: row;
    align-items: center;
    color: var(--secondary-color);

    .leftSection {
        flex: 1;

        h1 {
            font-weight: 500;
            margin-left: -8px;
            line-height: 95px;
            font-family: var(--primary-font);
            font-size: 6rem;
        }

        h2 {
            font-weight: 500;
            font-family: var(--primary-font);
            font-size: 1.6rem;
        }

        p {
            font-weight: 500;
            margin-top: 22px;
            font-family: var(--secondary-font);
            font-size: 1.5rem;
            width: 90%;
            line-height: 30px;
        }
    }

    .rightSection {
        flex: 1;
        display: flex;
        align-items: center;
        justify-content: center;

        .hero {
            opacity: 0;
            max-width: 100%;
            max-height: 100%;
        }
    }
}

@media(max-width: 991px) {
    .root {
        flex-direction: column;

        .leftSection {
            h1 {
                font-size: 5rem;
                line-height: 80px;
            }

            h2 {
                font-size: 1.2rem;
            }

            p {
                font-size: 1rem;
                line-height: 20px;
                margin-top: 12px;
            }
        }

        .rightSection {
            height: 60%;
            margin-top: 40px;
        }
    }
}

@media(max-width: 767px) {}

@media(max-width: 575px) {
    .root {

        .leftSection {
            flex: 1;

            h1 {
                font-size: 3rem;
                line-height: 50px;
                margin-left: -5px;
            }

            h2 {
                font-size: 0.8rem;
            }

            p {
                font-size: 0.8rem;
                line-height: 18px;
                margin-top: 10px;
            }
        }

        .rightSection {
            align-items: flex-start;
            flex: 2;
            margin-top: 0px;
        }
    }
}
</style>