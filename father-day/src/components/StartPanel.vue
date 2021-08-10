<template>
  <div class="panel">
    <h1>Dad's Taxi Calculator</h1>

    <h2>
    Dad's taxi is the cheapest, most used taxi on earth (probably). Wherever your little ones need to go, dad's cab company is usually the first port of call.
    Like being constantly exhausted, ferrying the kids around is part and parcel of fatherhood, and it's one that dads usually don't mind. But this Father's Day, why not pull the old switcheroo, and ask the kids to give a little back?
    Our Father's Day Chore Calculator tells you exactly what the children need to do to pay you back for your hard-earned petrol. Simply enter the number of miles you rack up in Dad's taxi per week, and we'll give them a list of 'repayment' tasks.
    <br><br>Happy Father's Day, dads!
    </h2>
    <div class="panel-bottom">
        <button class="btn-start">
            Start
        </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StartPanel',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style >
.panel {
    witdh: 60%;
    height: 80vh;
    min-height: 450px;
    max-width: 800px;
    min-width: 600px;
    margin: 48px;
    padding: 48px;
    background-color:rgb(255, 255, 255);
    border-radius: 12px;
    margin: auto;
}

.panel-bottom {
    margin-top: 120px;
}

body {
    background-color:rgb(79, 163, 228);
}

h1 {
    font-size: 48px;
    padding: 16px;
}
h2 {
    font-size: 24px;
    line-height: 32px;
    padding: 24px;
}

.btn-start {    
    width: 180px;
    background: none;
    border: 1px solid rgb(79, 163, 228);
    border-radius: 8px;
    padding: 16px;
    color:rgb(79, 163, 228);
    font-weight: 800;
}
.btn-start:hover {
    background-color: rgb(153, 209, 253);
    transition-duration: 800ms;
    color:white;
}

.btn-start:active {
    background-color: rgb(153, 209, 253);
}

</style>
