<template>
    <div class="itemBox">
        <div class="imgbox">
            <b-img :src="item.image" fluid-grow block></b-img>
        </div>
        <div class="contentbox">
            <div class="descriptionbox">
                <div class="textbox">
                    <span class="title detailItem">
                        {{item.title}}
                    </span>
                    <span class="text">
                        {{item.description}}
                    </span>
                </div>
                <div class="detailsbox">
                    <div class="pricebox center">
                        <div class="titleSelection center">
                            <span>Precio</span>
                        </div>
                        <span class="detailItem greenText">
                            {{item.price}} $
                        </span>                    
                    </div>
                    <div class="selectionbox f-vertical">
                        <div class="titleSelection center">
                            <span>Cantidad</span>
                        </div>
                        <div class="buttonsQuantitySelection center">
                            <div class="icon detailItem">
                                <b-icon-dash-circle></b-icon-dash-circle>
                            </div>
                            <span class="detailItem">{{ item.quantity }}</span>
                            <div class="icon detailItem">
                                <b-icon-plus-circle></b-icon-plus-circle>
                            </div>
                        </div>
                    </div>
                    <div class="totalbox center">
                        <div class="titleSelection center">
                            <span>Precio</span>
                        </div>
                        <span class="detailItem greenText">
                            30 $
                        </span>                    
                    </div>
                </div>
            </div>
            <div class="actionbox">
                <b-button variant="dark" class="btn-item" size="sm">Anadir comentario</b-button>
                <b-button class="buy-btn btn-item" size="sm">Comprar</b-button>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    name:"ItemElement",
    props:{
        item: {
            required: true
        }
    },
    data(){
        return{

        }
    }
}
</script>
<style lang="sass">
    $colorgreen: #827717
    .greenText
        color: $colorgreen
    .btn-item
        padding: 0.2rem 1.3rem !important
    .buy-btn
        background-color: $colorgreen !important
        border-color: $colorgreen !important
    .titleSelection
        font-size: 10px
    .detailItem
        font-size: 22px
    .center
        text-align: center
    .f-vertical
        display: flex
        flex-direction: column
    .f-horizontal
        display: flex
        flex-direction: row
    .actionbox
        display: flex
        flex-direction: row
        justify-content: space-around
        padding: 15px 0
    .descriptionbox
        display: flex
    .itemBox
        background-color: #fff
        width: 100%
        box-shadow: 5px 5px 5px 5px rgba(0,0,0,.15)
        // border: 1px solid green
        display: flex
        flex-direction: row
        margin-bottom: 40px
        .imgbox
            width: 40%
        .contentbox
            width: 60%
            display: flex
            flex-direction: column
            justify-content: space-around
            display: flex
                flex-direction: row
            .textbox
                padding: 0 15px
                display: flex
                flex-direction: column
                font-size: 12px
                width: 70%
                .title
                    margin-bottom: 5px
                .text
                    text-align: justify
            .detailsbox
                width: 30%
                display: flex
                flex-direction: column
        .detailsbox
            justify-content: space-evenly
            .selectionbox
            .buttonsQuantitySelection
                display: flex
                flex-direction: row
                text-align: center
                margin: auto
                .icon
                    margin: 0 5px
                    color: $colorgreen
    
    @media (max-width: 360px)
        .descriptionbox
            flex-direction: column
        .itemBox
            flex-direction: column
            .imgbox
                width: 100%            
            .contentbox
                width: 100%
                .textbox
                    margin-top: 10px
                    width: 100%
                .detailsbox
                    width: 100%
            .detailsbox
                margin-top: 15px
                margin-bottom: 15px
                flex-direction: row !important
                .buttonsQuantitySelection
                    flex-direction: row

</style>