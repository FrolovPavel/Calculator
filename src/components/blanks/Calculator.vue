<template>
    <div class="calculator">
        <h1 class="calculator__title">Калькулятор займа под ПТС</h1>
        <div class="calculator__wrapper">
            <div class="calculator__action">
                <div class="calculator__nav">
                    <h2 class="calculator__subtitle">
                        Тип платежа
                    </h2>
                    <Toggler
                            textOne="Дифференцированный"
                            textTwo="Аннуитетный"
                    />
                </div>

                <InputRange
                        label="Сумма займа"
                        :min="15000"
                        :max="1000000"
                        from="15 000"
                        to="1 000 000"
                        :moneySymbol="true"
                        @changeSlide="setCalculatorPayment"
                />
                <InputRange
                        label="Срок займа"
                        :min="2"
                        :max="12"
                        from="2 месяцев"
                        to="12 месяцев"
                        endValue="месяцев"
                />
                <div class="calculator__action-footer">
                    Условия выдачи займа могут отличаться, сиходя из анализа
                    документов и состояния вашего автомобиля
                </div>
            </div>
            <div class="calculator__info">
                <div class="calculator__info-wrapper">
                    <ShortInfo
                            description="Ставка"
                            class="calculator__rate"
                            :value="calculatorRate"
                            endValue="%"
                    />
                    <ShortInfo
                            description="Ежемесячный платеж"
                            class="calculator__payment"
                            :value="calculatorPayment"
                            :moneySymbol="true"
                    />
                </div>
                <Button
                    class="calculator__button"
                    text="Подать заявку"
                />
                <div class="calculator__info-footer">
                    Расчет займа предварительный
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import Button from "../ui/Button";
import Toggler from '../ui/Toggler'
import InputRange from "../ui/InputRange";
import ShortInfo from "./ShortInfo";

    export default {
        name: "Calculator",
        data: () => ({
            calculatorRate: 2.7,
            calculatorPayment: null
        }),
        components: {
            Button,
            Toggler,
            InputRange,
            ShortInfo
        },
        methods: {
            setCalculatorPayment (valueInput) {
                this.calculatorPayment = Math.round(valueInput * this.calculatorRate / 100)
            }
        },
        mounted() {
            this.calculatorPayment = Math.round(15000 * this.calculatorRate / 100)
        }
    }
</script>
