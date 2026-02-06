<script>
export default {
  data() {
    return {
      text1: "111",
      text2: "222",
      name: "john",
      surn: "smit",
      plane_img: "./image.png",
      text: "page",
      href: "page.html",
      /* страница 6 */
      num: 5,
      num1: 1,
      num2: 2,
      num3: 3,
      /* Страница 7 */
      arr1: ["x", "y", "z"],
      arr2: [1, 2, 3],
      /* Страница 8 */
      obj1: { x: 1, y: 2, z: 3 },
      /* страница 9-13 */
      /* страница 14 */
      textick_pomen: "Пока я такой",
      /* страница 15 */
      cost: 15,
      price: 320,
      /* страница 16 */
      hreffff: "https://web.telegram.org",
    };
  },
  methods: {
    /* страница 9 */
    show: function () {
      alert(Date());
    },
    /* Страница 11 */
    summa_num1_num2: function () {
      alert(this.num1 + this.num2);
    },
    /* Страница 12 */
    func12_1: function () {
      let den_nedeli = this.dop_func12_1(this.num2);
      alert(den_nedeli);
    },
    func12_2: function () {
      let data = new Date();
      let den_nedeli = this.dop_func12_1(data.getDay() - 1);
      alert(den_nedeli);
    },
    dop_func12_1: function (number) {
      let den_ned = {
        1: "Понидельник",
        2: "Вторник",
        3: "Среда",
        4: "Четверг",
        5: "Пятница",
        6: "Суббота",
        0: "Воскресенье",
      };
      return den_ned[number];
    },
    /* Страница 13 */
    squr: function (num) {
      alert(num * num);
    },
    /* Страница 14 */
    men_text: function () {
      this.textick_pomen = "Теперь я такой";
    },
    men_text1: function () {
      this.textick_pomen = "А вот теперь вообще другой";
    },
    cost_min1: function () {
      this.cost--;
    },
  },
  computed: {
    full: function () {
      return this.cost * this.price;
    },
  },
};
</script>
<template>
  <div>
    <h1>Это только начало</h1>
    <p>{{ text1 }}</p>
    <p>{{ text2 }}</p>
    <div>
      <h2>Меня зовут {{ name }}</h2>
    </div>
    <div>
      <h2>Моя фамилия {{ surn }}</h2>
    </div>
    <!-- страница 5 -->
    <img :src="plane_img" />
    <a :href="href">{{ text }} </a>
    <!-- Страница 6 -->
    <p>Квадрат {{ num }} = {{ num * num }}</p>
    <p>
      Cумма цифр {{ num1 }} {{ num2 }} {{ num3 }} = {{ num1 + num2 + num3 }}
    </p>
    <!-- страница 7 -->
    <p>Первое число массива = {{ arr1[0] }}</p>
    <p>Второе число массива = {{ arr1[1] }}</p>
    <p>Третье число массива = {{ arr1[2] }}</p>
    <p>Сумма второго массива = {{ arr2[0] + arr2[1] + arr2[2] }}</p>
    <!-- Страница 8 -->
    <p>Сумма элементов обьекта = {{ obj1.x + obj1.y + obj1.z }}</p>
    <!-- Страница 9 -->
    <!-- <p>{{ show() }}</p> -->
    <!-- она работает просто мешает) -->
    <!-- Страница 10 -->
    <button @click="show">data наведи</button> <br /><br />
    <button @mouseover="show">data нажми</button><br /><br />
    <!-- Страница 11 -->
    <button @mouseover="summa_num1_num2">Сумма чисел</button><br /><br />
    <!-- Страница 12 -->
    <button @mouseover="func12_1">Второй день недели это</button><br /><br />
    <button @click="func12_2">Сегодня день недели это</button><br /><br />
    <!-- Страница 13 -->
    <button @click="squr(num2)">Квадрат числа {{ num2 }} равен</button
    ><br /><br />
    <button @click="squr(num2)">
      Нажми на меня если <br />
      хочешь квадрат числа 2
    </button>
    <button @click="squr(num3)">
      Нажми на меня если <br />
      хочешь квадрат числа 3</button
    ><br /><br />
    <!-- Страница 14 -->
    <button @click="men_text">{{ textick_pomen }}</button> <br />
    <br />
    <p>{{ textick_pomen }}</p>
    <button @click="men_text">меняет по одному</button>
    <button @click="men_text1">меняет по другому</button><br />
    <br />
    <!-- Страница 15 -->
    <p>количесво контейнеров{{ cost }}</p>
    <p>цена контейнеров{{ price }}</p>
    <p>сколько стоят они все {{ full }}</p>

    <button @click="cost_min1">купили одну штуку</button><br />
    <br />
    <!-- Страница 16 -->
      <a @click.prevent :href="hreffff">ЕЕЕЕЕЕЕЕ</a><br /> <br />
      <button @click.once="cost_min1">купили одну штуку</button><br /> <br />
      
    <!-- Второй модуль -->
  </div>
</template>
