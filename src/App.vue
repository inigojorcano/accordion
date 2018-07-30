<template>
    <div id="app" class="template">
        <div class="template__container">
            <div class="template__content">
                <h1>Title</h1>
                <Accordion/>
                <Accordion/>
                <Accordion/>
                <Accordion/>
            </div>
        </div>
    </div>
</template>

<script>
import Accordion from './components/Accordion'

export default {
    name: 'App',
    components: {
        Accordion
    }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css?family=Roboto:100,300,400,700');

$color-text: #152935;
$color-white: #fff;
$color-grey: #f1f1f1;

* {
    margin: 0;
    padding: 0;
    list-style: none;
    text-decoration: none;
    border: none;
    outline: none;
}

.template {
    font-family: 'Roboto', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;

    &__container {
        max-width: 712px;
        display: inline-block;
        background: $color-grey;
    }

    &__content {
        margin: 64px 72px 69px 72px;
        padding: 45px 49px 108px 49px;
        background: $color-white;

        h1 {
            font-size: 64px;
            font-weight: 300;
            font-style: normal;
            font-stretch: normal;
            line-height: 1.06;
            letter-spacing: normal;
            text-align: left;
            color: $color-text;
            margin-bottom: 45px;
        }

    }
    
}

</style>
