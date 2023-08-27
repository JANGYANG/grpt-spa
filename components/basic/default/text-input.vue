<template>
    <div class="input-group">
        <span class="input-group-text">With textarea</span>
        <textarea class="form-control" aria-label="With textarea"></textarea>
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
