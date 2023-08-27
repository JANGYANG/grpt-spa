<template>
  <div class="container" style="margin-top: 5vh; margin-bottom: 5vh;">
    <h1 class="text-center">GRPT GENERATOR</h1>
    <div class="d-grid gap-2 col-6 mx-auto" style="margin-top: .25rem;">
      <BasicDefaultButton buttonTxt="Text Generator"/>
    </div>
    <div class="d-grid gap-2 col-6 mx-auto" style="margin-top: .25rem;">
      <BasicDefaultButton buttonTxt="Image Generator"/>
    </div>
    <div class="d-grid gap-2 col-6 mx-auto" style="margin-top: .25rem;">
      <BasicDefaultButton buttonTxt="Logo Generator" to="/introduction"/>
      <!-- <nuxt-link class="btn btn-outline-primary" to="/introduction">자기소개 보기</nuxt-link> -->
    </div>
    
    <div class="container text-center" style="margin-top: 1rem;">
      <div class="row">
        <div class="col">
          <h2>Product Description</h2>
          <div class="input-group" style="width:100%">
            <span class="input-group-text">Description</span>
            <textarea class="form-control" rows="15" aria-label="With textarea" v-model="inputVal"></textarea>
          </div>
          
          
          <div class="default">
            <BasicDefaultButton buttonTxt="SUBMIT" style="width:100%" @click="generate(inputVal)"/>
          </div>
        </div>
        <div class="col">
          <div class="container">
            <h2>INPUT DATA</h2>
            <div style="border: 1px solid black; border-radius: .1rem; padding: .75rem;">
              <p style="font-color:white;white-space: pre-line;text-align: left;">{{ inputVal }}</p>
            </div>
            <h2>RESULT</h2>
            <div style="border: 1px solid black; border-radius: .1rem; padding: .75rem;">
              <p>{{ returnVal.content }}</p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  
</template>

<script>

export default{
  setup(){
    const mainStyle= reactive({
      height:'100vh', 
      backgroundColor:'white',
      padding:'5%'
    });
    
    const inputVal = ref("DEFAULT TEXT");
    const returnVal = reactive(
      {
        content: 'Please Put in the Description and Enter the Submit Button'
    });

    
    const generate = (inputVal) => {
      alert(inputVal);

      returnVal.content = "HELLO";
    }
    

    return {
      mainStyle,
      generate,
      inputVal, 
      returnVal
    };
  },

};
</script>

<style>
.default {
  width: 100%;
}
</style>