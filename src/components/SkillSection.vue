<script setup>
import { skillText } from '@/constant/index'
</script>

<template>
    <section id="skill">
        <div class="skill__inner">
            <h2 class="skill__title">
                GROWTH<em>나의 성장</em>
            </h2>
            <div class="skill__desc">
                <div v-for="(skill, key) in skillText" :key="key">
                    <span>{{ key + 1 }}.</span>
                    <h3>{{ skill.title }}</h3>
                    <p>{{ skill.desc }}</p>
                </div>
            </div>
        </div>
    </section>
</template>
<style>
.skill__inner {
    padding: 16px;
    display: flex;
    justify-content: space-between;
    padding: 30vw 4.2vw 0vw;
}

.skill__title {
    position: sticky;
    top: 120px;
    left: 0;
    width: 48%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 100;
    line-height: 1.2;
    text-transform: uppercase;
    font-family: var(--subEng-font);
    font-weight: 60;
    color: var(--suBg-color);
    margin-bottom: 10px;
    border-bottom: 1px solid var(--suBg-color);
}

.skill__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 200;
    display: inline-block;
    vertical-align: 4px;
    margin-left: 10px;
}

.skill__desc {
    width: 50%;
}

.skill__desc span {
    font-size: 5vw;
    line-height: 1.5;
    font-weight: 100;
    font-family: var(--mainKor-font);
    color: var(--suBg-color);
}

.skill__desc h3 {
    font-size: 1.5rem;
    text-decoration: underline;
    text-underline-position: under;
    margin-bottom: 1vw;
    color: var(--suBg-color);
}

.skill__desc p {
    margin-bottom: 30vh;
    font-size: 1.1rem;
    font-family: var(--mainKor-font);
    color: var(--suBg-color);
}


@media (max-width: 800px) {
    .skill__inner {
        flex-direction: column;
    }

    .skill__title {
        font-size: 3.5rem;
        width: 100%;
        margin-bottom: 10vw;
        height: auto;
        background-color: var(--mainBg-color);
    }

    .skill__desc span {
        font-size: 10vw;
    }

    .skill__desc {
        font-weight: 100;
        width: 100%;
    }

    .skill__desc p {
        margin-bottom: 15vh;
    }
}
</style>