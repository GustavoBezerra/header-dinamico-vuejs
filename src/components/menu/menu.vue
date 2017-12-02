<template>
    <nav class="navbar" :class="getTema">
    <div class="container-fluid">
        <div class="navbar-header">
            <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#bs-example-navbar-collapse-1" aria-expanded="false">
                <span class="sr-only">Toggle navigation</span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
                <span class="icon-bar"></span>
            </button>
            <a href="#" class="navbar-left">
                <img alt="Logo da Duxus" style="width: 50px; height: 50px;" src="../../assets/logo_duxus.png">
            </a>
        </div>

        <div class="collapse navbar-collapse" id="bs-example-navbar-collapse-1">
            <ul class="nav navbar-nav">
                <li :class="menu.submenus ? 'dropdown' : ''" v-for="menu in menus">
                    <a v-if="menu.submenus" href="#" class="dropdown-toggle" :class="getCorTexto" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Dropdown <span class="caret"></span></a>
                    <ul v-if="menu.submenus" class="dropdown-menu">
                        <li v-for="submenu in menu.submenus"><a :href="submenu.url">{{submenu.titulo}}</a></li>                            
                    </ul>
                    <a v-else :href="menu.url" :class="getCorTexto">{{menu.titulo}}</a>
                </li>
            </ul>
            <form class="navbar-form navbar-right">
                <div class="input-group">
                    <input type="text" class="form-control" placeholder="O que você procura?" name="search">
                    <div class="input-group-btn">
                        <button class="btn btn-default" type="submit"><i class="glyphicon glyphicon-search"></i></button>
                    </div>
                </div>
            </form>        
        </div>
    </div>
    </nav>  
</template>

<script>
    export default {

        props: {
            sistema: {
                required: true, 
                type: String
            }
        },

        data() {
            return {
                menus: [
                    {titulo: 'Menu 1', url: 'http://google.com.br'},
                    {titulo: 'Menu 2', url: 'http://globo.com'},
                    {titulo: 'Menu 2', url: 'http://globo.com', submenus: [
                                                    {titulo: 'Submenu 1', url: 'http://google.com.br'},
                                                    {titulo: 'Submenu 2', url: 'http://globo.com'}
                                                ]}
                ]
            }
        },

        computed: {
            getTema() {
                if(this.sistema === 'dominio') return 'bg-primary';
                else if(this.sistema === 'credito') return 'bg-danger';
                else if(this.sistema === 'feeder') return 'bg-info'
            },

            getCorTexto(){
                if(this.sistema === 'dominio') return 'texto-branco';
                else if(this.sistema === 'credito') return 'texto-azul';
                else if(this.sistema === 'feeder') return 'texto-vermelho'
            }
        }
    }
</script>

<style>
    .texto-branco{
        color:white;
    }
    .texto-azul{
        color:blue;
    }
    .texto-vermelho{
        color:red;
    }
</style>


