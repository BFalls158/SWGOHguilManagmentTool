<template>
  <div>
    <div class="userHolder" v-for="user in users" :key="user.name" @click="toggleHidden(user)">
      <h2><b>{{user.name}}</b> GP: {{user.gp}}</h2>
      <div class="flexParent">
        <h6 class="flexChild" v-show="user.isVisible" v-for="toon in user.roster" :key="toon">{{toon.charName}} Gear Level: {{toon.gearLevel}} Power: {{toon.charGalPower}}</h6>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      users: [
        {
          name: 'Uttrs',
          isVisible: false,
          roster: [{
            charName: 'CLS',
            charGalPower: 20000,
            gearLevel: 12
          },
          {
            charName: 'JTR',
            charGalPower: 19000,
            gearLevel: 12
          },
          {
            charName: 'Cody',
            charGalPower: 17000,
            gearLevel: 11
          },
          {
            charName: 'GK',
            charGalPower: 16000,
            gearLevel: 10
          },
          {
            charName: 'Thrawn',
            charGalPower: 15000,
            gearLevel: 10
          }],
          gp: 1700000
        },
        {
          name: 'Cath',
          isVisible: false,
          roster: [{
            charName: 'CLS',
            charGalPower: 20000,
            gearLevel: 12
          },
          {
            charName: 'Han Solo',
            charGalPower: 21000,
            gearLevel: 11
          }],
          gp: 2500000
        }
      ]
      // isVisible: false
    }
  },
  methods: {
    toggleHidden (user) {
      user.isVisible = !user.isVisible
    }
  }
}
</script>

<style>
  /* h6 {
    display: float;
  } */
  .userHolder {
    border: 1px solid black;
    margin: 0px 20px 20px 0px;
  }
  .flexParent {
    padding: 5px;
    display: grid;
    grid-template-columns: 25% 25% 25% 25%;
    grid-template-rows: 100%;
  }
</style>