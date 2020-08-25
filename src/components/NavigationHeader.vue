<template>
    <b-navbar toggleable="lg">
        <b-navbar-toggle target="nav-collapse">
            <b-icon icon="grid"></b-icon>
        </b-navbar-toggle>

        <b-navbar-brand class="brandnav" href="#">Room Service</b-navbar-brand>

        <b-collapse id="nav-collapse" is-nav>
            <b-navbar-nav class="navnav" :fill="true">
                <b-nav-item active-class="act" active>Home</b-nav-item>
                <b-nav-item>Registration Form</b-nav-item>
                <b-nav-item>Foods and Drinks</b-nav-item>
                <b-nav-item>Poll</b-nav-item>
                <b-nav-item>Reservation Details</b-nav-item>    
                <b-nav-item-dropdown right>
                    <template v-slot:button-content>
                        <strong>{{  actualLang }}</strong>
                    </template>
                    <b-dropdown-item @click="changeLang('Español')">Español</b-dropdown-item>
                    <b-dropdown-item @click="changeLang('English')">English</b-dropdown-item>
                    <b-dropdown-item @click="changeLang('Portugues')">Portugues</b-dropdown-item>
                </b-nav-item-dropdown>                
            </b-navbar-nav>
        </b-collapse>
    </b-navbar>

    <!--
    <b-nav class="navigationHeader" fill>
        <div class="logoSection vcenter">
            Logo
        </div>
        <b-nav-item active-class="act" active>Home</b-nav-item>
        <b-nav-item>Registration Form</b-nav-item>
        <b-nav-item>Foods and Drinks</b-nav-item>
        <b-nav-item>Poll</b-nav-item>
        <b-nav-item>Reservation Details</b-nav-item>
        <b-nav-item-dropdown
            right>
            <template v-slot:button-content>
                <strong>{{  actualLang }}</strong>
            </template>
            <b-dropdown-item @click="changeLang('Español')">Español</b-dropdown-item>
            <b-dropdown-item @click="changeLang('English')">English</b-dropdown-item>
            <b-dropdown-item @click="changeLang('Portugues')">Portugues</b-dropdown-item>
        </b-nav-item-dropdown>
        <b-nav-item>Close</b-nav-item>
    </b-nav>        
    -->
</template>
<script>
export default {
    name: "NavigationHeader",
    data(){
        return{
            linkAttrs: {
                height: '60px',
                color: 'green',
            },
            actualLang: 'Español'
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

    .navbar-nav
        width: 100%
    .vcenter
        display: flex
        flex-direction: column
        justify-content: center
    .logoSection
        width: 200px
        height: 100%
        text-align: center
    .navigationHeader
        flex-wrap: nowrap !important
        height: 70px
    ul
        height: 100%
        .nav-link
            font-size: 1.2rem
            font-family: 'Roboto', sans-serif
            color: black
            height: 100%
            display: flex
            flex-direction: column
            justify-content: center
            &.active
                border-bottom: 6px solid #827717
                padding-top: 12px
        .dropdown-toggle::after
            border: none

    @media (max-width: 360px)
        ul .nav-link
            color: #fff !important
        .navbar-light .navbar-toggler
            color: #fff !important
            border-color: #fff !important
        .navbar-brand
            color: #fff !important
        .navbar
            position: absolute !important
            width: 100%
            background: linear-gradient(180deg, rgba(0,0,0,1) 0%, rgba(0,0,0,0) 100%)
</style>