<template>
    <header class="header">
        <div class="wrapper container">
            <a class="logo" href="#">
                <img src="@/assets/images/logo.svg" alt="" />
            </a>
            <Navigation :isNavigationVisible="isNavigationVisible" />
            <button
                aria-label="Navigation toggle"
                class="nav-toggle"
                @click="toggleNavigation"
            >
                <img
                    v-if="!isNavigationVisible"
                    key="open"
                    src="@/assets/images/icon-hamburger.svg"
                    alt=""
                />

                <img
                    v-if="isNavigationVisible"
                    key="close"
                    src="@/assets/images/icon-close.svg"
                    alt=""
                />
            </button>
            <button class="btn">Get Started</button>
        </div>
    </header>
</template>

<script>
import { onMounted, ref } from 'vue';

import Navigation from './Navigation';
export default {
    name: 'TheHeader',
    components: {
        Navigation,
    },
    setup() {
        let isNavigationVisible = ref(false);

        const toggleNavigation = () => {
            isNavigationVisible.value = !isNavigationVisible.value;
        };
        onMounted(() => {
            window.addEventListener('scroll', () => {
                const header = document.querySelector('header');
                header.classList.toggle('sticky', window.scrollY > 0);
            });
        });
        return { toggleNavigation, isNavigationVisible };
    },
};
</script>

<style lang="scss" scoped>
header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;

    z-index: 2;
    transition: background-color 350ms ease-in-out;
}
.sticky {
    background-color: var(--white);
}
.wrapper {
    position: relative;
    display: flex;
    padding: 1.75rem 0;
    justify-content: space-between;

    .nav-toggle {
        border: none;
        background: none;

        cursor: pointer;
        img {
            width: 3rem;
        }
        @include mq-min($v-10) {
            display: none;
        }
    }
    .nav-toggle:focus {
        outline: 1px solid var(--blue-400);
    }
    .logo {
        margin-top: 1rem;
        @include mq-min($v-10) {
            margin-top: 0;
            align-self: center;
        }
        img {
            width: 12.5rem;
        }
    }
    .btn {
        display: none;
        align-self: center;
        @include mq-min($v-10) {
            display: block;
        }
    }
}
</style>
