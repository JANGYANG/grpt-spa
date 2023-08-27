<template>
    <div>
        <button type="button" class="btn btn-outline-secondary" style="width:100%">
            {{ buttonTxt }}
        </button>
    </div>
</template>

<script>
export default {
    props: {
        buttonTxt: String
    },
    data(){
        return {
            data : "TESTBUTTON"
        }
    }
}
</script>

<style>
    
</style>
