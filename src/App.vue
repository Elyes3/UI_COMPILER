<template>
  <v-app>
    <v-main>
      <Nav/>
      <v-img src="@/assets/blob.svg" class="abs-fix"/>
      <div class="d-flex justify-center align-items-center min-h-100-vh flex-column">
        <h1>Type in your <span class="green-dark">code !</span> </h1>
        <v-container>
          <v-row>
            <Transition  name="slide-fade-right" appear>
            <v-col :cols="12" :md="5">
              <div class="textarea-cont" >
                <h2 class="green-dark">Input</h2>
                <v-textarea v-model="text1" label="Tunisian Code" variant="outlined" color="green darken-2" :no-resize="true"></v-textarea>
              </div>    
            </v-col>
            </Transition>
            <v-col :cols="12" :md="2" class="d-flex align-items-center">
              <v-btn block rounded="xl" size="x-large" color="green darken-2">Convert <v-icon icon="mdi-arrow-right"></v-icon></v-btn>
            </v-col>
            <Transition name="slide-fade-left" appear>
            <v-col :cols="12" :md="5">
              <div class="textarea-cont">
                <h2 class="green-dark">Output</h2>
                <v-textarea v-model="text2" label="Common Code" variant="outlined" :no-resize="true"  disabled></v-textarea>
              </div>
            </v-col>
          </Transition>
          </v-row>
        </v-container>
    </div>
    </v-main>
  
  </v-app>
</template>

<script>
import Nav from './components/Nav.vue'

export default {
  name: 'App',

  components: {
    Nav,
  },

  data: () => ({
    text1 : "",
    text2 : "",
    show : false,
  }),
  mounted(){
    this.show = true;
  }
}
</script>
<style scoped>
.min-h-100-vh{
  min-height: 92vh;
}
.align-items-center{
  align-items: center;
}
.green-dark{
  color: #4CAF50 !important;
}

.abs-fix{
  right : -100px;
  top : -100px;
  position : absolute;
  height:460px;
  width:500px;
}
.textarea-cont{
  border-radius : 10px;
  border: 1px solid green;
  padding: 10px;
}
@media (max-width: 960px) {
  .abs-fix{
    height:220px;
    width:300px;
    right : -120px;
  top : -50px;
  position : absolute;
  }

}
.slide-fade-right-enter-from{
  opacity : 0;
  transform:translateX(-30px);
}
.slide-fade-right-enter-active{
  transition :  1s;
}
.slide-fade-left-enter-from{
  opacity : 0;
  transform:translateX(30px);
}
.slide-fade-left-enter-active{
  transition :  1s;
}


</style>
