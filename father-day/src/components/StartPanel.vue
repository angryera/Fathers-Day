<template>
  <div class="panel">
    <img :src="'../assets/happy_sm.jpg'" />
    <h1>Dad's Taxi Calculator</h1>
    <div v-if="currentState === 'init'" class="panel-help">
      <div class="row">
        <div class="col-md-8">
          <h2>
            Our Father's Day Chore Calculator tells you exactly what the
            children need to do to pay you back for your hard-earned petrol.
            Simply enter the number of miles you rack up in Dad's taxi per week,
            and we'll give them a list of 'repayment' tasks.
            <br /><br />Happy Father's Day, dads!
          </h2>
          <div class="panel-bottom">
            <b-button variant="outline-primary" size="lg" v-on:click="start">
              GO
            </b-button>
          </div>
        </div>
      </div>
    </div>

    <div v-if="currentState === 'started'" class="panel-help">
      <div class="input">
        <input
          class="input-miles"
          v-model="miles"
          placeholder=" "
          @change="mileChange"
        />
        <h6>
          Miles you rack up in Dad's taxi per week.
        </h6>
      </div>

      <h5>{{ miles }} miles every week for a year = £ {{ pound }}</h5>

      <div class="table-container">
        <b-table striped hover :items="work_list"></b-table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "StartPanel",

  components: {},

  directives: {},

  data() {
    return {
      currentState: "init",
      work_list: [],
      miles: 0,
      pound: 0,
    };
  },

  mounted() {},

  methods: {
    start: function() {
      this.currentState = "started";
    },
    mileChange: function() {
      var miles = this.miles;
      var pound = ((miles * 0.115) / 7) * 365;
      pound = Math.round(pound * 100) / 100;
      this.pound = pound;
      console.log(pound);

      var price_list = [2, 1.84, 2, 2.04, 1.71, 1.89, 1.84, 3, 2.19, 6];
      var work_type = [
        "Tidying bedroom",
        "Cleaning dishes",
        "Vacuuming",
        "Helping with cooking",
        "Putting bins out",
        "Hanging washing out",
        "Dusting",
        "Cleaning car",
        "Cleaning bathroom",
        "Babysitting",
      ];
      this.work_list.splice(0, this.work_list.length);
      for (var i = 0; i < price_list.length; i++) {
        var work = {
          No: i + 1,
          Type: work_type[i],
          Count: Math.round(pound / price_list[i]),
        };
        this.work_list.push(work);
      }
    },
  },

  watch: {
    miles: function() {
      this.mileChange();
    },
  },
};
</script>

<style>
img {
  position: absolute;
  right: 0px;
  bottom: 0px;
  border-radius: 15px;
}

.panel-help {
  position: absolute;
}

.table-container {
}

.btn-play {
  border-radius: 50%;
  width: 64px;
  height: 64px;
  border: 1px solid #0a7cd4;
  background: transparent;
}

.panel {
  width: 850px;
  height: 80vh;
  margin: 48px;
  padding: 48px;
  border-radius: 12px;
  margin: auto;
  background-color: rgb(205, 255, 254);
  position: relative;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 13px 27px -5px,
    rgba(0, 0, 0, 0.3) 0px 8px 16px -8px;
}

.panel-bottom {
  margin-top: 16px;
}

body {
  background: radial-gradient(circle, white 20px, skyblue 10px), skyblue;
  background-size: 25px 60px;
}

h1 {
  font-size: 32px;
  padding: 16px;
}

h2 {
  font-size: 24px;
  line-height: 32px;
  padding: 24px;
}

h5 {
  text-align: left;
  color: lightseagreen;
}

h6 {
  margin-top: 0px;
  margin-bottom: 32px;
}
.input {
  text-align: left;
}

input {
  margin: 12px 0;
  font-family: inherit;
  font-size: inherit;
  padding: 8px 16px;
  border: none;
  border-bottom: 2px solid #4fc08d;
  outline: none;
  margin-right: 24px;
  width: 100%;
}
</style>
