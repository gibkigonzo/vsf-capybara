<template>
  <div
    v-if="getCmsData"
    :class="['cms-content', { container: sync }]"
    v-text="getCmsData.content"
  />
</template>

<script>
export default {
  name: "CmsBlock",
  props: {
    id: {
      type: Number,
      default: null,
      required: false
    },
    identifier: {
      type: String,
      default: null,
      required: false
    },
    sync: {
      type: Boolean,
      default: false,
      required: false
    }
  },
  computed: {
    getCmsData() {
      if (this.id) {
        return this.$store.getters[`cmsBlock/getCmsBlockById`](this.id);
      } else if (this.identifier) {
        return this.$store.getters[`cmsBlock/getCmsBlockByIdentifier`](
          this.identifier
        );
      }
      return null;
    }
  },
  // asyncData ({ store, route, context }) {
  // @TODO to cover SSR need find a way to pass props identifier/id to the asyncData()
  // for now it is not possible but assuming from some info it could be available later
  // we try to dispatch 'single' action which actually dispatch list to prefetch data anyway

  /* return new Promise((resolve, reject) => {
    store.dispatch('cmsBlock/single', {
      value: this.identifier
    }).then(res => {
      return resolve(res)
    })
  }) */
  // },
  created() {
    let queryKey = "";
    let queryValue = "";
    if (this.id) {
      queryKey = "id";
      queryValue = this.id;
    } else if (this.identifier) {
      queryKey = "identifier";
      queryValue = this.identifier;
    }
    if (queryKey && queryValue) {
      this.$store.dispatch("cmsBlock/single", {
        key: queryKey,
        value: queryValue
      });
    }
  }
};
</script>
