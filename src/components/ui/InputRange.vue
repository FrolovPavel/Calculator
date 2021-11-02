<template>
    <div class="input-range">
        <div class="input-range__label">
            <label>{{label}}</label>
            <div class="input-range__counter">
                {{value}}
                <span v-if="moneySymbol === false">{{endValue}}</span>
                <span v-if="moneySymbol">&#8381;</span>
            </div>
        </div>
        <VueSlider
            class="input-range__slider"
            ref="slider"
            v-model="value"
            v-bind="options"
            :min="min"
            :max="max"
            @change="onChange"
        />
        <div class="input-range__info">
            <p class="input-range__from">от {{from}}</p>
            <p class="input-range__to">до {{to}}</p>
        </div>
    </div>
</template>

<script>
import VueSlider from 'vue-slider-component'
import 'vue-slider-component/theme/default.css'

    export default {
        name: "InputRange",
        data: () => ({
            value: null,
            options: {
                dotSize: 18,
                width: 'auto',
                height: 5,
                interval: 1,
                tooltip: 'none',
            },

        }),
        props: {
            label: {
                type: [Number, String],
                require: false
            },
            from: {
                type: [Number, String],
                require: false
            },
            to: {
                type: [Number, String],
                require: false
            },
            min: {
                type: [Number],
                require: false
            },
            max: {
                type: [Number],
                require: false
            },
            endValue: {
                type: [Number, String],
                require: false
            },
            moneySymbol: {
                type: Boolean,
                default: false
            },
        },

        components: {
            VueSlider
        },
        methods: {
          onChange () {
              this.$emit('changeSlide', this.value)
          }
        },
        mounted() {
            this.value = this.min
        }
    }
</script>
