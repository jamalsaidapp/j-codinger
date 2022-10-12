<template>
  <div class="container">
    <div
      class="positon-relative"
      v-scroll-reveal="{ delay: 50, distance: '20px' }"
    >
      <div class="shane_tm_title">
        <div class="title_flex">
          <div class="left">
            <span>Portefeuille</span>
            <h3> Mes Projets </h3>
          </div>
        </div>
      </div>
      <!-- End shane_tm_title -->
      <div class="portfolio_filter">
        <ul>
          <li>
            <a
              v-on:click="activetab = 1"
              :class="[activetab === 1 ? 'active' : '']"
              >Tous</a
            >
          </li>
          <!-- End All for tabcontent 1 -->
          <li>
            <a
              v-on:click="activetab = 2"
              :class="[activetab === 2 ? 'active' : '']"
              >CRM</a
            >
          </li>
          <!-- End Vimeo tabcontent 2 -->
          <li>
            <a
              v-on:click="activetab = 3"
              :class="[activetab === 3 ? 'active' : '']"
              >Landing Websites</a
            >
          </li>
          <!-- End .Youtube tabcontent 3 -->
          <li>
            <a
              v-on:click="activetab = 4"
              :class="[activetab === 4 ? 'active' : '']"
              >Mobile Apps</a
            >
          </li>
          <!-- End Mix tabcontent 4 -->
        </ul>
      </div>
      <!-- End .portfolio-filter -->
    </div>

    <div v-if="activetab === 1" class="tabcontent">
      <div class="portfolio_list">
        <ul class="gallery_zoom">
          <CoolLightBox :items="allItems" :index="index" @close="index = null">
          </CoolLightBox>
          <li v-for="(image, imageIndex) in allItems" :key="imageIndex">
            <div class="inner" @click="index = imageIndex">
              <div class="entry shane_tm_portfolio_animation_wrap">
                <img class="image" :src="image.src" alt="Portfolio" />
              </div>
              <!-- End .entry -->
              <div class="mobile_title">
                <h3>{{ image.portfolioName }}</h3>
                <span>{{ image.portfolioType }}</span>
              </div>
            </div>
          </li>
          <!-- End li -->
        </ul>
      </div>

      <!-- End .portfolio_list -->
    </div>
    <!-- End .tabcontent 1 -->

    <div v-if="activetab === 2" class="tabcontent">
      <div class="portfolio_list">
        <ul>
          <CoolLightBox
            :items="crm"
            :index="index"
            @close="index = null"
          >
          </CoolLightBox>
          <li v-for="(image, imageIndex) in crm" :key="imageIndex">
            <div class="inner" @click="index = imageIndex">
              <div class="entry tokyo_tm_portfolio_animation_wrap">
                <img class="image" :src="image.src" alt="Portfolio" />
              </div>
              <!-- End .entry -->
              <div class="mobile_title">
                <h3>{{ image.portfolioName }}</h3>
                <span>{{ image.portfolioType }}</span>
              </div>
            </div>
          </li>
          <!-- End li -->
        </ul>
        <!-- End .portfolio_list -->
      </div>
    </div>
    <!-- End .tabcontent 2 -->

    <div v-if="activetab === 3" class="tabcontent">
      <div class="portfolio_list">
        <ul>
          <CoolLightBox
            :items="landing"
            :index="index"
            @close="index = null"
          >
          </CoolLightBox>
          <li v-for="(image, imageIndex) in landing" :key="imageIndex">
            <div class="inner" @click="index = imageIndex">
              <div class="entry tokyo_tm_portfolio_animation_wrap">
                <img class="image" :src="image.src" alt="Portfolio" />
              </div>
              <!-- End .entry -->
              <div class="mobile_title">
                <h3>{{ image.portfolioName }}</h3>
                <span>{{ image.portfolioType }}</span>
              </div>
            </div>
          </li>
          <!-- End li -->
        </ul>
        <!-- End .portfolio_list -->
      </div>
    </div>
    <!-- End .tabcontent 3 -->

    <div v-if="activetab === 4" class="tabcontent">
      <div class="portfolio_list">
        <ul>
          <CoolLightBox
            :items="mobile"
            :index="index"
            @close="index = null"
          >
          </CoolLightBox>

          <li v-for="(image, imageIndex) in mobile" :key="imageIndex">
            <div class="inner" @click="index = imageIndex">
              <div class="entry tokyo_tm_portfolio_animation_wrap">
                <img class="image" :src="image.src" alt="Portfolio" />
              </div>
              <!-- End .entry -->
              <div class="mobile_title">
                <h3>{{ image.portfolioName }}</h3>
                <span>{{ image.portfolioType }}</span>
              </div>
            </div>
          </li>
          <!-- End li -->
        </ul>
        <!-- End .portfolio_list -->
      </div>
    </div>
    <!-- End .tabcontent 4 -->
  </div>
</template>

<script>
export default {
  data() {
    return {
      activetab: 1,
      allItems: [],
      crm: [
        {
          src: require("../../assets/img/portfolio/CRM_1.png"),
          portfolioName: "LG CRM",
          portfolioType: "CRM",
        },
        {
          src: require("../../assets/img/portfolio/CRM_2.png"),
          portfolioName: "Gestion Parc",
          portfolioType: "CRM",
        },
      ],
      landing: [
        {
          src: require("../../assets/img/portfolio/LANDING_1.png"),
          portfolioName: "Nomatis.com",
          portfolioType: "Landing Websites",
        },
        {
          src: require("../../assets/img/portfolio/LANDING_2.png"),
          portfolioName: "Macrocom.ma",
          portfolioType: "Landing Websites",
        },
      ],
      mobile: [
        {
          src: require("../../assets/img/portfolio/MOBILE_1.jpg"),
          portfolioName: "Landing Websites",
          portfolioType: "Mobile Apps",
        },
        {
          src: require("../../assets/img/portfolio/MOBILE_2.jpg"),
          portfolioName: "Landing Websites",
          portfolioType: "Mobile Apps",
        },
      ],
      index: null,
    };
  },
  mounted() {
    this.allItems.push(...this.crm,...this.landing, ...this.mobile)
  }
};
</script>

<style lang="scss" scoped></style>
