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
                                        v-model="simple" 
                                        placeholder="Nome do cliente" 
                                    />
                                </div>
                            </div>
                        </form>
                    </va-card-content>
                </va-card>
            </div>
        </div>
    </div>
</template>

<script setup>
</script>