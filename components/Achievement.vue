<template>
  <div class="projects-top">
    <div class="title-create">
      <div class="title-create__text">
        作ったもの
        <div class="title-create__icon"></div>
      </div>
    </div>
    <div class="projects">
      <Project
        v-for="(project, key, name) in projects"
        :key="name"
        :url="project.url"
        :name="project.name"
        :description="project.description"
        :img="project.img"
        :alt="project.alt"
        :performance="project.performance"
        :language="project.language"
        :use="project.use"
      />
    </div>
    <div class="title-achievement">
      <div class="title-achievement__text">
        実績
        <div class="title-achievement__icon"></div>
      </div>
    </div>
    <div class="achievement">
      <div class="achievement__left">
        <p>受賞</p>
        <p>登壇回数</p>
        <p>GitHub</p>
        <p>Qiita</p>
        <p>ブログ</p>
      </div>
      <div class="achievement__right">
        <p>：優秀新人社員賞（平成31年3月29日）</p>
        <p>：5回（100名以上2回、70名以上1回、20,30名以上2回）</p>
        <p>：Contributions2400↑ Star170↑ Followers260↑</p>
        <p>：Contributions2300↑ トレンド入り6回</p>
        <p>：アメーバブログで月36万PVの個人ブログの運営経験あり</p>
      </div>
    </div>
    <div class="title-other">
      <div class="title-other__text">
        Other
        <div class="title-other__icon"></div>
      </div>
    </div>
    <div class="other">
      <div class="other__text">
        <div class="other__text__left">
          <p>生年月日</p>
          <p>血液型</p>
          <p>趣味</p>
          <p>出身</p>
          <p>住み</p>
          <p>開発環境</p>
          <p>強み</p>
          <p>尊敬する人</p>
        </div>
        <div class="other__text__right">
          <p>：1993年12月7日</p>
          <p>：A型</p>
          <p>：映画、プログラミング</p>
          <p>：兵庫県 神戸市</p>
          <p>：東京都 墨田区</p>
          <p>
            ：MacBook Pro Air / Win10, デュアル, Corei7-7700
          </p>
          <p>
            ：好きで取り組める事を仕事にした事、天職です。
          </p>
          <p>
            ：ぐらばく（<a
              class="other__text__right__link"
              href="https://twitter.com/Grabacr07"
              >@Grabacr07</a
            >）さん<br />&nbsp;&nbsp;プログラミングを始めたきっかけであり目標です。
          </p>
        </div>
      </div>
      <div class="other__tweet">
        <div class="other__tweet--1">
          <!-- 1ツイート目 -->
          <blockquote class="twitter-tweet" data-lang="ja">
            blockquote
          </blockquote>
          <script
            async
            src="https://platform.twitter.com/widgets.js"
            charset="utf-8"
          ></script>
        </div>
        <!-- 2ツイート目 -->
        <div class="other__tweet--2">
          <blockquote class="twitter-tweet" data-lang="ja">
            blockquote
          </blockquote>
          <script
            async
            src="https://platform.twitter.com/widgets.js"
            charset="utf-8"
          ></script>
        </div>
        <!-- 3ツイート目 -->
        <div class="other__tweet--3">
          <blockquote class="twitter-tweet" data-lang="ja">
            blockquote
          </blockquote>
          <script
            async
            src="https://platform.twitter.com/widgets.js"
            charset="utf-8"
          ></script>
        </div>
      </div>
      <div class="speakerdeck">
        <script
          async
          class="speakerdeck-embed"
          data-id="e0d151ad238746c49614f8436662bab7"
          data-ratio="1.77777777777778"
          src="//speakerdeck.com/assets/embed.js"
        ></script>
      </div>
    </div>
    <!-- BACKボタン -->
    <div v-on:click="toggleSwitch(), hingeReturn()" class="back">
      <div class="back__text">
        <b>TOP</b>
        <span>（TOPのキャラクターロゴを5回押すと・・・？）</span>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import '~assets/style/_mixins.scss';

.title-create {
  @include title;
  animation-delay: 0.5s;
  .title-create__icon {
    display: block;
    position: absolute;
    background-image: url('~@/assets/images/aizwellenstan.png');
    width: 120px;
    height: 120px;
    z-index: 10;
    right: -35px;
    top: -20px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    border-radius: 50%;
    border: solid 2px;
  }
}

.title-achievement {
  @include title;
  margin-top: 150px;
  .title-achievement__icon {
    display: block;
    position: absolute;
    background-image: url('~@/assets/images/aizwellenstan.png');
    width: 120px;
    height: 120px;
    z-index: 10;
    left: -40px;
    top: -20px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    border: none;
    border-radius: 50%;
    border: solid 2px;
  }
}

