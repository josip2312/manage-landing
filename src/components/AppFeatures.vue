<template>
    <section class="features">
        <div class="container">
            <div class="features-content spacing">
                <h2 class="heading-2">What’s different about Manage?</h2>
                <p class="features-paragraph">
                    Manage provides all the functionality your team needs,
                    without the complexity. Our software is tailor-made for
                    modern digital product teams.
                </p>
            </div>
            <div class="features-items spacing">
                <SingleFeature
                    v-for="feature in features"
                    :key="feature.buttonText"
                    :feature="feature"
                />
            </div>
        </div>
    </section>
</template>

<script>
import { features } from '@/data/features';
import SingleFeature from './SingleFeature';
export default {
    name: 'AppFeatures',
    components: {
        SingleFeature,
    },
    data() {
        return {
            features: features,
        };
    },
};
</script>

<style lang="scss" scoped>
.features {
    background-image: url(../assets/images/bg-tablet-pattern.svg);
    background-origin: border-box;
    background-repeat: no-repeat;
    background-position: -50% 50%;

    @include mq-min($v-12) {
        background-position: -50% -50%;
    }
}
.container {
    display: flex;
    flex-direction: column;
    align-items: center;
    @include mq-min($v-12) {
        flex-direction: row;
        justify-content: space-between;
        align-items: flex-start;
    }
}
.features-content {
    --spacer: 2.5rem;
    padding: 2.5rem 0;
    text-align: center;
    margin-bottom: 5rem;
    @include mq-min($v-12) {
        margin-bottom: 0rem;
        text-align: left;
    }

    .heading-2 {
        max-width: 35rem;
        margin-left: auto;
        margin-right: auto;
        @include mq-min($v-12) {
            margin-left: 0;
        }
    }

    .features-paragraph {
        width: 90%;
        max-width: 45rem;
        margin-left: auto;
        margin-right: auto;

        color: var(--blue-text);
        @include mq-min($v-12) {
            margin-left: 0;
        }
    }
}
.features-items {
    --spacer: 5rem;

    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
