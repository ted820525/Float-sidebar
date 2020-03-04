# Float-sidebar
Created with CodeSandbox

# 用v-show來做開關的關閉
#@click="togglePage來做名子的切換


 <i @click="show = !show " class="fas fa-bars"></i>
    </div>
    <transition-group name="fade" tag="ul">

      <li key="close" v-show="show" @click="show = !show "><i class="fas fa-times"></i></li>
      <li key="1" v-show="show" @click="togglePage('Youtube')"><i class="fab fa-youtube"></i></li>
      <li key="2" v-show="show" @click="togglePage('Twitter')"><i class="fab fa-twitter"></i></li>
      <li key="3" v-show="show" @click="togglePage('Pinterest')"><i class="fab fa-pinterest"></i></li>
      <li key="4" v-show="show" @click="togglePage('Facebook')"><i class="fab fa-facebook"></i></li>
      <li key="5" v-show="show" @click="togglePage('Instagram')"><i class="fab fa-instagram"></i></li>
      <li key="sidebar" v-show="show"></li>
      
    </transition-group>
    
    export default {
  data(){
    return{
      show: false,
      page: 'Youtube'

    }

  },
  methods:{
    togglePage(page){
      this.show =! this.show;
      this.page = page;

    }


