<template>
  <q-page class="flex flex-center">
    <img alt="Quasar logo" src="~assets/quasar-logo-full.svg" />
  </q-page>
</template>

<style></style>

<script>
export default {
  name: "PageIndex",
  methods: {
    handleNotifications() {
      window.plugins.OneSignal.startInit("51cffe2a-2373-40dc-95f2-610a895c3888")
        .handleNotificationOpened(payload => {
          console.log("notificationOpenedCallback: " + JSON.stringify(payload));
        })
        .endInit();
    }
  },
  created() {
    this.handleNotifications();
  }
};
</script>
