<script setup>
import { SiteText } from '@/constant/index'
</script>

<template>
    <section id="site">
        <div class="site__inner">
            <div class="site__title">
                Site Coding <em>나의 작업물</em>
            </div>
            <div class="site__wrap">
                <div v-for="(site, key) in SiteText" :key="key" :class="'site__item s' + (key + 1)">
                    <span class="num">{{ key + 1 }}</span>
                    <div class="text">
                        <div>{{ site.text[0] }}</div>
                        <div>{{ site.text[1] }}</div>
                        <div>{{ site.text[2] }}</div>
                    </div>
                    <h3 class="title">
                        {{ site.title }}
                    </h3>
                    <div class="btn">
                        <a href="site.code" class="code_btn">code</a>
                        <a href="site.view" class="view_btn">view</a>
                    </div>
                    <div class="info">
                        <span>{{ site.info[0] }}</span>
                        <span>{{ site.info[1] }}</span>
                        <span>{{ site.info[2] }}</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
</template>
<style>
.site__inner {
    padding: 16px;
    display: flex;
    flex-wrap: wrap;
    justify-content: left;
    padding: 0 4.2vw;
    color: var(--mainBg-color);
    font-family: var(--mainKor-font);
}

.site__title {
    position: sticky;
    top: 120px;
    left: 0;
    width: 100%;
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
    z-index: 12000;
}

.site__title em {
    font-family: var(--mainKor-font);
    font-size: 1.25rem;
    font-weight: 200;
    display: inline-block;
    vertical-align: 4px;
    margin-left: 10px;
}

.site__wrap {
    margin: 20px auto;
    width: 100%;
}

.site__item {
    padding: 20px;
    height: 80vh;
    position: relative;
    font-weight: 100;
    position: sticky;
    left: 0;
}

.site__item.s1 {
    background-color: var(--suBg-color100);
    top: 240px;
}

.site__item.s2 {
    background-color: var(--suBg-color200);
    top: 260px;
}

.site__item.s3 {
    background-color: var(--suBg-color300);
    top: 280px;
}

.site__item.s4 {
    background-color: var(--suBg-color400);
    top: 300px;
}

.site__item .num {
    font-size: 4vw;
}

.site__item .text {
    font-size: 3vw;
}

.site__item .title {
    position: absolute;
    right: 0;
    bottom: 0;
    display: flex;
    justify-content: flex-end;
    font-weight: 100;
    font-size: 5vw;
    margin-bottom: 20px;
    padding: 10px;
}

.site__item .btn {
    right: 0;
    top: 0;
    padding: 20px;
    position: absolute;
    display: flex;
    flex-wrap: wrap;
}

.site__item .btn a {
    padding: 5px 30px;
    border: 1px solid var(--mainBg-color);
    color: var(--mainBg-color);
}

.site__item .info {
    padding: 10px 10px;
    position: absolute;
    right: 0;
    bottom: 0;
}

@media (max-width: 800px) {
    .site__title {
        width: 100%;
        margin-bottom: 10vw;
        font-size: 30px;
        height: auto;
        top: 68px;
        z-index: 1000;
        background-color: var(--mainBg-color);
    }

    .site__item.s1 {
        top: 140px;
    }

    .site__item.s2 {
        top: 160px;
    }

    .site__item.s3 {
        top: 180px;
    }

    .site__item.s4 {
        top: 200px;
    }

    .site__item .num {
        font-size: 80px;
        left: 20px;
        top: 20px;
    }

    .site__item .text>div {
        font-size: 26px;
    }

    .site__item .info {
        flex-direction: column;
        width: 90%;
        margin-left: 5%;
        padding: 5px 0;
    }
}
</style>