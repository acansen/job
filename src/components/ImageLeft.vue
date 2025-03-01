<template>
  <div class="col full-width q-mb-xl">
    <div class="container row">
      <div class="col">
        <q-img
          loading="lazy"
          class="rounded-borders"
          style="max-height: 37rem"
          src="images/image_730x730px.webp"
        />
      </div>
      <div class="col q-pl-xl column flex-center">
        <div class="">
          <div class="text-h2 text-bold">SEX TOY QUIZ</div>
          <div class="text-h5 text-bold q-my-lg">Not sure which sex toy is right for you?</div>
          <div class="text-h6 q-mb-lg">
            Answer a series of anonymous questions and find your perfect match.
          </div>
          <q-btn
            label="Start quiz"
            class="text-bold"
            style="padding: 0.5rem 4rem"
            rounded
            outline
            color="white"
            size="1.5rem"
            no-caps
          ></q-btn>
        </div>
      </div>
    </div>
  </div>
</template>
<style scoped>
img {
  height: auto;
  max-width: 100%;
  object-fit: cover;
  transition: opacity 1.6s ease;
}

.background-image {
  bottom: 0;
  left: 0;
  position: absolute;
  right: 0;
  top: 0;
}

.background-image img {
  height: 100%;
  object-fit: cover;
  transition: opacity 1.6s ease;
  width: 100%;
}

.bannar {
  border: solid transparent;
  border-width: 0 0 50px;
  height: calc(100vh - 80px);
  max-height: 840px;
  overflow: hidden;
  position: relative;
  width: 100%;
}

@media screen and (min-width: 992px) {
  .bannar {
    min-height: 780px;
  }
}

@media screen and (max-width: 991px) {
  .bannar {
    border-width: 0 0 30px;
    height: calc(60vh - 80px);
    min-height: 600px;
  }
}

@media screen and (max-width: 575px) {
  .bannar {
    border-width: 0;
    height: 80vh;
    max-height: none;
    min-height: 410px;
    padding-top: 0;
  }
}

@media only screen and (max-width: 991px) and (orientation: landscape) {
  .bannar {
    height: calc(100vh - 80px);
    min-height: 600px;
  }
}

@media screen and (max-width: 575px) and (min-height: 1300px) {
  .bannar {
    height: 41rem;
  }
}

.bannar .container {
  display: flex;
  flex-direction: column;
  height: 100%;
  justify-content: flex-end;
  padding-bottom: 80px;
  padding-top: 80px;
  position: relative;
  z-index: 1;
}

@media screen and (max-width: 991px) {
  .bannar .container {
    padding-bottom: 40px;
    padding-top: 40px;
  }
}

.bannar .background-image source {
  position: absolute;
  top: 50%;
}

.bannar .background-image:before {
  background-image: linear-gradient(
    180deg,
    #0c0c0c,
    hsla(0, 0%, 5%, 0) 20%,
    hsla(0, 0%, 5%, 0) 67%,
    #0c0c0c 98%
  );
  bottom: 0;
  content: '';
  display: block;
  left: 0;
  opacity: 0.7;
  position: absolute;
  right: 0;
  top: 0;
  z-index: 0;
}
</style>
