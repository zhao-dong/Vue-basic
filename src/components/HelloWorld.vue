<template>
  <div class="hello">
    <h1>{{ msg }}</h1>

    <hr>
    <p> component and v for directive </p>
    <ol>
      <GameItemTestXXX v-for="item in games"  :key='item' v-bind:game="item"></GameItemTestXXX>
    </ol>
    <hr>
    <p> {{msg | toupper}} </p>
    <p> {{num | topercentage }} </p>
    <hr>
    <p> price is {{price}}, price added tax is {{priceInTax}}, price added tax in RMB is {{priceChinaRMB}}</p>
    <hr>
    <p> wacth property and button click</p>
     <button @click="btnClick(1000)"> Add 1000 </button>
     <hr>
     <p> set property 设置计算属性，同步更新元数据的值。</p>
     <button @click="btnClick1(10800)">把含税改价为10800円</button>
     <hr>
     <p> v-bind:class 为html标记绑定样式单class属性。</p>
     <div v-bind:class="{active:isActive}">红色文本1</div>
     <div :class="{active:isActive}">红色文本2</div>
     <button @click="btnClick2">改变class吧</button>

     <hr>
     <p> v-bind:class 为html标记绑定样式单class对象。</p>
     <div :class="myClass"> Red Text </div>

     <hr>
     <p> v-if 判断vue.js的变量的值，然后执行页面渲染逻辑。（if-elseif-else） </p>
     <h1 v-if="result == 0">成绩未公布</h1>
     <h1 v-else-if="result < 60">{{result}}分 - 考试不及格</h1>
     <h1 v-else-if="result < 80">{{result}}分 - 还需努力</h1>
     <h1 v-else>{{result}}分 - 考得不错，玩游戏吧！</h1>
     <button @click="btnClick3">考试成绩</button>

     <hr>
     <p> 标记是否显示html元素。(注意：v-show设置的标记在html DOM中不会消失) </p>
     <h1 v-show="true">任天堂新一代主机Switch</h1>
     <hr>
     <p> v-for 循环数组元素，整理内容显示到页面上。</p>
     <ul>
            <li v-for="(game, index) in gamesEx1" :key=(game,index)>({{index}}) {{game.title}} / 售价：{{game.price}}元</li>
     </ul>
     <hr>
     <p> v-for 循环JS对象，把对象内容循环显示到页面上。</p>
     <h1>JS对象迭代</h1>
     <div v-for="(value, key) in gamesEx2" :key="key">
         {{ key }} : {{ value }}
     </div>
     <hr>
     <p> v-on:(event) 页面元素的事件绑定。（click,keyup,load等等）</p>
     <h1>事件处理器</h1>
     <input id="txtName" v-on:keyup="txtKeyup($event)">
     <button id="btnOK4" v-on:click="btnClick4($event)">OK</button>
     <hr>
     <p> v-model 为表单控件元素创建双向数据绑定。（将JS变量的值“快速”设定到控件上，然后将用户输入的内容“快速”设置回JS变量）</p>
     <h1>表单控件绑定</h1>
     <input type="text" v-model="message" placeholder="来呀，编辑我吧！">
     <p>Message is: {{ message }}</p>
     <textarea v-model="message" placeholder="加入多行编辑" rows="8" cols="34"></textarea>
     <hr>
     <p> 表单复选框绑定 input[type="checkbox"] </p>
     <h1>表单复选框 </h1>
      <input type="checkbox" id="生化危机7" value="生化危机7" v-model="checkedGames">
      <label for="生化危机7">生化危机7xxx</label>
      <input type="checkbox" id="模拟飞行" value="模拟飞行" v-model="checkedGames">
      <label for="模拟飞行">模拟飞行xx</label>
      <input type="checkbox" id="塞尔达传说" value="塞尔达传说" v-model="checkedGames">
      <label for="塞尔达传说">塞尔达传说xx</label>
      <br>
      <p>您选择的游戏是: {{ checkedGames }}</p>
    <hr>
    <p> 表单单选按钮绑定 input[type="radio"] </p>
    <h1>表单单选按钮</h1>
    <h3>选择性别</h3>
    <input type="radio" id="male" value="男" v-model="pickedSex">
    <label for="male">男x</label>
    <br>
    <input type="radio" id="female" value="女" v-model="pickedSex">
    <label for="female">女x</label>
    <h3>选择爱好</h3>
    <input type="radio" id="game" value="玩游戏" v-model="pickedHobby">
    <label for="game">玩游戏x</label>
    <br>
    <input type="radio" id="movie" value="看电影" v-model="pickedHobby">
    <label for="movie">看电影x</label>
    <h3>选择结果</h3>
    <p>性别: {{ pickedSex }}</p>
    <p>爱好: {{ pickedHobby }}</p>
    <hr>
    <p> 表单下拉框绑定 v-model select </p>
    <h3>你最喜欢的NBA球星是：</h3>
   <select v-model="likedNBAStar" style="width:210px;">
       <option>科比</option>
       <option>詹姆斯</option>
       <option>哈登</option>
       <option>库里</option>
       <option>杜兰特</option>
   </select>

   <h3>我的全明星：</h3>
   <select v-model="likedNBAStars" multiple style="width:210px;height:210px;">
       <option>阿德托昆博</option>
       <option>怀特赛德</option>
       <option>阿尔德里奇</option>
       <option>戴维斯</option>
       <option>格里芬</option>
       <option>詹姆斯</option>
       <option>杜兰特</option>
       <option>巴特勒</option>
       <option>德罗赞</option>
       <option>哈登</option>
       <option>科比</option>
       <option>韦德</option>
       <option>伦纳德</option>
       <option>库里</option>
       <option>欧文</option>
       <option>保罗</option>
       <option>林树豪</option>
   </select>

   <h3>选择结果</h3>
   <p>我最最喜欢: {{ likedNBAStar }}</p>
   <p>我的全明星: {{ likedNBAStars }}</p>
   <hr>
   <p> .lazy .number .trim 表单修饰符 </p>
   <h1>用户注册</h1>

  <div>
      <label for="username">用户：</label>
      <input type="text" id="username" v-model.lazy="username" @change="checkUsername">
      <span v-if="checkUsernameOK">可注册</span>
  </div>
  <div>
      <label for="age">年龄：</label>
      <input type="number" id="age" v-model.number="age">
  </div>
  <div>
      <label for="content">个人简介：</label><br/>
      <textarea id="content" v-model.trim="content" cols="5" rows="8"></textarea>
  </div>

  <h4>信息区</h4>
  <p>{{username}}</p>
  <p>{{age}}</p>
  <p><pre>{{content}}</pre></p>
  <p>被包围在 pre 标签 元素中的文本通常会保留空格和换行符。而文本也会呈现为等宽字体。 </p>
  <hr>
  <p> 组件就是页面上的一小块区域内容，完成一个小的页面功能 Vue.js的组件不仅可以单独声明注册使用，还可以在Vue实例中进行局部注册使用。</p>
  <my-weather></my-weather>
  <hr>
  <p> 为自己的页面表格编写表行组件。</p>
  <h1>2017年最期待的游戏是：</h1>
  <table border="1">
      <tr>
          <td>编号</td>
          <td>游戏名称</td>
      </tr>
  </table>
  <hr>
  <p> 为Vue.js组件添加数据，使组件可以动态显示各种数据，注意是数据函数，不是数据属性。 </p>
  <my-weather> </my-weather>
  <hr>
  <p> 组件数据传递, 制作可接受参数的组件。</p>
  <h1>您的成绩评价</h1>
  <test-result :score="50"></test-result>
  <test-result :score="65"></test-result>
  <test-result :score="90"></test-result>
  <test-result :score="100"/>
  <hr>
  <p> 制作可接受变量参数的组件。</p>
  <div>请输入您的名字：<input v-model="myname"></div>
  <say-hello :pname="myname" />
  <hr>
  <p> 组件的数据, 为组件中接受到的变量进行逻辑验证。</p>
  <h1>身世之谜</h1>
  <show-member-info name="koma" :age="25" :detail="{address:'earth', language:'世界语'}"></show-member-info>
  <hr>
  <p> v-on 侦听组件事件，当组件触发事件后进行事件处理。$emit 触发事件，并将数据提交给事件侦听者。</p>
  <h1>人生加法</h1>
      <add-method :a="6" :b="12" v-on:add_event="getAddResult"></add-method>
      <h3>{{result1}}</h3>
  <hr>
  <p> slot是父组件与子组件的通讯方式，可以将父组件的内容显示在子组件当中。</p>
  <say-to pname="koma">
        你的视频做的太差了。
    </say-to>
    <say-to pname="mike">
        你千万不要学koma。
    </say-to>
    <say-to pname="john">
        你教教他们两个吧。
    </say-to>
  <hr>
  <p>slot命名 在子组件中通过为多个slot进行命名,来接受父组件的不同内容的数据。</p>
  <nba-all-stars c="奥尼尔" pf="加内特">
       <span slot="sf">皮尔斯</span>
       <span slot="sg">雷阿伦</span>
       <span slot="pg">隆多</span>
   </nba-all-stars>
