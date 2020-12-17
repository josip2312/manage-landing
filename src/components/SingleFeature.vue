<template>
    <div class="feature-item spacing-sm">
        <div class="feature-item-heading">
            <button class="btn">{{ feature.buttonText }}</button>
            <h3 class="heading-3">{{ feature.title }}</h3>
        </div>
        <p class="feature-item-paragraph">
            {{ feature.paragraph }}
        </p>
    </div>
</template>

<script>
export default {
    name: 'SingleFeature',
    props: {
        feature: {
            type: Object,
            required: true,
        },
    },
};
</script>

<style lang="scss" scoped>
.feature-item {
    &-heading {
        .btn {
            padding: 0.3em 1.5em;
            margin-right: 2rem;
            transform: translateY(0.25rem);
        }
        display: flex;
        align-items: baseline;
        margin-bottom: 1.5rem;
        @include mq-min($v-12) {
            margin-bottom: 0.5rem;
            margin-left: -9.5rem;
        }
    }

    &-paragraph {
        width: 100%;
        max-width: 50rem;
        color: var(--blue-text);
    }
}
</style>
