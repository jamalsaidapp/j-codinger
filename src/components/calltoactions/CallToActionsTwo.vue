<template>
  <div
    class="shane_tm_talk bg_image_props"
    :style="{ backgroundImage: 'url(' + imgSrc + ')' }"
    id="contact"
  >
    <div class="shape">
      <img
        class="svg"
        src="../../assets/img/svg/paper.svg"
        alt="partners brand"
      />
    </div>
    <!-- End shape -->

    <div class="background" id="talk">
      <a class="player"></a>
      <div class="overlay"></div>
    </div>
    <!-- End background -->

    <div class="talk_inner">
      <div class="text" v-scroll-reveal="{ delay: 100 }">
        <h3>Vous Avez Un Projet ?<br/> Nous Avons Les Compétences</h3>
      </div>
      <div class="button" v-scroll-reveal="{ delay: 200 }">
        <button class="white-fill-bg" @click="showModal">
          Faire Une Demande
        </button>
      </div>
    </div>
    <!-- End talk_inner -->

    <!-- Start Modalbox -->
    <transition name="fade">
      <!-- Modal -->
      <div
        :class="{ 'modal-mask': isActive }"
        id="modal"
        @click="closeModal"
        v-if="isVisible"
      >
        <div class="modal-dialog modal-dialog-centered " @click.stop>
          <div class="modal-content calltoactions-content">
            <div class="close" @click="closeModal">
              <img
                class="svg"
                src="../../assets/img/svg/cancel.svg"
                alt="cancel-img"
              />
            </div>
            <!-- End .close -->

            <div class="shane_tm_mobalbox_contact">
              <div class="box_inner">
                <div class="title">
                  <h3>Contactez-Nous</h3>
                </div>

                <div class="wrapper">
                  <div class="">
                    <div class="fields">
                      <Contact />
                    </div>
                  </div>
                </div>
                <!-- End wrapper -->

                <div class="short_info">
                  <ul>
                    <!-- End silgle address -->

                    <li>
                      <div class="list_inner">
                        <img
                          class="svg"
                          src="../../assets/img/svg/phone.svg"
                          alt="phone"
                        />
                        <p>
                          <a href="tel:+212669293758">+212 06 69 29 37 58</a>
                        </p>
                      </div>
                    </li>
                    <!-- End silgle address -->

                    <li>
                      <div class="list_inner">
                        <img
                          class="svg"
                          src="../../assets/img/svg/share.svg"
                          alt="share"
                        />

                        <Social />
                      </div>
                    </li>
                    <!-- End silgle address -->
                  </ul>
                </div>
                <!-- End modal conetent -->
              </div>
              <!-- End box inner -->
            </div>
            <!-- End modalbox news -->
          </div>
        </div>
      </div>
    </transition>
    <!-- End Modalbox -->
  </div>
  <!-- Start Modal -->
</template>

<script>
import Contact from "../Contact.vue";
import Social from "../Social.vue";
export default {
  components: {
    Contact,
    Social,
  },
  data() {
    return {
      imgSrc: require("../../assets/img/callto-action/bg_1.jpg"),
      isActive: false,
      isVisible: false,
    };
  },
  methods: {
    showModal: function() {
      this.isActive = true;
      this.isVisible = true;
    },
    closeModal: function() {
      this.isActive = false;
      this.isVisible = false;
    },
  },
};
</script>

<style lang="scss" scoped></style>
