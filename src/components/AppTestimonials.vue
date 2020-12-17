<template>
    <section class="testimonials">
        <h2 class="heading-2">What they’ve said</h2>
        <div class="testimonials-container">
            <SingleTestimonial
                v-for="testimonial in testimonials"
                :key="testimonial.id"
                :testimonial="testimonial"
            />

            <div class="dots">
                <div
                    v-for="(i, index) in testimonials.length"
                    @click="activateTestimonial(index)"
                    :key="index"
                    class="dot"
                    :class="{ active: activeTestimonial === index }"
                ></div>
            </div>
        </div>
    </section>
</template>

<script>
import { testimonials } from '@/data/testimonials';
import SingleTestimonial from './SingleTestimonial';
export default {
    name: 'AppTestimonials',
    components: {
        SingleTestimonial,
    },
    data() {
        return {
            windowWidth: window.innerWidth,
            activeTestimonial: 0,
            testimonials: testimonials,
        };
    },
    computed: {
        isMobile() {
            return this.windowWidth <= 1000;
        },
    },
    mounted() {
        window.addEventListener(
            'resize',
            () => {
                this.windowWidth = window.innerWidth;
            },
            { passive: true },
        );
    },

    methods: {
        activateTestimonial(index) {
            this.activeTestimonial = index;
            this.testimonials.forEach((test) => {
                test.active = false;
            });
            this.testimonials[index].active = true;
        },
    },
};
</script>

<style lang="scss" scoped>
.testimonials {
    padding: 5em 0;
    text-align: center;

    .heading-2 {
        margin-bottom: 10rem;
    }
}
.testimonials-container {
    padding: 0 1rem;
    position: relative;
    min-height: 40vh;
    display: flex;
    flex-direction: column;
    align-items: center;
    @include mq-min($v-12) {
        flex-direction: row;
        align-items: stretch;

        & > * + * {
            margin-left: 5rem;
        }

        & > * {
            opacity: 1;
            transform: scale(1);
        }
    }
}

.dots {
    position: absolute;
    bottom: 5rem;

    display: flex;
    align-items: center;

    @include mq-min($v-12) {
        display: none;
    }
    .dot {
        margin: 0 0.5rem;
        width: 2rem;
        height: 2rem;
        border-radius: 50%;
        background-color: transparent;
        border: 2px solid var(--accent);
        cursor: pointer;
    }
    .dot.active {
        background-color: var(--accent);
    }
}
</style>
