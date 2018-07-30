<template>
    <div class="accordion" :class="accordionClasses">
        <div class="accordion__title" @click="toggleAccordion">
            <h2>Label</h2>
        </div>
        <div class="accordion__content">
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Quae eligendi recusandae pariatur quam sit deleniti suscipit nulla optio, dolore cupiditate enim voluptatum. Officia amet tenetur, voluptatibus enim aspernatur itaque laborum.</p>
        </div>
        <hr>
    </div>
</template>

<script>
export default {
    name: 'Accordion',
    data: function() {
        return{
            isOpen: false
        }
    },
    methods: {
        toggleAccordion: function() {
            this.isOpen = !this.isOpen;
        }
    },
    computed: {
        accordionClasses: function() {
            return {
                'accordion--active': this.isOpen
            };
        }
    }
}
</script>

<style lang="scss" scoped>

$color-text-title: #517489;
$color-text-paragraph: #152935;
$color-hr: #dfe3e6;
$color-chevron: #4a90e2;

.accordion {
    max-width: 470px;

    &__title {
        cursor: pointer;
        position: relative;

        h2 {
            font-size: 16px;
            font-weight: bold;
            font-style: normal;
            font-stretch: normal;
            line-height: 1.5;
            letter-spacing: normal;
            text-align: left;
            color: $color-text-title;
            padding: 7px 0 9px 20px; 

            &::before {
                content: '';
                border-right: 2px solid $color-chevron;
                border-top: 2px solid $color-chevron;
                height: 6.5px;
                width: 6.5px;
                display: inline-block;
                position: absolute;
                left: 0;
                top: 14.5px;
                transform: rotate(45deg);
                -ms-transform: rotate(45deg);
                transition: all 0.4s;
            }

        }

    }

    &__content {
        overflow: hidden;
        max-height: 0;
        font-size: 14px;
        font-weight: normal;
        font-style: normal;
        font-stretch: normal;
        line-height: 1.43;
        letter-spacing: normal;
        text-align: left;
        color: $color-text-paragraph;
        transition: max-height 0.5s;

        p {
            padding: 2px 20px 27px 20px; 
        }

    }
    
    hr {
        width: 100%;
        height: 1px;
        background-color: $color-hr;
        border: 0;
    }

    &--active {
        
        .accordion__content {
            max-height: 300px;
            transition: max-height 0.5s;
            transition-delay: 0.2s;
        }

        .accordion__title {
            
            h2 {
                
                &::before {
                    top: 13.5px;
                    transform: rotate(135deg);
                    -ms-transform: rotate(135deg);
                }
            }
        }
    }
}
</style>
