<template>
  <div class="home-four">
    <Header />

    <Slider />

    <div class="shane_tm_section" id="about">
      <div class="shane_tm_about">
        <div class="container">
          <About />
        </div>

      </div>
    </div>

    <div class="shane_tm_section" id="portfolio">
      <div class="shane_tm_portfolio">
        <Portfolio />
      </div>
    </div>

    <Skills />

    <Video />

    <div class="shane_tm_section">
      <div class="shane_tm_partners">
        <div class="container">
          <div class="partners_inner">
            <Brand />
          </div>
        </div>
      </div>
    </div>

    <CallToActions />

    <Footer />

  </div>
</template>

<script>
import Header from "../../components/Header";
import Slider from "../../components/slider/SliderFour";
import About from "../../components/about/AboutFour";
import Portfolio from "../../components/portfolio/PortfolioTwo";
import Skills from "../../components/skills/SkillsTwo";
import Video from "../../components/video/VideoTwo";
import Brand from "../../components/Brand";
import CallToActions from "../../components/calltoactions/CallToActionsTwo";
import Footer from "../../components/Footer";
export default {
  components: {
    Header,
    Slider,
    About,
    Portfolio,
    Skills,
    Video,
    Brand,
    CallToActions,
    Footer,
  },
};
</script>

<style lang="scss" scoped></style>
