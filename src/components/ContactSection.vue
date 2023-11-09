<script setup>
import { contactText } from '@/constant/index'
</script>

<template>
    <section id="contact">
        <div class="contact__inner">
            <h2 class="contact__title">Contact <em>연락처</em></h2>
            <div class="contact__text">

                <div class="contact__line" aria-hidden="true">
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                </div>

                <div class="text">
                    <div v-for="(cont, key) in contactText" :key="key">
                        <a href="cont.link">{{ cont.title }}</a><br>
                    </div>
                </div>

                <div class="contact__line" aria-hidden="true">
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                    <span class="line"></span>
                </div>

            </div>
        </div>
    </section>
</template>
<style>
#contact {
    height: 100vh;
}

.contact__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    padding: 0vw 4.2vw;
}

.contact__title {
    width: 100%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 100;
    line-height: 1.2;
    text-transform: uppercase;
    font-family: var(--subEng-font);
    font-weight: 60;
    color: var(--suBg-color);
    margin-bottom: 30px;
    border-bottom: 1px solid var(--suBg-color);
    z-index: 12000;
}

.contact__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 200;
    display: inline-block;
    vertical-align: 4px;
    margin-left: 10px;
}

.contact__text {
    width: 100%;
}


.contact__line {
    display: block;
    width: 100%;
}


.contact__line .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--suBg-color200);
    margin-bottom: 0.4vw;
}

.contact__line.bottom {
    display: none;
}

.contact__line .line:nth-child(1) {
    height: 1px;
}

.contact__line .line:nth-child(2) {
    height: 1px;
}

.contact__line .line:nth-child(3) {
    height: 2px;
}

.contact__line .line:nth-child(4) {
    height: 3px;
}

.contact__line .line:nth-child(5) {
    height: 4px;
}

.intro__lines.bottom .line:nth-child(5) {
    height: 4px;
}

.intro__lines.bottom .line:nth-child(4) {
    height: 3px;
}

.intro__lines.bottom .line:nth-child(3) {
    height: 1px;
}

.intro__lines.bottom .line:nth-child(2) {
    height: 1px;
}

.intro__lines.bottom .line:nth-child(1) {
    height: 1px;
}

.contact__text {
    display: flex;
    flex-wrap: wrap;
    width: 100%;
}

.contact__text .text {
    text-align: center;
    background-color: var(--suBg-color);
    width: 100%;
    padding: 10vw 0;
    font-size: 1.5rem;
}
</style>