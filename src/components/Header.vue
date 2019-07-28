<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="info">
      <b-navbar-brand href="#">NavBar</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>

      <div>
        <a id="show-btn" @click="$bvModal.show('bv-modal-example')">Open Modal</a>

        <b-modal id="bv-modal-example" hide-footer>
          <template slot="modal-title">
            <b>درباره ما</b>
          </template>
          <div class="d-block text-center">
            <h5>
              شرکت هوشمندسازان دراک
              <br />شماره تماس : 09172338020
            </h5>
          </div>
          <b-button class="mt-3" block @click="$bvModal.hide('bv-modal-example')">بستن</b-button>
        </b-modal>
      </div>
    </b-navbar>
  </div>
</template>
<script>
</script>
<style>
</style>
