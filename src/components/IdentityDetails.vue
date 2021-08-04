<template>
  <div class="identity-details">
    <div v-for="info in information" :key="info.icon">
      <span>
        <i :class="info.icon"></i>
        <p>{{ info.description }}</p>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "identity-details",
  data() {
    return {
      information: [
        { icon: "fas fa-envelope", description: "mace.mirasol@itemhound.com" },
        { icon: "fas fa-calendar-alt", description: "October 25, 1999" },
        { icon: "fas fa-mobile-alt", description: "09774501576" },
        {
          icon: "fas fa-map-marker-alt",
          description: "Iloilo City, Philippines"
        }
      ]
    };
  }
};
</script>
