<script lang="ts">
import SkillItem from './SkillItem.vue';

export default {
    components: {
        SkillItem,
    },
    data() {
        return {
            skills: [
                { name: 'ReactJS', progressWidth: '70%' },
                { name: 'VueJS', progressWidth: '30%' },
                { name: 'CSS / SASS', progressWidth: '60%' },
                { name: 'Figma', progressWidth: '70%' },
                { name: 'GIT', progressWidth: '90%' },
                { name: 'AWS', progressWidth: '50%' },
                { name: 'CI/CD', progressWidth: '45%' }
            ],
        };
    },
};
</script>

<template>
    <section id="mainSection">
        <div class="leftSection" id="aboutSection">
            <div class="heading" id="aboutHeading">
                ABOUT ME
                <div class="divider" />
            </div>
            <div class="content" id="aboutContent">
                I'm a software engineer with a passion for understanding how things work. My journey began with robotics and
                evolved into a love for programming, where I've focused on front-end development using React and Next.js. I
                bring a user-centric approach to my projects, ensuring an intuitive user experience. I thrive on finding
                long-term solutions to complex problems and emphasize automated testing to prevent future issues. I've
                played a pivotal role in implementing Scrum methodologies and am an advocate for teamwork.
            </div>
        </div>
        <div class="rightSection" id="skillsSection">
            <div class="heading" id="skillsHeading">
                SKILLS
                <div class="divider" />
            </div>
            <div class="content">
                <SkillItem v-for="skill in skills" :key="skill.name" :progressWidth="skill.progressWidth">
                    <template #skill>
                        {{ skill.name }}
                    </template>
                </SkillItem>
            </div>
        </div>
    </section>
</template>

<style scoped>
section {
    background-color: var(--secondary-color);
    border-radius: 20px 20px 0px 0px;
    display: flex;
    flex-direction: row;
    color: var(--primary-color);
    font-size: 22px;
    font-family: arial_rounded;
    gap: 100px;
    padding-top: 60px;
}

.leftSection {
    flex: 4;

    .content {
        text-align: justify;
    }
}

.rightSection {
    flex: 3;

    .content {
        height: 100%;
        display: flex;
        flex-direction: column;
        gap: 20px;
    }
}

.heading {
    font-family: var(--primary-font);
    font-size: 27px;
    width: fit-content;
    padding-bottom: 30px;

    .divider {
        background-color: var(--primary-color);
        height: 8px;
        width: 40%;
    }
}

@media(max-width: 1199px) {
    section {
        flex-direction: column;
        font-size: 20px;
        gap: 20px;
        overflow: hidden;
    }

    .heading {
        font-size: 24px;
        padding-bottom: 10px;
    }

    .leftSection {
        flex: none;
        height: fit-content;
    }

    .rightSection {
        max-height: calc(50% - 60px);
        flex: none;

        .content {
            flex-wrap: wrap;
            gap: 10px;
            align-items: start;
        }
    }
}

@media(max-width: 991px) {
    section {
        font-size: 18px;
        padding-top: 35px;
    }

    .heading {
        font-size: 22px;
    }
}

@media(max-width: 767px) {
    section {
        height: 200vh;
        height: 200svh;
        font-size: 20px;
        padding: 50px;
    }

    .leftSection,
    .rightSection {
        flex: 1;
    }

    .rightSection {
        .content {
            gap: 20px;
        }
    }

    .heading {
        font-size: 24px;
        padding-bottom: 30px;
    }
}

@media(max-width: 575px) {
    section {
        font-size: 16px;
        padding: 50px 30px;
    }

    .leftSection,
    .rightSection {
        flex: 1;
    }

    .rightSection {
        .content {
            gap: 20px;
        }
    }

    .heading {
        font-size: 22px;
        padding-bottom: 20px;

        .divider {
            height: 7px;
        }
    }
}
</style>