<template>
  <section>
    <div class="hero-banner" id="land-rover">
      <div class="container hero-banner__inner">
        <BookingForm />
      </div>
    </div>
  </section>
</template>

<script>
import BookingForm from "~/components/BookingForm.vue";
export default {
  name: "HeroBanner",
  components: {
    BookingForm,
  },
};
</script>

<style lang="scss" scoped>
.hero-banner {
  width: 100%;
  min-height: calc(100vh - 86px);
  display: flex;
  align-items: stretch;
  justify-content: flex-end;
  position: relative;
  background-size: cover;
  background-position: center;

  &#land-rover {
    background-image: url("~/assets/images/land-rover.jpg");
  }

  &__inner {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    position: relative;
    z-index: 10;
  }

  &:after {
    content: "";
    position: absolute;
    width: 100%;
    height: 100%;
    left: 0;
    top: 0;
    background: rgb(0, 0, 0);
    background: linear-gradient(
      90deg,
      rgba(0, 0, 0, 0) 0%,
      rgba(0, 0, 0, 0.6) 100%
    );
  }
}
</style>
