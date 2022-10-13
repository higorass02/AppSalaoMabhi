<template>
    <div class="form-elements">
        <div class="row">
            <div class="flex xs12">
                <va-card>
                    <va-card-title>Cadastrar novo Agendamento</va-card-title>
                    <va-card-content>
                        <form>
                            <div class="row">
                                <div class="flex md4 sm6 xs12">
                                    <va-input
                                        label="Nome do Cliente"
                                        placeholder="Nome do cliente"
                                        v-model="nameCustumer"
                                        id="name-custumer"
                                    />
                                </div>
                                <div class="flex md4 sm6 xs12">
                                    <va-select
                                        v-model="employee"
                                        label="Funcionario"
                                        text-by="description"
                                        track-by="id"
                                        :options="employees"
                                    />
                                </div>
                                <div class="flex md4 sm6 xs12">
                                    <va-select
                                        v-model="service"
                                        label="Serviço"
                                        text-by="description"
                                        track-by="id"
                                        :options="services"
                                    />
                                </div>
                            </div>
                            <div class="row">
                                <div class="flex md4 sm6 xs12">
                                    <va-date-input
                                        v-model="dateInput.simple"
                                        label="Data do Agendamento"
                                        manual-input
                                        id="date-scheduling"
                                    />
                                </div>
                                <div class="flex md4 sm6 xs12">
                                    <va-time-input v-model="startTime" label="Horario de Inicio" id="start-time" manual-input/>
                                </div>
                                <div class="flex md4 sm6 xs12">
                                    <va-time-input v-model="endTime" label="Horario de Termino" id="end-time" manual-input/>
                                </div>
                            </div>
                        </form>
                    </va-card-content>
                </va-card>
            </div>
        </div>
    </div>
</template>

<script>
    import { ref } from 'vue'
    export default {
        name: "newScheduling",
        props: {
            // custumer: {
            //     required: false,
            //     default: {
            //         name: 'default'
            //     }
            // }
        },
        setup() {
            const nameCustumer = ref('');
            // if(custumer.name) nameCustumer.value = custumer.name
            const employees = ref([
                {
                    id: 1,
                    description: "Marcia - Cabeleleira"
                },
                {
                    id: 2,
                    description: "Funcionaria - Manicure"
                },
            ]);
            const services = ref ([
                {
                    id: 1,
                    description: 'Cabelo'
                },
                {
                    id: 2,
                    description: 'Unha (Pé)'
                },
                {
                    id: 3,
                    description: 'Unha (Mão)'
                },
                {
                    id: 4,
                    description: 'Unha (Pé e Mão)'
                },
            ])
            const employee = ref([])
            const service = ref([])
            let dateStartTime = new Date()
            let dateEndTime = new Date()
            dateEndTime.setMinutes(dateStartTime.getMinutes() + 30);
            
            const startTime = ref( dateStartTime )
            const endTime = ref( dateEndTime )
            const dateInput = ref({
                simple: new Date(),
                disabled: '2018-05-09',
                range: { start: new Date(), end: datePlusDay(null, 7) },
                multiple: ['2018-04-25', '2018-04-27'],
            })
            
            function datePlusDay (date = new Date(), number) {
                const d = new Date(date)
                d.setDate(d.getDate() + number)
                return d
            }

            return{
                nameCustumer,
                employee,
                employees,
                dateInput,
                service,
                services,
                startTime,
                endTime
            }
        }
    }
</script>

<style scoped>
</style>