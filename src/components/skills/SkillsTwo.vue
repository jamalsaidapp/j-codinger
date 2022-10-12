<template>
  <div class="shane_tm_section">
    <div class="shane_tm_skills">
      <div class="container">
        <div class="skills_inner">
          <div
            class="left"
            v-scroll-reveal="{ delay: 50, distance: '50px', duration: 1000 }"
          >
            <div class="shane_tm_title">
              <h3>J'ai de grandes compétences en développement et en programmation</h3>
            </div>
            <div class="text">
              <p>
                Je travaille sur un modèle de portfolio personnel professionnel, visuellement sophistiqué
                et technologiquement compétent, réactif et multifonctionnel.
              </p>
            </div>
          </div>
          <!-- End .left -->

          <div class="right">
            <div class="tokyo_progress">
              <div
                class="progress_inner"
                v-scroll-reveal="{
                  delay: 50,
                  distance: '20px',
                  duration: 1000,
                }"
              >
                <span>
                  <span class="label">Développement web</span>
                  <span class="number">95%</span>
                </span>
                <div class="background">
                  <div class="bar">
                    <div class="bar_in" style="width:95%"></div>
                  </div>
                </div>
              </div>
              <!-- End .progress_inner -->

              <div
                class="progress_inner"
                v-scroll-reveal="{
                  delay: 100,
                  distance: '20px',
                  duration: 1200,
                }"
              >
                <span>
                  <span class="label">Développement Mobile Apps</span>
                  <span class="number">80%</span>
                </span>
                <div class="background">
                  <div class="bar">
                    <div class="bar_in" style="width:80%"></div>
                  </div>
                </div>
              </div>
              <!-- End .progress_inner -->

              <div
                class="progress_inner"
                v-scroll-reveal="{
                  delay: 150,
                  distance: '20px',
                  duration: 1300,
                }"
              >
                <span>
                  <span class="label">Création de Logos</span>
                  <span class="number">90%</span>
                </span>
                <div class="background">
                  <div class="bar">
                    <div class="bar_in" style="width:90%"></div>
                  </div>
                </div>
              </div>
              <!-- End .progress_inner -->
            </div>
          </div>
          <!-- End .right -->
        </div>
      </div>
      <!-- End .conainer -->
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped></style>
