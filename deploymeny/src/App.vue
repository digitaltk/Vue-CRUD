<template>
  <div id="app">

<div>
<h1> Deployments</h1>

  <b-card
    title="Frodo Baggins"

    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
Linux Deployments
    </b-card-text>

    <b-button href="#" variant="primary">Click Here</b-button>
  </b-card>
  
  
  <b-card
    title="Bilboo Baggins"

    tag="article"
    style="max-width: 20rem;"
    class="mb-2"
  >
    <b-card-text>
Windows Based Deployment    
</b-card-text>

  <b-button v-b-modal.modal-1>Click Here</b-button>

  <b-modal id="modal-1" title="Project Rollback">
 <h4>Choose a deployment to roll back on?</h4>
 

<b-container class="bv-example-row">
  <b-row>
    <b-col>Prodo A</b-col>
    <b-col><b-button>
    <b-button @click="modalShow = !modalShow">Button</b-button>

    <b-modal v-model="modalShow" title="Are You Sure?">Are You Sure You Want To Rollback?
   <b-card bg-variant="dark" text-variant="white" title="Prado A">
  <b-card-text>
Project Rollback  </b-card-text>
  <b-button href="exit()" variant="success">Yes, i want to roll back</b-button>
   <b-overlay :show="show" rounded="sm" @shown="onShown" @hidden="onHidden">
      <b-card title="Card with custom overlay content" :aria-hidden="show ? 'true' : null">
        <b-card-text>Lorem ipsum dolor sit amet, consectetur adipiscing elit.</b-card-text>
        <b-card-text>Click the button to toggle the overlay:</b-card-text>
        <b-button ref="show" :disabled="show" variant="danger" @click="show = true">
          No, I Do Not Want To Rollback
        </b-button>
      </b-card>
      <template v-slot:overlay>
        <div class="text-center">
          <b-icon icon="stopwatch" font-scale="3" animation="cylon"></b-icon>
          <p id="cancel-label">Please wait...</p>
          <b-button
            ref="cancel"
            variant="outline-danger"
            size="sm"
            aria-describedby="cancel-label"
            @click="show = false"
          >
            Cancel
          </b-button>
        </div>
      </template>
    </b-overlay>

</b-card>
   
    </b-modal>

    </b-button></b-col>
    <b-col>15:00</b-col>
    <b-col>31.07.2018</b-col>
  </b-row>

   <b-row>
    <b-col>Betie</b-col>
    <b-col> <b-button>Button</b-button></b-col>
    <b-col>20:00</b-col>
    <b-col>20.07.2018</b-col>
  </b-row>

   <b-row>
    <b-col>Prodo A</b-col>
    <b-col><b-button>Button</b-button></b-col>
    <b-col>15:00</b-col>
    <b-col>31.07.2018</b-col>
  </b-row>

   <b-row>
    <b-col>Arwin</b-col>
    <b-col><b-button>Button</b-button></b-col>
    <b-col>16:00</b-col>
    <b-col>31.05.2018</b-col>
  </b-row>

   <b-row>
    <b-col>Prodo A</b-col>
    <b-col><b-button>Button</b-button></b-col>
    <b-col>15:00</b-col>
    <b-col>31.07.2018</b-col>
  </b-row>

      <div class="mt-3">
      <h6 class="text-center">Select</h6>
      <b-pagination-nav number-of-pages="10" base-url="#" align="center"></b-pagination-nav>
    </div>
</b-container>
</b-modal>
</b-card>
</div>

  </div>
</template>

<script>
export default {
    data() {
      return {
        show: false,
         modalShow: false
      }
    },
    methods: {
      onShown() {
        // Focus the cancel button when the overlay is showing
        this.$refs.cancel.focus()
      },
      onHidden() {
        // Focus the show button when the overlay is removed
        this.$refs.show.focus()
      }
    }
  }
</script>

<style>
.bv-example-row{
  padding: 10px;


}

</style>
