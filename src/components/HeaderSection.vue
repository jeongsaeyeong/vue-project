<script setup>
import { headerNav } from "@/constant/index"
</script>

<template>
    <header id="header" role="banner">
        <div class="header__inner">
            <div class="header__logo">
                <a href="#">PORTFOLIO</a>
            </div>
            <div class="header__nav" role="navigation" aria-label="메인 메뉴" :class="{ show: isNavVisible }">
                <ul>
                    <li v-for="(nav, key) in headerNav" :key="key">
                        <a :href="nav.url" @click="scrolllink($event)">{{ nav.title }}</a>
                    </li>
                </ul>
            </div>
            <div class="header__nav__mobile" id="headerToggle" aria-controls="primary-menu"
                aria-expanded="isNavVisible.toString()" @click="toggleMobileMenu" role="button">
                <span></span>
            </div>
        </div>
    </header>
</template>

<script>
export default {
    data() {
        return {
            isNavVisible: false
        }
    },
    mounted: function () {
        this.scrolllink();
    },
    methods: {
        toggleMobileMenu() {
            this.isNavVisible = !this.isNavVisible;

            const headerToggle = document.getElementById("headerToggle");
            const headerNav = document.querySelector(".header__nav");

            if (headerToggle) {
                headerToggle.addEventListener("click", () => {
                    headerNav.classList.toggle("show");

                    headerToggle.getAttribute("aria-expanded") === "true"
                        ? headerToggle.setAttribute("aria-expanded", false)
                        : headerToggle.setAttribute("aria-expanded", true)

                })
            }
        },

        scrolllink() {
            document.querySelectorAll("a[href^='#']").forEach((anchor) => {
                anchor.addEventListener("click", function (event) {
                    event.preventDefault();

                    const targetId = this.getAttribute("href");
                    const targetElement = document.querySelector(targetId);

                    if (targetElement) {
                        targetElement.scrollIntoView({ behavior: "smooth" });
                    }
                })
            })
        }
    },
}
</script>

<style>
#header {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    z-index: 999999;
    background-color: var(--mainBg-color);
}

.header__inner {
    display: flex;
    align-items: center;
    justify-content: space-between;
    font-family: var(--subEng-font);
    padding: 1.5rem;
    position: relative;
    border-bottom: 1px solid var(--suBg-color);
}

.header__inner ul {
    position: absolute;
    right: 5%;
    top: 50%;
    transform: translateY(-50%);
}

.header__inner ul li {
    font-size: 1.1rem;
    margin-right: 30px;
}

.header__logo {
    display: inline-block;
    flex-wrap: wrap;
    font-size: 30px;
    margin-bottom: 5px;
}

.header__logo a {
    color: var(--suBg-color200);
    margin-left: 1rem;
    transition: all 0.3s;
}

.header__logo a::before {
    content: '';
}

.header__logo a:hover {
    color: var(--suBg-color);
}

.header__nav li {
    color: #fff;
    display: inline;
}

.header__nav li a {
    color: var(--suBg-color);
    position: relative;
}

.header__nav li a::before {
    content: '';
    width: 100%;
    height: 1px;
    background-color: var(--suBg-color);
    position: absolute;
    left: 0;
    bottom: 0;
    transform: scaleX(0);
    transition: all 0.3s;
}

.header__nav li a:hover::before {
    transform: scaleX(1);
}

/* header__nav__mobile */
.header__nav__mobile {
    width: 40px;
    height: 40px;
    cursor: pointer;
    display: none;
}

.header__nav__mobile span {
    display: block;
    width: 40px;
    height: 2px;
    background-color: var(--suBg-color);
    margin-top: 19px;
    position: relative;
}

.header__nav__mobile span::before {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--suBg-color);
    position: absolute;
    right: 0;
    top: 15px;
    transition: width 0.3s;
}

.header__nav__mobile span::after {
    content: '';
    width: 40px;
    height: 2px;
    background-color: var(--suBg-color);
    position: absolute;
    right: 0;
    bottom: 15px;
    transition: width 0.3s;
}

@media (max-width: 1200px) {
    .header__inner ul {
        right: 0;
    }

    .header__nav li a {
        font-size: 16px;
    }

}

@media (max-width: 800px) {
    .header__nav {
        display: none;
    }

    .header__nav.show {
        display: block;
    }

    .header__nav.show ul {
        margin-top: 120px;
        display: flex;
        position: absolute;
        right: 0;
        top: -20px;
        z-index: 10000;
        min-width: 150px;
        padding: 20px 0;
        opacity: 0;
        transition: all 0.5s;
    }

    .header__nav.show ul:hover {
        top: 0px;
        opacity: 1;
    }

    .header__nav.show ul li {
        margin-bottom: 10px;
        display: block;
        text-align: right;
        font-size: 14px;
    }

    .header__nav.show+.header__nav__mobile span::before {
        width: 20px;
    }

    .header__nav.show+.header__nav__mobile span::after {
        width: 20px;
    }


    .header__nav__mobile {
        display: block;
    }

}
</style>