.title-other {
  @include title;
  margin-top: 150px;
  .title-other__icon {
    display: block;
    position: absolute;
    background-image: url('~@/assets/images/aizwellenstan.png');
    width: 120px;
    height: 120px;
    z-index: 10;
    right: -35px;
    top: -20px;
    background-size: contain;
    background-position: center;
    background-repeat: no-repeat;
    border: none;
    border-radius: 50%;
    border: solid 2px;
  }
}

.achievement {
  width: 60%;
  margin: 0 auto;
  border: double 1px #283c5f;
  border-radius: 10px;
  padding: 40px 60px 25px 100px;
  text-align: left;
  display: flex;
  justify-content: center;
  &__left {
    font-size: 17px;
    p {
      margin-bottom: 15px;
    }
  }
  &__right {
    font-size: 17px;
    p {
      margin-bottom: 15px;
    }
  }
  &__right--company {
    font-size: 12px;
  }
}

.other {
  width: 60%;
  margin: 0 auto;
  border: double 1px #283c5f;
  border-radius: 10px;
  text-align: left;
  &__text {
    margin-top: 40px;
    display: flex;
    justify-content: center;
    &__left {
      font-size: 17px;
      p {
        margin-bottom: 15px;
      }
    }
    &__right {
      font-size: 17px;
      p {
        margin-bottom: 15px;
      }
      &__link {
        color: #0099e8;
        text-decoration: none;
        &:hover {
          opacity: 0.7;
          text-decoration: underline;
        }
      }
    }
  }
  &__tweet {
    display: flex;
    justify-content: space-between;
    margin: 35px auto 30px;
    flex-wrap: wrap;
    width: 650px;
  }
  &__tweet--1 {
    margin: 0 auto;
  }
  &__tweet--2 {
    width: 310px;
  }
  &__tweet--3 {
    width: 310px;
  }
}

.speakerdeck {
  max-width: 77%;
  margin: 40px auto;
}

.back {
  text-align: center;
  position: relative;
  text-decoration: none;
  color: #1b1b1b;
  background: #fff;
  border: 2px solid #1b1b1b;
  font-size: 20px;
  line-height: 50px;
  width: 60%;
  margin: 100px auto 30px;
  padding: 10px;
  border-radius: 5px;
  transition: 0.4s;
  &:hover {
    background: #1b1b1b;
    color: #fff;
    cursor: pointer;
    text-decoration: none;
  }
}
</style>

