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
        Показать только 8 елементов
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
      index: 8,
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
          this.index = this.index + 8;
        }
      },
      indexOriginal(){
        this.index = 8;
        this.originalPosition = false;
      }
    },
    created(){
    },
    watch:{
      index(){
         if(this.index > 31 || this.index == 31){
          this.nameBtn = 'Товаров больше нет';
          this.originalPosition = true;
          return 
        }
      }
    }
  }
</script>

<style scoped>

</style>
