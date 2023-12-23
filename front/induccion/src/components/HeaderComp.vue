<template>
    <!-- En cuanto a la altura no se que estaría bien así que lo dejo a tu criterio -->
    <div class="w-full flex text-white ">
        <div class="w-1/2 lg:w-1/4  ">
            <!-- Aqui va a ir el logo del tec para que dejes el espacio y ya lo pongas como te parezca -->
        </div>
        <nav class="w-1/2 lg:w-3/4 flex bg-blue-500 place-content-end">
            <!-- Aqui son los elementos -->
            <div class="lg:hidden">
                <p>Menu</p>
                <!-- Aquí se hará una nav var del tipo lateral para movil -->
            </div>
            <div class="hidden lg:flex">
                <!-- Esta es una nav var para computadora -->
                <div v-for="section in page_data" :key="section.id" class="px-5">
                    <!-- Este boton redirecciona a otras paginas -->
                    <div v-if="section.type == 'page'">
                        <div class="w-10">
                            <p>{{ section.title }}</p>
                        </div>
                    </div>
                    <!-- Este de aqui redirecciona a un menu desplegable -->
                    <div v-else>
                        <button>
                            {{ section.title }}
                        </button>

                    </div>

                </div>

            </div>
        </nav>
    </div>
</template>

<script>
export default {
    data() {
        return {
            page_data: [
                {
                    "title": "Inicio",
                    "type": "page",
                    "data": ""
                },
                {
                    "title": "Departamentos",
                    "type": "object",
                    "data": []
                },

            ]
        }
    },
}
</script>