<script>
import Project from '@/components/Project.vue'
export default {
  components: {
    Project
  },
  data() {
    return {
      projects: [
        {
          url: 'https://github.com/aocattleya/Ramen-Timer',
          name: 'ラーメンタイマー',
          description: 'カップラーメンのタイマーアプリ',
          img: require('@/assets/images/timer.gif'),
          alt: 'ramen-timer',
          performance: 'GitHub★50↑ Qiitaトレンド入り 登壇1回',
          language: '【言語】JavaScript（Vue.js）',
          use: '【使用】Firebase, PWA, SweetAlert'
        },
        {
          url: 'https://github.com/aocattleya/MiniBookSearch',
          name: 'MiniBookSearch',
          description: '簡易書籍管理システム',
          img: require('@/assets/images/MiniBookSearch.png'),
          alt: 'MiniBookSearch',
          performance: 'GitHub★20↑ Qiitaトレンド入り 登壇1回',
          language: '【言語】Python（Flask）+ Vue.js',
          use: '【使用】Elasticsearch, axios, WebAPI'
        },
        {
          url: 'https://github.com/aocattleya/WordCloud-Japanese',
          name: 'WordCloud-Japanese',
          description: 'Mecabなしで実現するWordCloud',
          img: require('@/assets/images/WordCloud.png'),
          alt: 'WordCloud',
          performance: '登壇2回',
          language: '【言語】Python',
          use: '【使用】WordCloud'
        },
        {
          url: 'https://github.com/aocattleya/illustration-OriginalCharacters',
          name: 'OriginalCharacters',
          description: '描いたオリジナルキャラクターまとめ',
          img: require('@/assets/images/illustration.jpg'),
          alt: 'OriginalCharacters',
          performance: '',
          language: '【使用】FireAlpaca',
          use: '【詳細】「aocattleya」と「くりんちゃん」がいます。'
        },
        {
          url: 'https://github.com/aocattleya/Portfolio',
          name: 'Portfolio',
          description: 'Nuxt.jsでポートフォリオ',
          img: require('@/assets/images/aocattleyaSite.gif'),
          alt: 'Portfolio',
          performance: '登壇1回',
          language: '【言語】JavaScript（Nuxt.js）',
          use: '【使用】Animate.css, Firebase'
        },
        {
          url: 'https://github.com/aocattleya/Qiita-ContributionGraph',
          name: 'Qiita Contribution Graph',
          description: 'Qiitaいいね数の上位5つをグラフで出力',
          img: require('@/assets/images/qiiitaGraph.png'),
          alt: 'Qiita Contribution Graph',
          performance: '',
          language: '【言語】Lua',
          use: ''
        },
        {
          url: 'https://github.com/aocattleya/LeisurePass',
          name: 'LeisurePass！',
          description: 'チケット販売のECサイト',
          img: require('@/assets/images/LeisurePass.png'),
          alt: 'LeisurePass！',
          performance: '',
          language: '【言語】Java（Apache Struts2）',
          use: '【使用】Eclipse'
        },
        {
          url: 'https://github.com/aocattleya/KizunaAI-Lang',
          name: 'キズナアイ言語',
          description: 'r-fxxkを使用したBrainfuck系言語',
          img: require('@/assets/images/kizunaai.jpeg'),
          alt: 'キズナアイ言語',
          performance: '',
          language: '【言語】キズナアイ言語, Ruby',
          use: '【使用】r-fxxk'
        },
        {
          url: 'https://github.com/aocattleya/NightSky-Background',
          name: 'NightSky-Background',
          description: '星の流れる動く背景',
          img: require('@/assets/images/NightSky.gif'),
          alt: 'NightSky-Background',
          performance: '登壇1回',
          language: '【言語】CSS',
          use: '【使用】FireAlpaca'
        },
        {
          url: 'https://github.com/aocattleya/DLsite-Animation',
          name: 'DLsite-Animation',
          description: '崩壊するDLsite入り口風サイト',
          img: require('@/assets/images/DLsite-Animation.png'),
          alt: 'DLsite-Animation',
          performance: '',
          language: '【言語】JavaScript（Vue.js）, CSS',
          use: '【使用】Animate.css'
        },
        {
          url: 'https://github.com/aocattleya/GroupChat-App',
          name: 'GroupChat App',
          description: 'グループチャットアプリ',
          img: require('@/assets/images/GroupChat.gif'),
          alt: 'GroupChatApp',
          performance: '',
          language:
            '【言語】Ruby（Ruby on Rails） + Haml, SCSS(BEM) + jQuery(Ajax)',
          use: '【使用】AWS, Nginx'
        },
        {
          url: 'https://github.com/aocattleya/Vue-FormValidation',
          name: 'Vue FormValidation',
          description: 'Vue CLIでフォームバリデーション',
          img: require('@/assets/images/FormValidation.gif'),
          alt: 'VueFormValidation',
          performance: '',
          language: '【言語】JavaScript（Vue.js）',
          use: '【使用】SweetAlert'
        },
        {
          url: 'https://github.com/aocattleya/Visual_CSharpApps',
          name: 'VisualC# Apps',
          description: '８個のデスクトップアプリ',
          img: require('@/assets/images/CSharp.jpg'),
          alt: 'VisualC#Apps',
          performance: '',
          language: '【言語】C#',
          use: '【使用】VisualStudio2017, WinForms, CoreTweet'
        },
        {
          url: 'https://github.com/aocattleya/Totoro-Layer',
          name: 'Totoro-Layer',
          description: 'トトロのアニメーション',
          img: require('@/assets/images/totoro.png'),
          alt: 'ramen-timer',
          performance: '',
          language: '【使用】FireAlpaca',
          use:
            '【詳細】社内忘年会のビンゴゲーム待機画面用に描かせて頂いた動くトトロ。'
        },
        {
          url: 'https://github.com/aocattleya?tab=repositories',
          name: '他にも見る',
          description: '',
          img: require('@/assets/images/kurin-github.png'),
          alt: 'other',
          performance: '現在、40個以上のリポジトリがあります。',
          language: '',
          use:
            '全てのリポジトリにデモ画像などを充実させているので是非楽しんでください。'
        }
      ],
      isActive: false
    }
  },
  methods: {
    toggleSwitch() {
      this.isActive = false
      this.$emit('profile-open', this.isActive)
    },
    hingeReturn() {
      if (this.hinge === false) {
        this.hinge = true
      } else {
        this.hinge = false
      }
    }
  }
}
</script>
