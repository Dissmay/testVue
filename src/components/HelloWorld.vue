<template>
  <v-container>
    <h2>Grid Layout</h2>
    <v-row>
      <v-col
        tile
        outlined
        class="pa-2"
        v-for="(n, i) in getCards()"
        :key="i"
        >
        <cards></cards>
      </v-col>
    </v-row>
    <v-btn @click="indexD" v-if="!originalPosition"> 
      {{nameBtn}}
    </v-btn>
    <v-btn @click="indexOriginal" v-if="originalPosition">
      Go back
    </v-btn>
  </v-container>
</template>

<script>
  import cards from './cards'
  export default {
    data: () => ({
      alignments: [
        'center',
      ],
      cards :[
        {name:1},{name:1},{name:1},{name:1},
        {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
        {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
        {name:1},{name:1},{name:1},{name:1},{name:1}, {name:1},{name:1},{name:1},
        {name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},{name:1},
      ],
      index: 10,
      number:10,
      nameBtn: 'Show More',
      originalPosition: false
    }),
    components:{
      cards
    },
    methods:{
      getCards(){
       let tmp = this.cards.slice(0, this.index);
       return tmp;
      },
      indexD(){
        let lastIndex = this.cards.indexOf(this.cards[this.cards.length - 1]);
        if(this.index > lastIndex || this.index == lastIndex){
          return
        }else{
          this.index = this.index + this.number;
        }
      },
      indexOriginal(){
        this.index = this.number;
        this.originalPosition = false;
      }
    },
    created(){
      if(window.innerWidth == 1420){
        this.number = 10;
        this.index = 10;
      }
      if(window.innerWidth == 1920){
        this.number = 16;
        this.index = 16;
      }
      if(window.innerWidth == 1024){
        this.number = 8;
        this.index = 8;
      }
      if(window.innerWidth == 736){
        this.number = 6;
        this.index = 6;
      }
      if(window.innerWidth == 344){
        this.number = 2;
        this.index = 2;
      }
    },
    watch:{
      index(){
        if(this.index > 31 || this.index == 31){
          this.originalPosition = true;
          return 
        }
      }
    }
  }
</script>

<style scoped>

</style>
