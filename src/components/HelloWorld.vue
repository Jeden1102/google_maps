<template>
  <GMapAutocomplete
       placeholder="This is a placeholder"
       @place_changed="setPlace"
    >
  </GMapAutocomplete>
  <GMapMap
    :center="center"
    :zoom="10"
    map-type-id="terrain"
    style="width: 100vw; height: 20rem"
  >
    <GMapCluster :zoomOnClick="true">
      <GMapMarker
        :key="index"
        v-for="(m, index) in markers"
        :position="m.position"
        :clickable="true"
        :draggable="false"
        :icon="require('@/assets/logo.png')"
        @click="handleClick"
      >
      <GMapInfoWindow>
        <div>I am in info window <MyComponent/>
        </div>
      </GMapInfoWindow>
    </GMapMarker>
    </GMapCluster>
  </GMapMap>
</template>

<script>
export default {
  data() {
    return {
      center: { lat: 51.093048, lng: 6.84212 },
      markers: [
        {
          test:"abc",
          position: {
            lat: 57.093048,
            lng: 6.84212,
          },
        },
        {
          position: {
            lat: 51.198429,
            lng: 6.69529,
          },
        },
        {
          position: {
            lat: 51.165218,
            lng: 7.067116,
          },
        },
        {
          position: {
            lat: 51.09256,
            lng: 6.84074,
          },
        },
        {
          position: {
            lat: 51.09256,
            lng: 6.84074,
          },
        },
        {
          position: {
            lat: 53.09256,
            lng: 6.84074,
          },
        },
        {
          test:"Abc",
          position: {
            lat: 55.09256,
            lng: 6.84074,
          },
        },
        {
          position: {
            lat: 51.09256,
            lng: 6.84074,
          },
        },
      ],
    };
  },
  methods: {
    handleClick(event){
      console.log(event)
    }
  },
};
</script>

<style>
body {
  margin: 0;
}
</style>
