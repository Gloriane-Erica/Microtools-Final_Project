
<template>
  <header>
      <div class="d-flex justify-content-center align-items-center bg-primary text-white" style="border-bottom: 3px solid #adadad;">
        <div class="p-4">
          <h5 class="text-light text-center">Advanced Web Application Project</h5>
          <h1 class="text-warning" style="font-size: 100px;">MicroTool</h1>
        </div>
      </div>
  </header>
  <div class="container py-3" style="height: 100vh;">
    <div class="col-md-12 d-flex justify-content-between py-3" style="border-bottom: 3px solid #adadad;">
        <div class="card mt-3 " :class="flexBox" style="width: 18rem ;">
            <a @click="showFlexbox" class="text-decoration-none" >
              <div class="card-body">
                <h4 class="card-title">Flexbox</h4>
                <p class="card-text">A CSS layout module.</p>
              </div>
            </a>
        </div>
        <div @click="showMetricConverter" class="card mt-3 " :class="metricCon" style="width: 18rem ;">
            <a class="text-decoration-none">
              <div class="card-body">
                <h4 class="card-title">Metric Converter</h4>
                <p class="card-text">A tool for converting metric units</p>
              </div>
            </a>
        </div>
        <div @click="showCountdownTimer" class="card mt-3 " :class="countTimer" style="width: 18rem ;">
            <a class="text-decoration-none">
              <div class="card-body">
                <h4 class="card-title">Countdown Timer</h4>
                <p class="card-text">A countdown timer toool.</p>
              </div>
            </a>
        </div>
        <div @click="showPasswordGenerator" class="card mt-3" :class="passGen" style="width: 18rem ;">
            <a class="text-decoration-none">
              <div class="card-body">
                <h4 class="card-title">Password Generator</h4>
                <p class="card-text">A tool for generating random password.</p>
              </div>
            </a>
        </div>
        
    </div>
    <div class="row">
      <Flexbox :showFlexboxComponent="showFlexboxComponent"/>
      <PasswordGenerator :showPasswordGeneratorComponent="showPasswordGeneratorComponent"/> 
      <CountdownTimer :showCountdownTimerComponent="showCountdownTimerComponent"/>
      <MetricConverter :showMetricConverterComponent="showMetricConverterComponent"/>
    </div>
  </div>
</template>

<script>
  import Flexbox from './components/Flexbox.vue'
  import PasswordGenerator from './components/PasswordGenerator.vue'
  import CountdownTimer from './components/CountdownTimer.vue'
  import MetricConverter from './components/MetricConverter.vue'

  export default{
    components: {Flexbox, CountdownTimer, MetricConverter, PasswordGenerator},
    data(){
      return{
        showMetricConverterComponent: false,
        showFlexboxComponent: true,
        showPasswordGeneratorComponent: false,
        showCountdownTimerComponent: false,
        flexBox: 'active',
        passGen: '',
        countTimer: '',
        metricCon: '',
      }
    },
    methods: {
      showFlexbox(){
        this.showFlexboxComponent = true
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = false
        this.flexBox = 'active'
        this.passGen = ''
        this.countTimer = ''
        this.metricCon = ''

      },
      showPasswordGenerator(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = true
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = false
        this.flexBox = ''
        this.passGen = 'active'
        this.countTimer = ''
        this.metricCon = ''
      },
      showCountdownTimer(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = true
        this.showMetricConverterComponent = false
        this.flexBox = ''
        this.passGen = ''
        this.countTimer = 'active'
        this.metricCon = ''
      },
      showMetricConverter(){
        this.showFlexboxComponent = false
        this.showPasswordGeneratorComponent = false
        this.showCountdownTimerComponent = false
        this.showMetricConverterComponent = true
        this.flexBox = ''
        this.passGen = ''
        this.countTimer = ''
        this.metricCon = 'active'
      }
    }
  }
</script>

<style>
  div .active{
    background-color: #e7a930;
    cursor: pointer;
  }
  div .active a{
    color: aliceblue;
  }
  div a{
    color: #2c3f50;
  }
  label{
    font-weight: bold;
  }
</style>