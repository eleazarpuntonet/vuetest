<template>
    <b-container class="mainContainer" fluid>
        <navigation-header>
        </navigation-header>
        <div class="headerTitleImage">
        </div>
        <div class="titleHeader">
            <div class="textTitle">
                <h1>REALIZA TU PEDIDO</h1>
            </div>
            <div class="actionButtons">
                <div class="buttons">
                    <b-button class="btn-action-secondary btn-action">Ver detalle pedido</b-button>
                    <b-button class="btn-action-primary btn-action">Ver detalle pedido</b-button>
                </div>
            </div>
        </div>
        <b-container>

        <b-row class="itemsContainer">
            <b-col md="6" sm="12" v-for="item in items" :key="item.id">
                <item-component :item="item">
                </item-component>
            </b-col>
        </b-row>
        </b-container>
    </b-container>
</template>
<script>
import { productItems } from "../assets/constants"
import NavigationHeader from "./NavigationHeader"
import ItemComponent from "./ItemComponent"
export default {
    components:{
        ItemComponent,
        NavigationHeader
    },
    data(){
        return{
            linkAttrs: {
                height: '60px',
                color: 'green',
            },
            actualLang: 'Español',
            items: productItems
        }
    },
    methods:{
        changeLang(lang){
            this.actualLang = lang
        }
    }
}
</script>
<style lang="sass">
body
    background-color: #FAFAFA !important
    // background-color: red !important
.itemsContainer
    background-color: #FAFAFA
.mainContainer
    padding: 0px !important
    // background-color: red !important
.btn-action
    border-radius: 0px !important
    padding: 0.6rem 0.9rem !important
.btn-action-secondary
    background-color: #E0E0E0 !important
    border-color: #E0E0E0 !important
    color: black !important
.btn-action-primary
    background-color: #827717 !important
    border-color: #827717 !important
    color: #fff !important
.titleHeader
    padding: 20px
    background-color: #fff
    margin-top: -100px
    margin-bottom: 100px
    margin-left: auto
    margin-right: auto
    width: 600px
    display: flex
    flex-direction: row
    .textTitle
        margin: 0 15px
        h1
            font-size: 1.4rem
            letter-spacing: 4px
        text-align: center
        width: 40%
        display: flex
        flex-direction: column
        justify-content: center
    .actionButtons
        display: flex
        flex-direction: column
        justify-content: center
        width: 100%
        .buttons
            width: 100%
            display: flex
            justify-content: space-around
            flex-direction: row
.headerTitleImage
    height: 250px
    width: 100%
    // background-color: red
    background-image: url("../assets/img/imgback.jpg")
    background-position: center
    background-size: cover
    background-repeat: no-repeat


@media (max-width: 360px)
    .mainContainer
        padding: 5px !important
    .headerTitleImage
        height: 200px
    .btn-action
        border-radius: 0px !important
        padding: 0.1rem 0.3rem !important
        font-size: 12px !important
    .titleHeader
        margin-top: -20px
        margin-bottom: 20px
        // display: none
        flex-direction: column
        padding: 10px
        width: 90%
        .textTitle
            display: none


// @media (max-width: 480px)
// @media (max-width: 768px)
// @media (max-width: 1024px)

</style>