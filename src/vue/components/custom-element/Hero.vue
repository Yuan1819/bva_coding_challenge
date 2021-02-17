<template>
  <div class="hero-container">
    <div class="hero hero--challenge desktop-only" :style="{ backgroundImage: `url(${desktop_img})` }">
      <div class="hero__inner">
        <div v-if="title.length > 0 || description.length > 0" class="page-width hero__content" :class="text_align">
          <h2 class="h1 mega-title" :style="{ color: color}">{{ title }}</h2>
          <div class="rte-setting mega-subtitle" :style="{ color: color}">{{ description }}</div>
          <a :href="cta_url"
            class="btn hero__btn"
            :style="{ color: color}"
            >
            {{ cta_text }}
          </a>
        </div>
      </div>
    </div>
    <div class="hero hero--challenge mobile-only" :style="{ backgroundImage: `url(${mobile_img})` }">
      <div class="hero__inner">
        <div v-if="title.length > 0 || description.length > 0" class="page-width hero__content center">
          <h2 class="h1 mega-title" :style="{ color: color}">{{ title }}</h2>
          <div class="rte-setting mega-subtitle" :style="{ color: color}">{{ description }}</div>
          <a :href="cta_url"
            class="btn hero__btn"
            :style="{ color: color}"
            >
            {{ cta_text }}
          </a>
        </div>
      </div>
    </div>
    <noscript>
      <div class="hero" :style="{ backgroundImage: `url(${desktop_img})` }"></div>
    </noscript>
  </div>

</template>

<script>
export default {
  props: {
    settings: String,
  },
  computed: {
    title: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.title;
    },
    description: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.description;
    },
    cta_text: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.cta_text;
    },
    cta_url: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.cta_url;
    },
    desktop_img: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.destkop_img;
    },
    mobile_img: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.mobile_img;
    },
    color: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.text_color;
    },
    text_align: function(){
      const settings_json = JSON.parse(this.settings);
      return settings_json.text_align;
    }
  }
};

</script>
