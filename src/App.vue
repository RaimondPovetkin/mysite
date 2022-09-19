<template>
  <div class="wrap-content r4">
    <div class="colomn">
      <div class="title">
        {{items[activeIndex].title}}
      </div>
      <div class="description" v-for="item in items[activeIndex].description" :key="item">
        <div class="subtitle">
          {{item.subtitle}}
        </div>
        <div class="subbody">
          <div class="subbody-text">
            {{item.body}}
          </div>
        </div>
      </div>
      <div v-if="items[activeIndex].buttons" class="buttons">
        <div v-for="item in items[activeIndex].buttons" :key="item">
          <a :href="item.src">
            <button class="button-item">{{ item.btntitle }}</button>
          </a>
        </div>
      </div>
    </div>
    <div class="center"></div>
    <swiper
        :effect="'cards'"
        :grabCursor="true"
        :modules="modules"
        class="mySwiper"
        @slideChange="slideChange"
        :preventInteractionOnTransition="true"
        navigation
    >
      <swiper-slide></swiper-slide><swiper-slide></swiper-slide
    ><swiper-slide></swiper-slide><swiper-slide></swiper-slide
    ><swiper-slide></swiper-slide>
    </swiper>
  </div>
</template>
<script>
// Import Swiper Vue.js components
import { Swiper, SwiperSlide } from "swiper/vue";

// Import Swiper styles
import "swiper/css";

import "swiper/css/effect-cards";

import "./style.scss";

// import required modules
import { EffectCards } from "swiper";
import "swiper/css/navigation";
import { Navigation } from "swiper";
export default {
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    return {
      modules: [EffectCards, Navigation],
    };
  },
  data: () => ({
    activeIndex: 0,
    items:[
      {
        title:'Работал с технологиями:',
        description:[
          {
            subtitle: 'Вёрстка:',
            body: 'HTML5/CSS3 (SCSS), Методология БЭМ, Bootstrap'
          },
          {
            subtitle: 'Frontend:',
            body: 'JavaScript, Vue (VueX), React, Webpack'
          },
          {
            subtitle: 'Backend:',
            body: 'MySQL, PHP'
          },
          {
            subtitle: 'Другое:',
            body: 'Git/GitHub, WordPress'
          }
        ]
      },
      {
        title:'Система складского контроля и учета на предприятии',
        description:[
          {
            subtitle: 'Технологии:',
            body: 'PHP, MySQL, Bootstrap'
          },
          {
            subtitle: 'Предметная область:',
            body: 'Покупка и сбыт металла'
          },
          {
            subtitle: 'Результат:',
            body: 'Благодаря автоматизации процессов на предприятии удалось сократить рабочее время сотрудников'
          }
        ],
        buttons:[
          {
            btntitle: 'DEMO',
            src: 'http://o93124nt.beget.tech/boot/index.php'
          },
        ]
      },
      {
        title: 'WordPress шаблон одностраничного сайта',
        description: [
          {
            subtitle: 'Технологии:',
            body: 'HTML5/CSS3, БЭМ, WordPress'
          },
          {
            subtitle: 'Результат:',
            body: 'Создание максимально гибкого и адаптивного шаблона презентационного сайта и его админ-панели'
          },
        ],
        buttons:[
          {
            btntitle: 'DEMO',
            src: 'http://o93124nt.beget.tech/land/index.html'
          },
          {
            btntitle: 'Скачать',
            src: 'https://github.com/RaimondPovetkin/WP_theme/archive/refs/heads/master.zip'
          },
        ]
      },
      {
        title:'Домашний pet-проект',
        description: [
          {
            subtitle: 'Технологии:',
            body: 'JavaScript, canvas, (React)'
          },
          {
            subtitle: 'Идея:',
            body: 'Сервис, позволяющий создавать персонажей и анимацию путём простого взаимодействия с Drag n Drop интерфейсом. Применимо для производства игр и мультипликации'
          },
          {
            subtitle: 'Реализация:',
            body: 'Сейчас проект представляет собой своеобразную генерацию лиц, в ближайшее время планирую создать обширные возможности для кастомизации персонажа и перенести приложение на React'
          },
        ],
        buttons:[
          {
            btntitle: 'DEMO',
            src: 'http://o93124nt.beget.tech/pet/index.html'
          },
          {
            btntitle: 'GitHub',
            src: 'https://github.com/RaimondPovetkin/My-pet-project'
          },
        ]
      },
      {
        title:'SPA на Vue 3',
        description: [
          {
            subtitle: 'Технологии:',
            body: 'Vue 3, SCSS (mobile first), JavaScript'
          },
          {
            subtitle: 'О проекте:',
            body: 'Адаптивный одностраничный сайт, разработанный мною в рамках выполнения тестового задания для одной компании'
          },
        ],
        buttons:[
          {
            btntitle: 'DEMO',
            src: 'https://raimondpovetkin.github.io/customTest/'
          },
          {
            btntitle: 'GitHub',
            src: 'https://github.com/RaimondPovetkin/customTest'
          },
        ]
      },
    ]
  }),
  methods:{
    slideChange(e){
      this.activeIndex = Object.assign({}, e).activeIndex
    }
  }
};
</script>