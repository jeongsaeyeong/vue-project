<script setup>
import { footerText } from '@/constant/index'
</script>

<template>
    <footer id="footer" role="contentinfo">
        <div class="footer__inner">
            <h2 class="footer__text">
                <div>jeongsaeyeong</div>
            </h2>
            <div class="footer__info">
                <div class="left">
                    <div class="title">
                        <a href="#">sign up</a>
                    </div>
                    <p class="desc">회원가입을 하시면 댓글과 게시판 기능을 이용할 수 있습니다.</p>
                </div>
                <div class="right">
                    <h3>social</h3>
                    <ul>
                        <li v-for="(footer, key) in footerText" :key="key">
                            <a href="footer.link">{{ footer.title }}</a>
                            <em>{{ footer.desc }}</em>
                        </li>
                    </ul>
                </div>
            </div>
            <div class="footer__right">
                2023 webstoryboy /
                이 사이트는 비트를 이용하여 제작하였습니다.
            </div>
        </div>
    </footer>
</template>
<style>
.footer__inner {
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    padding: 10vw 4.2vw;
}

.footer__text {
    width: 100%;
    height: 4.9vw;
    font-size: 4vw;
    font-weight: 100;
    line-height: 1.2;
    text-transform: uppercase;
    font-family: var(--subEng-font);
    font-weight: 60;
    color: var(--suBg-color);
    margin-bottom: 20px;
    border-bottom: 1px solid var(--suBg-color);
    z-index: 12000;
}

.footer__info {
    color: #fff;
    display: flex;
    margin-bottom: 30px;
    width: 100%;
}

.footer__info .left {
    width: 40%;
    padding-right: 60px;
}

.footer__info .left .title {
    margin-bottom: 10px;
}

.footer__info .left .title a {
    font-family: var(--subEng-font);
    font-size: 30px;
    color: #fff;
    font-weight: 100;
}

.footer__info .right {
    width: 60%;
}

.footer__info .right h3 {
    font-family: var(--subEng-font);
    font-size: 30px;
    color: #fff;
    font-weight: 100;
}

.footer__info .right ul {
    margin-left: 10px;
    margin-top: 10px;
}

.footer__info .right ul li a {
    display: inline-block;
    font-family: var(--subEng-font);
    font-weight: 100;
    width: 10%;
    color: #fff;
    border-bottom: 1px solid var(--suBg-color300);
    line-height: 2;
}

.footer__info .right ul li em {
    margin-top: 5px;
    font-weight: 100;
    padding-left: 6rem;
    text-align: right;
}

.footer__right {
    width: 100%;
    padding: 10px 0;
    display: inline-block;
    color: var(--suBg-color300);
    text-align: center;
    font-weight: 100;
    font-size: 14px;
    border-top: 1px solid var(--suBg-color);
}
</style>