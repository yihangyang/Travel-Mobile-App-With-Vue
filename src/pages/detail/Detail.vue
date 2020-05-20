<template>
  <div>
    <detail-banner></detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>

<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default {
  name: 'Detail',
  components: {
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data () {
    return {
      list: [{
        title: 'Adult',
        children: [{
          title: 'Adult Yearly',
          children: [{
            title: 'Adult Yearly Leipzig'
          }, {
            title: 'Adult Yearly Bonn'
          }]
        }, {
          title: 'Adult Monthly'
        }]
      }, {
        title: 'Student'
      }, {
        title: 'Child'
      }, {
        title: 'Discount'
      }]
    }
  },
  methods: {
    getDetailInfo () {
      axios.get('/api/detail.json?id=' + this.$route.params.id)
    }
  },
  mounted () {
    this.getDetailInfo()
  }
}
</script>

<style lang="stylus" scoped>
  .content
    height: 50rem
</style>
