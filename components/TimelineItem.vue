<template>
  <li
    v-scroll-reveal
    :class="{'period': period, 'my-12 md:my-0': period}"
    class="timeline-item"
  >
    <div
      v-if="!period"
      class="timeline-info"
    >
      <span v-text="when" />
    </div>
    <div
      v-if="!period"
      class="timeline-marker"
    />
    <div class="timeline-content">
      <h3
        v-if="!period"
        class="font-bold text-lg timeline-header mt-0"
        v-text="title"
        :is="url?'a':'span'" :href="url || ''" target="_blank"
      />
      <h2
        v-else
        class="font-bold text-xl timeline-header mt-0 mb-2"
        :is="url?'a':'span'" :href="url || ''" target="_blank"
        v-text="title"
      />
      <p>
        <slot />
      </p>
    </div>
  </li>

    <!--<li>-->
      <!--<div class="border-line"></div>-->
      <!--<div class="date">-->
        <!--<span v-text="when" />-->
      <!--</div>-->
      <!--<div class="timeline-description">-->
        <!--<h3-->
        <!--v-if="!period"-->
        <!--class="font-bold text-lg timeline-header mt-0"-->
        <!--v-text="title"-->
        <!--/>-->
        <!--<h2-->
        <!--v-else-->
        <!--class="font-bold text-xl timeline-header mt-0 mb-2"-->
        <!--v-text="title"-->
        <!--/>-->
        <!--<p>-->
          <!--<slot />-->
        <!--</p>-->
      <!--</div>-->
    <!--</li>-->
</template>

<script>
export default {
  props: {
    period: {
      type: Boolean,
      default: false
    },
    title: {
      type: String,
      required: true
    },
    when: {
      type: String,
      required: false
    },
    url: {
      type: String,
      required: false
    }
  }
}
</script>
