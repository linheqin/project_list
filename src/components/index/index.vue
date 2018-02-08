  <template>
  <div>
    <x-header :left-options="{showBack: false}" :class="bg_color">小河项目</x-header>
    <group :class="group_project_list" :title="'VUE项目'">
      <cell :title="'企业微信项目（考勤统计）'" :class=project_list @click.native="showModule" value="2017-04 +"></cell>
      <cell :title="'企业微信项目（考勤打卡）'" :class=project_list @click.native="showModule" value="2017-04 +"></cell>
      <cell :title="'电影网站'" :class=project_list link="http://chenhuichao.com/vue2.x-douban/dist/#/" value="2017-04"></cell>
      <cell :title="'开心时刻'" :class=project_list link="http://happy.g1024.top/#/happy" is-link value="2017-03"></cell>
      <cell :title="'购物车'" :class=project_list link="https://sailengsi.github.io/sls-vuex2-demo/dist/" is-link value="2016-12"></cell>
    </group>
    <group :class="group_project_list" :title="'APP'">
      <cell :title="'象形企业（超级企业）'" :class=project_list @click.native="showPlugin" value="2016-03 ~ 2016-12"></cell>
    </group>
    <group :class="group_project_list" :title="'移动端游戏'">
      <cell :title="'赛车'" :class=project_list link="http://app98.vliang.com/carmask" is-link value="2015-12"></cell>
      <cell :title="'小熊抢币'" :class=project_list link="http://app98.vliang.com/joy" is-link value="2015-09"></cell>
      <cell :title="'2048小游戏'" :class=project_list link="http://app71.vliang.com/" is-link value="2015-07" is-link></cell>
      <cell :title="'嘉宝游戏'" :class=project_list link="http://app109.vliang.com/answer" is-link value="2015-03"></cell>
      <cell :title="'取数钱'" :class=project_list link="http://app132.vliang.com/home" is-link value="2015-02"></cell>
    </group>
    <group :class="group_project_list" :title="'PC网站'">
      <cell :title="'苏泊尔网站'" :class=project_list link="http://app70.vliang.com/home" is-link value="2014-12"></cell>
      <cell :title="'HTC'" :class=project_list link="http://www.htc.com/cn/go/htc-one-m8" is-link value="2014-11"></cell>
      <cell :title="'大众汽车'" :class=project_list link="http://app90.vliang.com/index.html" is-link value="2014-11"></cell>
      <cell :title="'圣诞家园'" :class=project_list link="http://app98.vliang.com/" is-link value="2014-09"></cell>
    </group>
    <group :class="group_project_list" :title="'移动端项目'">
      <cell :title="'邀请函'" :class=project_list link="http://app95.vliang.com/" is-link value="2015-10"></cell>
      <cell :title="'圣诞家园'" :class=project_list link="http://app98.vliang.com/" is-link value="2015-08"></cell>
      <cell :title="'丰田汽车'" :class=project_list link="http://app110.vliang.com/" is-link value="2015-06"></cell>
      <cell :title="'易车'" :class=project_list link="http://app114.vliang.com/" is-link value="2015-04"></cell>
      <cell :title="'青春岁月'" :class=project_list link="http://app121.vliang.com/home" is-link value="2015-03"></cell>
      <cell :title="'12星座'" :class=project_list link="http://app137.vliang.com/home" is-link value="2015-03"></cell>
      <cell :title="'巴不豆'" :class=project_list link="http://app143.vliang.com/" is-link value="2014-07"></cell>
      <cell :title="'十问'" :class=project_list link="http://app145.vliang.com/" is-link value="2014-07"></cell>
      <cell :title="'变装'" :class=project_list link="http://app210.vliang.com/" is-link value="2014-05"></cell>
    </group>
    <group :class="group_project_list" :title="'其他项目'">
      <cell :title="'其他'" :class=project_list @click.native="showModule1" value="2014-
      2018"></cell>
    </group>
  </div>
</template>

<script>
  import { XHeader, Actionsheet, TransferDom, ButtonTab, ButtonTabItem ,Cell,Confirm,ConfirmPlugin,Group,AlertModule, AlertPlugin,XButton, Alert} from 'vux'

  export default {
    directives: {
      TransferDom
    },
    components: {
      XHeader,
      Actionsheet,
      ButtonTab,
      ButtonTabItem,
      Cell,
      Confirm,
      ConfirmPlugin,
      Group,
      Alert,
      XButton, 
      AlertPlugin,
      AlertModule
    },
    data () {
      return {
        showMenus: false,
        project_list: "project_list",
        group_project_list: "group_project_list",
        bg_color: "blue_color",
        show: false
      }
    },
    methods: {
      showPlugin () {
        const _this = this 
        this.$vux.confirm.show({
          title: '温馨提示！',
          content: '可通过下载APP观看内嵌H5页面项目！',
          onCancel () {
          },
          onConfirm () {
            window.localtion.href = "http://sj.qq.com/myapp/detail.htm?apkName=net.sinedu.company"
          }
        })
      },
      showModule () {
        AlertModule.show({
          title: '温馨提示！',
          content: '您需要关注企业微信才能观看！',
        })
      },
      showModule1 () {
        AlertModule.show({
          title: '温馨提示！',
          content: '项目颇多,未完全展示,其他项目在本地,需要本地观看！',
        })
      }
    }
  }
</script>

<style lang="less">

  .overwrite-title-demo {
    margin-top: 5px;
  }
  .group_project_list>div {
    margin-top: 0;
    background: none;
  }

  .group_project_list .project_list {
    margin-bottom: 0.5rem;
    background: #fff;
    // border-top: 1px solid #eee;
    // border-bottom: 1px solid #eee;
  }
  .project_list:before {
    display: none;
  }
  .group_project_list>div:after {
    display: none;
  }
  .blue_color.vux-header {
    background: #39f;
  }
  .group_project_list .weui-cells__title {
    padding: 0.4rem 0 0.4rem 15px;
    margin-bottom: 0;
    font-weight: bold;
    font-size: 1rem;
    color: #39f;
  }
</style>