</div>
</template>

<script>
import GameItemTestXXX from '@/components/GameItem.vue'
var CompMultiSpot = {
  props: ['c', 'pf'],
  template: '<div>' +
    '<div>中锋：{{c}}</div>' +
    '<div>大前：{{pf}}</div>' +
    '<div>小前：<slot name="sf"></slot></div>' +
    '<div>分卫：<slot name="sg"></slot></div>' +
    '<div>控卫：<slot name="pg"></slot></div>' +
    '</div>'
}
var WeatherComponent = {
  template: '<div>今天下雨，随它去吧！<strong>{{todayWeather}}</strong></div>',
  data: function () {
    return {
      todayWeather: '雨加雪'
    }
  }
}
var TestResult = {
  props: ['score'],
  template: '<div><strong>{{score}}分，{{testResult}}</strong></div>',
  computed: {
    testResult: function () {
      var strResult = ''
      if (this.score < 60) {
        strResult = '不及格'
      } else if (this.score < 90) {
        strResult = '中等生'
      } else if (this.score <= 100) {
        strResult = '优秀生'
      }
      return strResult
    }
  }
}
var CompTest = {
  props: ['pname'],
  template: '<div>你好，<strong>{{pname}}</strong>！</div>'
}
var CompSayTo = {
  props: ['pname'],
  template: '<div>' +
  '你好，<strong>{{pname}}</strong>！' +
  '<slot></slot>' +
  '</div>'
}
var CompParaValidate = {
  props: {
    name: {
      type: String,
      required: true
    },
    age: {
      type: Number,
      validator: function (value) {
        return value >= 0 && value <= 130
      }
    },
    detail: {
      type: Object,
      default: function () {
        return {
          address: 'US',
          language: 'English'
        }
      }
    }
  },
  template: '<div>姓名：{{this.name}}<br/>' +
  '年龄：{{this.age}}岁<br/>' +
  '地址：{{this.detail.address}}<br/>' +
  '语言：{{this.detail.language}} </div>'
}
var AddComp = {
  props: ['a', 'b'],
  template: '<div><button v-on:click="add">加吧</button></div>',
  methods: {
    add: function () {
      var value = 0
      value = this.a + this.b
      this.$emit('add_event', {
        result: value
      })
    }
  }
}
export default {
  name: 'HelloWorld',
  data () {
    return {
      result1: 0,
      myname: 'Koma',
      username: '',
      checkUsernameOK: false,
      age: '',
      content: '',
      likedNBAStar: null,
      likedNBAStars: [],
      pickedSex: '',
      pickedHobby: '',
      msg: 'Welcome to Your Vue.js App',
      num: 0.3,
      price: 1000,
      isActive: true,
      result: 0,
      message: 'I like MaLiAO',
      checkedGames: [],
      games: [
        {title: 'GAME1'},
        {title: 'GAME2'},
        {title: 'GAME3'}
      ],
      gamesEx1: [
        {title: '勇者斗恶龙', price: 500},
        {title: '库跑卡丁车', price: 400},
        {title: '马里奥世界', price: 550}
      ],

      gamesEx2: {
        title: '乌贼娘2代',
        price: 350,
        pubdate: '2017年夏季',
        category: '射击',
        agerange: '全年龄'
      },
      myClass: {
        active: true,
        big: true
      }
    }
  },
  components: {
    GameItemTestXXX,
    'my-weather': WeatherComponent,
    'test-result': TestResult,
    'say-hello': CompTest,
    'show-member-info': CompParaValidate,
    'add-method': AddComp,
    'say-to': CompSayTo,
    'nba-all-stars': CompMultiSpot
  },
  filters:
  {
    toupper: function (value) {
      return value.toUpperCase()
    },
    topercentage: function (value) {
      return value * 100 + '%'
    }
  },
  computed: {
  /*
    priceInTax: function () {
      return this.price * 1.08
    }, */

    priceInTax: {
      get: function () {
        return this.price * 1.08
      },
      set: function (value) {
        this.price = value / 1.08
      }
    },
    priceChinaRMB: function () {
      return Math.round(this.priceInTax)
    }
  },
  methods: {
    btnClick: function (newPrice) {
      this.price += newPrice
    },
    btnClick1: function (newPrice) {
      this.priceInTax = newPrice
    },
    btnClick2: function () {
      this.isActive = !this.isActive
    },
    btnClick3: function () {
      this.result = Math.round(Math.random() * 100)
    },
    txtKeyup: function (event) {
      this.debugLog(event)
    },
    btnClick4: function (event) {
      this.debugLog(event)
    },
    debugLog: function (event) {
      console.log(
        event.srcElement.tagName,
        event.srcElement.id,
        event.srcElement.innerHTML,
        event.key ? event.key : ''
      )
    },
    checkUsername: function () {
      if (this.username.length > 0) this.checkUsernameOK = true
      else this.checkUsernameOK = false
    },
    getAddResult: function (pval) {
      this.result1 = pval.result
    }
  },
  watch: {
    price: function (newValue, oldValue) {
      console.log(newValue, oldValue)
      this.msg += newValue
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
body {
  font-size: 24px;
}
.active {
  color: red;
}
.big {
  front-weight: bolder;
  font-size: 64px;
}
</style>
