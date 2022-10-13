<template>
    <div class="row">
        <div class="flex xs12">
            <va-card>
                <va-card-title>Registrar novo Agendamento</va-card-title>
                <va-card-content>
                    <form>
                        <div class="row">
                            <div class="flex md10 sm2 xs10">
                                <va-input v-model="text" placeholder="Entre com o nome do cliente" messages="entre com o nome do cliente"/>
                            </div>
                            <div class="flex md2 sm2 xs2">
                                <va-button class="mr-2 mb-2">
                                    <p style="margin-right: 10px;">Pesquisar</p>
                                    <va-icon class="icon-rigth input-icon" name="search" />
                                </va-button>
                            </div>
                        </div>
                    </form>
                </va-card-content>
            </va-card>
        </div>
        <div class="flex xs12">
            <va-card>
                <va-card-title> Listagem de clientes cadastrados </va-card-title>
                <va-card-content>
                    <div class="table-wrapper">
                        <table class="va-table va-table--striped va-table--hoverable">
                            <thead>
                                <tr>
                                    <th>Nome</th>
                                    <th>Email</th>
                                    <th>data do ultimo atendimento</th>
                                    <th>possui agendamentos futuros</th>
                                    <th>Agendar</th>
                                </tr>
                            </thead>

                            <tbody>
                                <tr>
                                    <td>Fulano de Tal</td>
                                    <td>fulanoDeTal@email.com.br</td>
                                    <td>00/00/0000 00:00</td>
                                    <td>
                                        <va-chip shadow class="mb-2 mr-2 flex-center" color="success">Sim</va-chip>
                                    </td>
                                    <td>
                                        <va-button class="mr-2 mb-2" color="primary"> Agendar </va-button>
                                    </td>
                                </tr>
                                <tr>
                                    <td>Outro fulano de Tal</td>
                                    <td>outrofulanoDeTal@email.com.br</td>
                                    <td>00/00/0000 00:00</td>
                                    <td>
                                        <va-chip shadow class="mb-2 mr-2 flex-center" color="danger">Não</va-chip>
                                    </td>
                                    <td>
                                        <va-button class="mr-2 mb-2" color="primary"> Agendar </va-button>
                                    </td>
                                </tr>
                            </tbody>
                        </table>
                    </div>
                </va-card-content>
            </va-card>
        </div>
    </div>
</template>

<script>
    import { ref } from "vue"

    export default {
        name: "formSearchCustumer",
        props: {
            search: {
                type: Boolean,
                default: false
            },
        },
        setup() {
            const search = ref()
            const text = ref()
            return {
                search,
                text
            };
        },
        // // computed: {},
        // // watch: {},
        // methods: {
        //     agendar() {
        //         this.search = false;
        //         // custumerEmits()
        //     },
        //     // custumerEmits() {
        //     //     const custumerData = {
        //     //         name: 'fulano'
        //     //     }
        //     //     this.$emit("custumerEmits", this.custumerData)
        //     // }
        // },
        // // emits: ["custumerEmits"]
        // // mounted: {}
    }    
</script>