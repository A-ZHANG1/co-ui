<template>
  <div>
    <el-row>
      <el-col :span="18">
        <div style="background:#1f2d3d;height:60px">合同</div>
      </el-col>
      <el-col :span="6">
        <el-menu :default-active="$route.parth"
                 mode="horizontal"
                 background-color="#1f2d3d"
    text-color="#fff"
    active-text-color="#ffd04b"
    router>
    <el-menu-item index="/forceGraph">{{$t('navbar.all')}}</el-menu-item>
    <el-menu-item index="/subGraph">{{$t('navbar.subgraph')}}</el-menu-item>
    <el-menu-item index="/contractUpload">{{$t('navbar.contractImport')}}</el-menu-item>
    </el-menu>
    </el-col>
    </el-row>
    <el-row>
      <el-radio-group v-model="lang" size="small">
        <el-radio label="zh" border>中</el-radio>
        <el-radio label="en" border>EN</el-radio>
      </el-radio-group>
    </el-row>

    <el-row>
      <div style="margin:0px 0px 20px 110px;padding:0;width:820px;height:0px;background-color:white;overflow:hidden;"></div>
    </el-row>

  </div>
</template>

<script>
import ForceGraph from '@/views/ForceGraph'
import SubGraph from '@/views/SubGraph'
import {mapState} from 'vuex'

export default {
  components: {
    ForceGraph,
    SubGraph
  },
  // data () {
  //   return {
  //     lang: this.$store.language
  //   }
  // },
  computed: {
    lang: {
      get () {
        return this.$store.state.graphData.language
      },
      set (lang) {
        this.$i18n.locale = lang
        this.$store.dispatch('setLanguage', lang)
      }
    }
  },
  methods: {
  }
}
</script>
