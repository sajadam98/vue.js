<template>
  <div>
    <nav class="navbar navbar-expand-lg navbar-light bg-dark">
      <a class="navbar-brand" href="#" style="margin-left: 25%;font-size: 28px; color: azure">دراک</a>

      <div class="collapse navbar-collapse" id="navbarSupportedContent">
        <ul class="navbar-nav mr-auto">
          <li class="nav-item">
            <div>
              <a
                class="nav-link"
                id="about-us-link"
                href="#"
                @click="$bvModal.show('bv-modal-example')"
              >
                <b>درباره ما</b>
                <span class="sr-only">(current)</span>
              </a>

              <b-modal id="bv-modal-example" hide-footer>
                <template slot="modal-title">
                  <h4 id="about-us-title">درباره ما</h4>
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
          </li>
        </ul>
      </div>
    </nav>
  </div>
</template>
<script>
</script>
<style>
</style>
