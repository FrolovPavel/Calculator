<template>
    <div class="short-info">
        <p class="short-info__description">{{description}}</p>
        <div class="short-info__value">
            {{value}}
            <span v-if="moneySymbol === false">{{endValue}}</span>
            <span v-if="moneySymbol">&#8381;</span>
        </div>
    </div>
</template>

<script>
    export default {
        name: "ShortInfo",
        props: {
            value: {

            },
            description: {
                type: [Number, String]
            },
            endValue: {
                type: [Number, String],
                require: false
            },
            moneySymbol: {
                type: Boolean,
                default: false
            }
        }
    }
</script>

