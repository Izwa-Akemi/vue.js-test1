<template>
  <div class="about">
    <h2>商品詳細</h2>
    <p>current team:{{ this.teams[teamId].name }}</p>
    <button @click="increase">count</button>
    <p>{{ $store.state.sum }}</p>
    <p>Last team name clicked:{{$store.state.lastTeam}}</p>
    <router-link to="/">戻る</router-link>
  </div>
</template>


<script>
export default {
  methods:{
    increase:function(){
    this.$store.commit('incrementMutation',this.lastTeam);
    this.lastTeam = this.teams[this.teamId].name;
    }
  },
  data() {
    return {
      teams: [
        {
          id: "c36136ef-552f-4dc9-84b6-65ecb8574e81",
          name: "Team_A",
        },
        {
          id: "ed0459f5-716d-4ef4-99ba-5dc750dfe0d0",
          name: "Team_B",
        },
        {
          id: "60d0d5d5-8ce9-41d9-a65b-13a090c10ae1",
          name: "Team_C",
        },
      ],
    };
  },
  props: ["teamId"], //ShopListからidを受け取る
};
</script>