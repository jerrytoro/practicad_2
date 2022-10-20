<template>
    <div class="container">

        <div class="row">
            <h3>{{producto.nombre}}</h3>
        </div>
        <div class="row">
            <div class="col-12 col-sm-6 col-md-4 ">
                <img :src="producto.imagen">
            </div>
            <div class="col-12 col-sm-6  col-md-8">
                <h6>{{producto.descripcion}}</h6>
                <div class="p-3 mb-2 text-white" :style="precioEstilos">
                    {{producto.precio}} BOB
                </div>
                <h5>Color</h5>
                <div>
                    <button @click="alertacolor(pedido.color=producto.colores[0],pedido.id=producto.id)"
                        class="color-box clic" :style="{background:producto.colores[0]}"></button>
                    <button @click="alertacolor(pedido.color=producto.colores[1],pedido.id=producto.id)"
                        class="color-box clic" :style="{background:producto.colores[1]}"></button>
                    <button @click="alertacolor(pedido.color=producto.colores[2],pedido.id=producto.id)"
                        class="color-box clic" :style="{background:producto.colores[2]}"></button>
                    <button @click="alertacolor(pedido.color=producto.colores[3],pedido.id=producto.id)"
                        class="color-box clic" :style="{background:producto.colores[3]}"></button>

                </div>
                <h5>Cantidad</h5>
                <div class="quantity">
                    <button v-if="pedido.cantidad>1" v-on:click="pedido.cantidad -=1">-</button>
                    <button v-if="pedido.cantidad==1" v-on:click="pedido.cantidad -=1" disabled="true">-</button>
                    <div>{{pedido.cantidad}}</div> <button v-on:click="pedido.cantidad +=1">+</button>
                </div>
                <div>

                </div>
                <div class="buy-box">
                    <button v-if="producto.count>=1" type="button" class="btn btn-primary"
                        @click="alerta(pedido)">Comprar</button>
                </div>

            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'productoView',
    data() {
        return {
            precioEstilos: "background: orangered; color: white; font-weight: bold",
            producto: {
                id: 1,
                imagen: "https://ae01.alicdn.com/kf/Sc3cc58f2a441419f970cc01f9e5358fbw/Dron-LU3-MAX-GPS-8K-HD-profesional-con-c-mara-Dual-card-n-autoestabilizador-Motor-sin.jpg_Q90.jpg_.webp",
                nombre: "Dron LU3 MAX GPS 8K HD",
                descripcion: "Dron LU3 MAX GPS 8K HD profesional con <b>cámara Dual</b>,cardán autoestabilizador, Motor sin escobillas para evitar obstáculos, cuadricóptero plegable",
                precio: 620,
                colores: ["red", "blue", "black", "yellow"],
                count: 1,
            },
            pedido: {
                id: null,
                cantidad: 1,
                color: null
            }
        }
    },
    methods: {
        alerta: function (pedido) {
            alert(` id: ${pedido.id}\n cantidad: ${pedido.cantidad}\n color: ${pedido.color}`);
            console.log(pedido.count)
        },
        alertacolor: function (color) {
            alert(` seleccionaste el color: ${color}`);
            console.log(color.count)
        }
    },
    computed: {
    },
    mounted() {
    },
    components: {
    }
}
</script>

<style>
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

.precioEstilos {
    background: orangered;
    color: white;
    font-weight: "bold";
}
.container img {
    width: 100%;
}
</style>