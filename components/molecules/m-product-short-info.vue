<template>
  <div class="m-product-short-info">
    <div class="m-product-short-info__mobile-top">
      <div>
        <SfHeading
          title="Cashmere Sweater"
          :level="1"
          class="sf-heading--no-underline sf-heading--left m-product-short-info__heading"
        />
        <div class="m-product-short-info__sub">
          <SfPrice
            regular="$50.00"
            class="sf-price--big m-product-short-info__sub-price"
          />
          <div class="m-product-short-info__sub-rating">
            <SfRating :score="4" :max="5" />
            <div class="m-product-short-info__sub-reviews desktop-only">
              Read all 1 review
            </div>
            <div class="m-product-short-info__sub-reviews mobile-only">
              (1)
            </div>
          </div>
        </div>
      </div>
    </div>
    <p class="m-product-short-info__description desktop-only">
      Find stunning women cocktail and party dresses. Stand out in lace and
      metallic cocktail dresses and party dresses from all your favorite brands.
    </p>
  </div>
</template>
<script>
import { SfPrice, SfRating, SfHeading } from "@storefront-ui/vue";
export default {
  name: "MProductShortInfo",
  components: {
    SfPrice,
    SfRating,
    SfHeading
  }
};
</script>
<style lang="scss" scoped>
@import "~@storefront-ui/vue/styles";

@mixin for-desktop {
  @media screen and (min-width: $desktop-min) {
    @content;
  }
}

.m-product-short-info {
  &__description {
    margin: $spacer-extra-big 0 ($spacer-big * 3) 0;
    font-family: $body-font-family-secondary;
    font-size: $font-size-regular-mobile;
    line-height: 1.6;
    @include for-desktop {
      font-size: $font-size-regular-desktop;
    }
  }
  &__heading {
    margin-top: $spacer-big;
    ::v-deep .sf-heading__title {
      font-size: $font-size-big-mobile;
      font-weight: $body-font-weight-primary;
      @include for-desktop {
        font-size: $h1-font-size-desktop;
        font-weight: $body-font-weight-secondary;
      }
    }
    @include for-desktop {
      margin-top: 0;
    }
  }
  &__mobile-top {
    display: flex;
    align-items: center;
    @include for-desktop {
      display: block;
    }
  }
  &__sub {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
  }
  &__sub-price {
    flex-basis: 100%;
    margin-top: $spacer-big / 4;
    @include for-desktop {
      flex-basis: auto;
      margin-top: $spacer-big / 2;
    }
  }
  &__sub-rating {
    display: flex;
    margin-top: $spacer-big / 2;
    @include for-desktop {
      margin-left: auto;
    }
  }
  &__sub-reviews {
    margin-left: 10px;
    font-size: 0.75rem;
  }
}
</style>
