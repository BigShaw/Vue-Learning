<template>
  <div id="app">
    <section class="hero is-primary">
      <div class="hero-body">
        <div class="container">
          <h1 class="title">
            Vue.js Learning
          </h1>
          <h2 class="subtitle">
            Practise following Tutorial From <a target="_blank" href="https://laracasts.com/series/learn-vue-2-step-by-step">laracasts.com</a>
          </h2>
        </div>
      </div>
    </section>
    <div class="section">
      <tabs>

        <tab name="Messages" :selected="true">
          <message title="Hello World" body="Lorem ipsum dolor sit amet."></message>
          <message title="Hello World aaa" body="Lorem ipadfasdfsadfsum dolor sit amet."></message>
        </tab>

        <tab name="Counter">
          <counter></counter>
          <coupon @applied="onCouponApplied"></coupon>
        </tab>

        <tab name="Tasks">
          <Tasks></Tasks>
        </tab>

        <tab name="Modal">
          <modal v-if="showModal" @close="showModal = false">
            <h1 slot="header">My Title</h1>
            <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod
              tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam,
              quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo
              consequat.</p>
            </modal>
            <a class="button" @click="showModal = true">Show Modal</a>
          </tab>

          <!-- <tab name="About Our aaa">
            <progress-view inline-template>
              <div>
                <h1>Your Progress through This Course is {{completionRate}}</h1>
                <p><button @click="completionRate += 10"></button></p>
              </div>
            </progress-view> 
          </tab>-->

        </tabs>

      </div>




    </div>

  </template>

  <script>
    import modal from './components/modal.vue'
    import Message from './components/Message.vue'
    import Counter from './components/Counter.vue'
    import tabs from './components/tabs.vue'
    import tab from './components/tab.vue'
    import Tasks from './components/Tasks.vue'
    import coupon from './components/coupon.vue'

    export default {
      name: 'app',
      components:{ 
        Message, 
        Counter,
        modal,
        tabs,
        tab,
        Tasks,
        coupon
      },
      data () {
        return {
          showModal : false
        }
      },
      methods: {

      },
      created(){
        Event.$on('applied',() => alert('Handling it!'));
      }
    }



  </script>

  <style lang="scss">



  </style>
