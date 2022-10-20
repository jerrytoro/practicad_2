<template>
    <nav id="app-nav" class="navbar navbar-expand-lg " v-bind:style="menuColor">
        <div class="container-fluid">
            <a class="navbar-brand" href="#">{{marca}}</a>
            <button class="navbar-toggler" type="button" data-bs-toggle="collapse"
                data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false"
                aria-label="Toggle navigation">
                <span class="navbar-toggler-icon"></span>
            </button>
            <div class="collapse navbar-collapse" id="navbarSupportedContent">
                <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                    <li class="nav-item">
                        <a class="nav-link" aria-current="page" :href="menus[1].url">{{menus[0].nombre}}</a>
                    </li>
                    <li class="nav-item">
                        <a class="nav-link" :href="menus[0].url">{{menus[1].nombre}}</a>
                    </li>
                </ul>
            </div>
        </div>
    </nav>
    <productoView></productoView>
    <tarjetaProductos></tarjetaProductos>
    <piePaginaView></piePaginaView>
</template>

<script>
import productoView from '@/views/ProductoView.vue';
import piePaginaView from '@/views/PiePaginaView.vue';
import tarjetaProductos from '@/views/TarjProductView.vue';
export default {
    name: 'menuView',
    data() {
        return {
            marca: "MegaDron",
            menuColor: "background:lightblue",
            precioEstilos: "background: orangered; color: white; font-weight: bold",
            menus: [
                {
                    nombre: "Inicio",
                    url: "#"
                },
                {
                    nombre: "Tienda",
                    url: "#"
                }
            ]
        }
    },
    methods: {
    },
    computed: {
    },
    mounted() {
    },
    components: {
        productoView,
        piePaginaView,
        tarjetaProductos
    }
}
</script>

<style>
.color-box {
    width: 40px;
    height: 40px;
    border-radius: 50%;
    margin: 7px;
    display: inline-block;
}

.clic {
    cursor: pointer;
}

.quantity button {
    border-radius: 50%;
    display: inline-block;
    width: 30px;
}

.quantity div {
    text-align: center;
    min-width: 30px;
    display: inline-block;
    font-weight: bold;
}

.buy-box {
    margin: 20px;
}

.container {
    margin-top: 50px;
}

.producto-relacionado-precio {
    background: orangered;
    color: white;
    text-align: center;
    padding: 10px;
}

.precioEstilos {
    background: orangered;
    color: white;
    font-weight: "bold";
}
</style>