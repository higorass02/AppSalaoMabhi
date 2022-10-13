<template>
    <div class="form-elements">
        <formSearchCustumer :search="true"/>
        <newScheduling/>
    </div>
</template>

<script setup>
    import formSearchCustumer from "../../../components/forms/scheduling/formSearchCustumer.vue"
    import newScheduling from "../../../components/forms/scheduling/newScheduling.vue"
</script>