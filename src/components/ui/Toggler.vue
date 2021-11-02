<template>
    <div class="toggler">
        <div
            class="toggler__one"
            :class="{'active' : isActiveOne}"
            v-on:click="onClickOne"
        >
            {{textOne}}
        </div>
        <div class="toggler__separator"></div>
        <div
            class="toggler__two"
            :class="{'active' : isActiveTwo}"
            v-on:click="onClickTwo"
        >
            {{textTwo}}
        </div>

    </div>
</template>

<script>
    export default {
        name: "Toggler",
        data: () => ({
            isActiveOne: true,
            isActiveTwo: false
        }),
        props: {
            textOne: {
                type: [Number, String],
                require: false
            },
            textTwo: {
                type: [Number, String],
                require: false
            }
        },
        methods: {
            onClickOne () {
                if(this.isActiveOne === false) {
                    this.isActiveOne = !this.isActiveOne
                    this.isActiveTwo = !this.isActiveTwo
                }

                // this.$emit()
            },
            onClickTwo () {
                if(this.isActiveTwo === false) {
                    this.isActiveOne = !this.isActiveOne
                    this.isActiveTwo = !this.isActiveTwo
                }

                // this.$emit()
            },
        }
    }
</script>

