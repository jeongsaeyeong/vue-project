<script setup>
import { portText } from '@/constant/index'
</script>

<template>
    <section id="port">
        <div class="port__inner">
            <div class="port__title">
                portfolio <em>포트폴리오 작업물</em>
            </div>
            <div class="port__wrap">
                <div v-for="(port, key) in portText" :key="key" class="port__item p1">
                    <span class="num">{{ port.num }}</span>
                    <a href="#">
                        <img :src="port.img" alt="">
                    </a>
                    <h3 class="title lineA">{{ port.title }}</h3>
                    <p class="desc">
                        {{ port.desc }}
                    </p>
                </div>
            </div>
        </div>
    </section>
</template>

<script>
import gsap from 'gsap';
import ScrollTrigger from 'gsap/ScrollTrigger'
gsap.registerPlugin(ScrollTrigger);

export default {
    mounted: function () {
        this.scrollAnimation();
    },
    methods: {
        scrollAnimation() {
            const horSection = gsap.utils.toArray(".port__item");

            gsap.to(horSection, {
                xPercent: -120 * (horSection.length - 1),
                ease: "none",
                scrollTrigger: {
                    trigger: "#port",
                    start: "top 100px",
                    end: "+=1000",
                    pin: true,
                    scrub: 1,
                    markers: false,
                    invalidateOnRefresh: true,
                    anticipatePin: 1,
                }
            });
        }
    }
}

</script>

<style>
#port {
    width: 100%;
    overflow: hidden;
}

.port__inner {
    padding: 16px 4.2vw;
    font-family: var(--mainKor-font);
}

.port__title {
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

.port__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 200;
    display: inline-block;
    vertical-align: 4px;
    margin-left: 10px;
}

.port__wrap {
    display: flex;
    flex-wrap: wrap;
    width: 7000px;
    overflow: hidden;
}

.port__item {
    width: 500px;
    background-color: #000000;
    margin-right: 25px;
    padding: 5px 20px;
    position: relative;
    color: var(--suBg-color100);
    border: 1px solid var(--suBg-color);
}

.port__item:first-child {
    margin-left: 60px;
}

.port__item .num {
    font-size: 60px;
    font-weight: 100;
}

.port__item a img {
    filter: saturate(0%);
    margin-bottom: 15px;
    transition: all 0.3s;
    border: 1px solid var(--suBg-color);
}

.port__item a img:hover {
    filter: saturate(80%);
}

.port__item .title {
    font-size: 20px;
    text-align: center;
    padding-bottom: 10px;
}

.port__item .desc {
    padding: 20px 5px;
}

.lineA {
    border-bottom: 1px solid var(--suBg-color);
    z-index: 10;
}

.lineB {
    border-bottom: 1px solid var(--mainBg-color);
    z-index: 10;
}

.anothor {
    background-color: #f1f1f1;
    color: var(--mainBg-color);
}
</style>