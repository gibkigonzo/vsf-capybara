<template>
  <div class="m-product-gallery">
    <SfImage
      src="assets/storybook/productpage/productA.jpg"
      class="desktop-only"
    />
    <SfImage
      src="assets/storybook/productpage/productB.jpg"
      class="desktop-only"
    />
    <SfGallery
      class="m-product-gallery__mobile mobile-only"
      :images="[
        {
          small: { url: 'assets/storybook/productpage/productM.jpg' },
          big: { url: 'assets/storybook/productpage/productM.jpg' }
        },
        {
          small: { url: 'assets/storybook/productpage/productM.jpg' },
          big: { url: 'assets/storybook/productpage/productM.jpg' }
        }
      ]"
    />
  </div>
</template>
<script>
import { SfGallery, SfImage } from "@storefront-ui/vue";
export default {
  name: "MProductGallery",
  components: {
    SfGallery,
    SfImage
  }
};
</script>
<style lang="scss" scoped>
@import "~@storefront-ui/vue/styles";
.m-product-gallery {
  flex: 1;
  &__mobile {
    $height-other: 240px;
    $height-iOS: 265px;

    height: calc(100vh - #{$height-other});
    @supports (-webkit-overflow-scrolling: touch) {
      height: calc(100vh - #{$height-iOS});
    }
    ::v-deep .glide {
      &,
      * {
        height: 100%;
      }
      &__slide {
        position: relative;
        overflow: hidden;
      }
      img {
        position: absolute;
        left: 50%;
        transform: translateX(-50%);
        min-width: calc((375 / 490) * (100vh - #{$height-other}));
        @supports (-webkit-overflow-scrolling: touch) {
          min-width: calc((375 / 490) * (100vh - #{$height-iOS}));
        }
      }
    }
    ::v-deep .sf-gallery__stage {
      width: 100%;
    }
  }
}
</style>
