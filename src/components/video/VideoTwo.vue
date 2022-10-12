<template>
  <div class="shane_tm_section">
    <CoolLightBox :items="youtubeItems" :index="index" @close="index = null">
    </CoolLightBox>
    <div
      class="shane_tm_business_video"
      v-for="(image, imageIndex) in youtubeItems"
      :key="imageIndex"
    >
      <div class="bg">
        <div
          class="image jarallax"
          :style="{ backgroundImage: 'url(' + image.thumb + ')' }"
        ></div>
        <div class="overlay"></div>
      </div>
      <!-- End .bg -->

      <div class="content">

        <h3
          class="text"
          v-scroll-reveal="{ delay: 100, distance: '50px', duration: 1200 }"
        >
          Conseil en Systèmes d’information
        </h3>

        <div
          class="shane_tm_video_button"
          v-scroll-reveal="{ delay: 150, distance: '50px', duration: 1400 }"
        >
          <button class="popup-youtube" @click="showModal">
            Ouvrir un Ticket
          </button>
        </div>
      </div>
      <!-- End .content -->
    </div>
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

            <div class="shane_tm_mobalbox_contact">
              <div class="box_inner">
                <div class="title">
                  <h3>Creation du Ticket</h3>
                </div>

                <div class="wrapper">
                  <div class="">
                    <div class="fields">
                      <div class="tokyo_tm_contact">
                        <div class="fields">
                          <ValidationObserver v-slot="{ handleSubmit }">
                            <form class="contact_form" @submit.prevent="handleSubmit(onSubmit)">
                              <div class="first">
                                <ul>
                                  <ValidationProvider
                                      name="name"
                                      rules="required"
                                      v-slot="{ errors }"
                                  >
                                    <li>
                                      <input
                                          v-model="formData.name"
                                          type="text"
                                          placeholder="Name*"
                                          autocomplete="off"
                                      />
                                      <span class="inpur-error">{{ errors[0] }}</span>
                                    </li>
                                  </ValidationProvider>
                                  <ValidationProvider
                                      name="email"
                                      rules="required|email"
                                      v-slot="{ errors }"
                                  >
                                    <li>
                                      <input
                                          type="text"
                                          rules="required|email"
                                          v-model="formData.email"
                                          placeholder="Email*"
                                      />
                                      <span class="inpur-error">{{ errors[0] }}</span>
                                    </li>
                                  </ValidationProvider>
                                  <ValidationProvider
                                      name="phone"
                                      rules="required"
                                      v-slot="{ errors }"
                                  >
                                    <li>
                                      <input
                                          type="text"
                                          rules="required"
                                          v-model="formData.phone"
                                          placeholder="Télephone*"
                                      />
                                      <span class="inpur-error">{{ errors[0] }}</span>
                                    </li>
                                  </ValidationProvider>
                                  <ValidationProvider
                                      name="message"
                                      rules="required"
                                      v-slot="{ errors }"
                                  >
                                    <li>
                                    <textarea
                                        v-model="formData.message"
                                        placeholder="Description d'incident*"
                                    ></textarea>
                                      <span class="inpur-error">{{ errors[0] }}</span>
                                    </li>
                                  </ValidationProvider>
                                </ul>
                              </div>
                              <div class="tokyo_tm_button">
                                <button type="submit" class="white-fill-bg fill-black">
                                  Envoyer
                                </button>
                              </div>
                            </form>
                          </ValidationObserver>
                        </div>
                        <!-- END FIELDS -->
                      </div>
                    </div>
                  </div>
                </div>

              </div>

            </div>

          </div>
        </div>
      </div>
    </transition>

  </div>
</template>

<script>
import {ValidationObserver} from "vee-validate";
import {ValidationProvider} from "vee-validate/dist/vee-validate.full.esm";

export default {
  components: {
    ValidationObserver,
    ValidationProvider,
  },
  data() {
    return {
      index: null,
      youtubeItems: [
        {
          thumb: require("../../assets/img/support_it/IT_SUPPORT.png"),
        },
      ],
      isActive: false,
      isVisible: false,
      formData: {
        name: "",
        email: "",
        phone: "",
        message: "",
      },
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
    onSubmit() {
      console.log(this.formData);
      this.isVisible = false;
      this.formData =  {
        name: "",
            email: "",
            phone: "",
            message: "",
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
