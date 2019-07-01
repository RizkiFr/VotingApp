<template>
  <v-container>
    <v-layout row wrap>
      <v-flex v-for="(vote, id) in votes" :key="id" md6 lg6 xs12>
        <v-card flat class="text-xs-center ma-3">
          <v-card-text>
            <v-avatar v-if="vote.id==1" size="300">
              <img src="1.png">
            </v-avatar>
            <v-avatar v-if="vote.id==2" size="300">
              <img src="2.png">
            </v-avatar>
            <div class="subheading mt-3"><span class="text-weight-bold title">{{vote.nama}}</span></div>
            <div class="grey--text">Capres &amp; Cawapres No. 0{{vote.id}}</div>
          </v-card-text>
          <v-btn block v-on:click="addVote(vote.id)" class="cyan">Vote</v-btn>
        </v-card>
          <v-card flat dark class="ma-3 red justify-end">
            <v-layout text-xs-center>
             <v-card-text class="title">{{vote.voting}} Voters</v-card-text>
            </v-layout>
          </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  nama: 'vote',
  apikey:'YOUR_API_KEY',
  idkey:'UChF7Xq30UeZEARi_29YVrvg',
  data(){
    return{
      votes:[]
    }
  },
  methods:{
    async getList() {
          this.axios.get('http://api.sinetral.online/public/vote')
          .then((response) => {(this.votes = response.data)
          })
        },

    addVote: function(id){
      this.axios.put('http://api.sinetral.online/public/vote/'+id).then((response)=>{
      this.getList(response)
      })
    },
  },
    mounted () {
    this.getList()
    setInterval(() => this.getList(), 300000); 
  }
}
</script>