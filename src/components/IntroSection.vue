<template>
    <section id="intro">
        <div class="intro__inner">
            <h1 class="intro__title">
                MAKE NEW WORLD
            </h1>

            <div class="intro__lineAs" aria-hidden="true">
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
            </div>
            <div class="intro__text">
                <div class="intro_img">
                    <div class="profile"></div>
                    <!-- <div class="chessleft"><img src="assets/img/chess02.png" alt=""></div>
                        <div class="chessright"><img src="assets/img/chess03.png" alt=""></div> -->
                </div>
                <div class="text">
                    <div>How can we</div>
                    <div>Create</div>
                    <div>New world?</div>
                </div>
            </div>

            <div class="intro__lineAs bottom" aria-hidden="true">
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
                <span class="lineA"></span>
            </div>
        </div>
    </section>
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,500;0,600;0,700;1,300;1,400;1,500;1,600;1,700&family=DM+Serif+Display:ital@0;1&display=swap');

#intro {
    height: 100vh;
}

.intro__inner {
    font-family: 'Cormorant Garamond';
    width: 100%;
    height: 100%;
    display: flex;
    align-items: flex-start;
    justify-content: flex-end;
    flex-direction: column;
    padding: 70vw 4.2vw;
}

.intro__title {
    font-size: 9.8vw;
    font-weight: 700;
    color: var(--suBg-color);
    line-height: 0.9;
    padding-left: 10px;
}

.intro__lines {
    display: block;
    width: 100%;
}

.intro__lines .line {
    display: block;
    width: 100%;
    height: 1px;
    background-color: var(--suBg-color200);
    margin-bottom: 0.4vw;
}

.intro__lines.bottom {
    display: none;
}

.intro__lines .line:nth-child(1) {
    height: 1px;
}

.intro__lines .line:nth-child(2) {
    height: 1px;
}

.intro__lines .line:nth-child(3) {
    height: 2px;
}

.intro__lines .line:nth-child(4) {
    height: 3px;
}

.intro__lines .line:nth-child(5) {
    height: 4px;
}

/*  */

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

.intro__text {
    background-color: var(--suBg-color100);
    width: 100%;
    /* height: 48vh; */
    padding: 10vw 0;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    position: relative;
}

.intro__text .intro_img .profile {
    /* background-image: url(../../img/profile.png);
    background-position: center;
    background-size: cover; */
    position: absolute;
    padding: 10vw;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 50%;
    background-color: #ccc;
    z-index: 1;
}

.intro__text .intro_img .chessleft {
    position: absolute;
    left: -20px;
    bottom: -20px;
    z-index: 40000;
    width: 35%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}

.intro__text .intro_img .chessright {
    position: absolute;
    right: -20px;
    bottom: -80px;
    z-index: 40000;
    width: 35%;
    background-position: center;
    background-size: cover;
    background-repeat: no-repeat;
}

.intro__text .text {
    font-family: var(--subEng-font);
    font-size: 4vw;
    line-height: 1.2;
    font-weight: 100;
    z-index: 2;
    transition: opacity 0.3s;
}

.intro__text .text:hover {
    opacity: 0;
    cursor: pointer;
}

@media (max-width: 1200px) {
    .intro__inner {
        justify-content: center;
        align-items: center;
    }

    .intro__title {
        font-size: 9.7vw;
        padding-left: 0;
    }
}

@media (max-width: 800px) {
    .intro__inner {
        justify-content: center;
        align-items: center;
    }

    .intro__title {
        font-size: 9.5vw;
        line-height: 1.3;
    }

    .intro__lines.bottom {
        display: block;
    }

    .intro__text .text {
        font-size: 30px;
    }
}
</style>