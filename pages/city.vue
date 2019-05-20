<template>
  <ul>
    <li v-for="city in cities" :key="city.id">{{ city.name }}</li>
  </ul>
</template>

<script>
export default {
  async asyncData({ app }) {
    const res = await app.$axios(
      "http://www.land.mlit.go.jp/webland/api/CitySearch?area=13"
    );
    console.log(res.data.data);
    return {
      cities: res.data.data
    };
  }
};
</script>
