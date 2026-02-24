<script>
export default {
  data() {
    return {
      items: [1, 2, 3, 4, 5],
      arr: ["x", "y", "z"],
      Obj: {
        user1: "100$",
        user2: "200$",
        user3: "300$",
      },
      items_3: [1, 2, 3],
      /* страница 31 */
      hrefs: [
        { href: "1.html", text: "text1" },
        { href: "2.html", text: "text2" },
        { href: "3.html", text: "text3" },
      ],
      products: [
        {
          name: "product1",
          price: 100,
          quantity: 5,
        },
        {
          name: "product2",
          price: 200,
          quantity: 4,
        },
        {
          name: "product3",
          price: 300,
          quantity: 3,
        },
      ],
      items_33: [1, -2, 3, -4, 5],
      /* страница 34 */
      products: [
        {
          id: 1,
          name: "product1",
        },
        {
          id: 2,
          name: "product2",
        },
        {
          id: 3,
          name: "product3",
        },
      ],
      cssClasses: "text_red text_bold",

      objec: {
        done: true,
        selected: false,
      },
      objects: {
        hidden: false,
      },
      isValid: true,
      isDisabled: true,
      masseg: "",
      num: 0,
      num_1: 0,
      num_2: 0,
      sum_num: 0,
      text_1: "",
      text_2: "",
      fio: "",
      nam: "",
      lastnam: "",
      fazernam: "",
      textre: "",
      masivchik: [],
      check: true,
      arr_2: [],
      selected: "Cтрана",
      selected_1: "",
      selected_2: "",
      selected_3: "",
      selected_4: "",
      mas_nedeli: [
        "Понедельник",
        "Вторник",
        "Среда",
        "Четверг",
        "Пятница",
        "Суббота",
        "Воскресенье",
      ],
      mas_day: Array.from({ length: 31 }, (_, i) => i + 1),
      mas_months: [
        "Январь",
        "Февраль",
        "Март",
        "Апрель",
        "Май",
        "Июнь",
        "Июль",
        "Август",
        "Сентябрь",
        "Октябрь",
        "Ноябрь",
        "Декабрь",
      ],
      mas_year: [
        2000, 2001, 2002, 2003, 2004, 2005, 2006, 2007, 2008, 2009, 2010, 2011,
        2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019, 2020, 2021, 2022, 2023,
        2024, 2025, 2026,
      ],
      rebin: true,
      inputText: "",
      displayedText: "",
      mouseButton: "",
      message: "",
      newItem: "",
      itemsss: ["a", "b", "c", "d", "e"],
      users: [
        { id: 1, name: "эльдар", salary: 100, age: 30, isEdit: false },
        { id: 2, name: "эмир", salary: 200, age: 40, isEdit: false },
        { id: 3, name: "руслан", salary: 300, age: 50, isEdit: false },
      ],
    };
  }, //////
  methods: {
    add: function () {
      this.arr.push("eldar");
    },
    del: function () {
      this.arr.shift();
    },
    del_pos: function () {
      this.arr.pop();
    },
    del_pred_pos: function () {
      let a = this.arr.pop();
      this.arr.pop();
      this.arr.push();
    },
    sorted: function () {
      this.arr.sorted();
    },
    reverse: function () {
      this.arr.reverse();
    },
    pocaz: function () {
      this.objects.hidden = true;
    },
    ischez: function () {
      this.objects.hidden = false;
    },
    togl: function () {
      this.objects.hidden = !this.objects.hidden;
    },
    t: function (m) {
      let a = m.toUpperCase();
      return a;
    },
    cvad: function (num) {
      let a = num;
      return a * a;
    },
    fun_44_1: function () {
      this.sum_num = Number(this.num_1) + Number(this.num_2);
    },
    mena: function () {
      let a = this.text_1;
      let b = this.text_2;
      this.text_2 = a;
      this.text_1 = b;
    },
    razdel: function () {
      let a = this.fio;
      [this.nam, this.lastnam, this.fazernam] = a.split(" ");
    },
    spisoc: function () {
      let a = this.textre;
      this.masivchik = a.split(" ");
    },
    date_func: function () {
      let date = new Data();
      this.selected_4 = date.getFullYear();
      this.selected_3 = date.getMonth() + 1;
      this.selected_2 = date.getDate();
      return [year, mouth, day];
    },
    rebinn: function () {
      this.rebin = !this.rebin;
    },
    displayEnteredText() {
      this.displayedText = this.inputText;
    },
    showMessage() {
      this.message = "Ctrl был зажат!";
    },
    handleMouseButton(button) {
      this.mouseButton = button;
    },
    addItemToEnd() {
      if (this.newItem.trim() !== "") {
        this.itemsss.push(this.newItem);
        this.newItem = ""; // Очищаем инпут после добавления
      }
    },
    addItemToStart() {
      if (this.newItem.trim() !== "") {
        this.itemsss.unshift(this.newItem);
        this.newItem = ""; // Очищаем инпут после добавления
      }
    },
    removeItem(index) {
      this.itemsss.splice(index, 1);
    },
    removeUser(id) {
      this.users = this.users.filter((user) => user.id !== id);
    },
    // Удаление пользователя
    removeUser(id) {
      this.users = this.users.filter((user) => user.id !== id);
    },

    // Включение режима редактирования
    editUser(user) {
      // Сохраняем копию оригинальных данных на случай отмены
      this.$set(user, "originalData", { ...user });
      user.isEdit = true;
    },

    // Сохранение изменений
    saveUser(user) {
      // Удаляем временные данные
      delete user.originalData;
      user.isEdit = false;
    },

    // Отмена редактирования
    cancelEdit(user) {
      // Восстанавливаем оригинальные данные
      if (user.originalData) {
        user.name = user.originalData.name;
        user.salary = user.originalData.salary;
        user.age = user.originalData.age;
        delete user.originalData;
      }
      user.isEdit = false;
    },
  },
};
</script>

<template>
  <div v-for="elem_item in items">{{ elem_item ** 2 }}</div>
  <br />
  <ul>
    <li v-for="elem_item in items">{{ elem_item }}</li>
  </ul>
  <!-- страница 28 -->
  <ul>
    <li v-for="(elem, key) in arr">{{ key }}</li>
    <br />
    <!-- ключи имеются ввиду как индексы -->
  </ul>
  <!-- страница 29 -->
  <ul>
    <li v-for="(elem, key) in Obj">{{ elem }}</li>
  </ul>
  <br />
  <ul>
    <li v-for="(elem, key) in Obj">{{ key }} - {{ elem }}</li>
  </ul>
  <br />
  <ul>
    <li v-for="(elem, key, index) in Obj">
      {{ key }} - {{ elem }} - {{ index }}
    </li>
  </ul>
  <br />
  <ul>
    <li v-for="(elem, key, index) in Obj">
      {{ key }} - {{ elem }} - {{ index + 1 }}
    </li>
  </ul>
  <br />
  <br />
  <!-- страница 30 -->
  <div v-for="elem in items_3">
    <p>{{ elem }}</p>
    <p class="divider"></p>
  </div>
  <br />
  <ul>
    <template v-for="elem in items_3">
      <li>{{ elem }}</li>
      <li class="divider"></li>
    </template>
  </ul>
  <br />
  <!-- страница 31 -->
  <ul>
    <li v-for="href_i in hrefs">
      <a :href="href_i.href">{{ href_i.text }} </a>
    </li>
  </ul>
  <br />
  <table>
    <tr v-for="i in products">
      <td>{{ i.name }}</td>
      <td>{{ i.price }}</td>
      <td>{{ i.quantity }}</td>
    </tr>
  </table>
  <!-- страница 32 -->
  <p v-for="i in 30">{{ i }}</p>
  <br />
  <br />
  <!-- страница 33 -->
  <template v-for="item in items_33">
    <p v-if="item > 0">{{ item }}</p>
  </template>
  <br /><br />
  <!-- страница 34 -->
  <p v-for="id in products" :key="id.id">{{ id.name }}</p>
  <!-- страница 35 -->
  <br /><br />
  <ul>
    <li v-for="i in arr">{{ i }}</li>
    <button @click="add">
      нажми и ты добавишь в конец <br />
      имя создателя програмы
    </button>
    <button @click="del">нажми чтобы удалить <br />первый элемент</button>
    <button @click="del_pos">
      нажми чтобы удалить <br />последний элемент
    </button>
    <button @click="del_pred_pos">
      нажми чтобы удалить <br />пред последний элемент
    </button>
    <button @click="sorted">нажми и список отсартируется</button>
    <button @click="reverse">нажми и список отсартируется</button>
  </ul>
  <!-- страница 36 -->
  <!-- страница 37 -->

  <br /><br />
  <p :class="cssClasses">да я толстый и красный</p>
  <!-- Страница 38 -->
  <p :class="objec">во мне есть класс done и нет класса selected</p>
  <!-- страница 39 -->
  <br /><br />
  <button @click="pocaz">нажми и текст исчезнет</button>
  <br /><br />
  <button @click="ischez">нажми и текст появится</button>
  <br />
  <br />
  <button @click="togl">
    {{
      objects.hidden ? "Нажми чтобы текст появился" : "Нажми чтобы текст исчез"
    }}
  </button>
  <p :class="objects">я тут есть</p>
  <!-- CNHFYBWF 40 -->
  <h1 :class="{ active: true, valid: false }"></h1>
  <!-- страница 41 -->
  <h1 :class="{ valid: isValid, disabled: isDisabled }"></h1>
  <!-- страница 42 -->
  <p :style="{ color: 'green', backgroundColor: 'yellow' }">
    текст в зеленый цвет, а его фон - в желтый.
  </p>
  <p :style="{ fontWeight: 'bold', fontStyle: 'italic ' }">
    Сделайте его текст жирным и курсивным.
  </p>
  <!-- Модуль 4  -->
  <!-- страница 43 -->
  <br /><br /><br />
  <input v-model="masseg" />
  <br />
  <p>{{ masseg }}</p>
  <br />
  <p>{{ t(masseg) }}</p>
  <br />
  <input v-model="num" />
  <br />
  <p>{{ cvad(num) }}</p>
  <br /><br />
  <!-- страница 44 -->
  <input type="text" v-model="num_1" />
  <br />
  <input type="text" v-model="num_2" />
  <br />
  <button @click="fun_44_1">нажми на меня</button>
  <br />
  <p>{{ sum_num }}</p>
  <br />
  <input v-model="text_1" />
  <br />
  <input v-model="text_2" />
  <br />
  <button @click="mena">меняем</button>
  <br />
  <input type="text" v-model="fio" />
  <br />
  <button @click="razdel">разделяем фио</button>
  <br />
  <p>{{ nam }}</p>
  <br />
  <p>{{ lastnam }}</p>
  <br />
  <p>{{ fazernam }}</p>
  <br />
  <br />
  <textarea v-model="textre"></textarea>
  <br />
  <p>{{ textre }}</p>
  <br />
  <button @click="spisoc">нажми на меня и раздели</button>
  <br />
  <ul>
    <li v-for="i in masivchik">{{ i }}</li>
  </ul>
  <br />
  <!--  -->
  <input type="checkbox" v-model="check" />\
  <br />
  <p v-if="check">здесь я</p>
  <br />
  <!--  -->
  <br />
  <br />
  <br />
  <p>ты знаешь английски?</p>
  <input type="checkbox" v-model="arr_2" value="английский" />
  <p>ты знаешь немецкий</p>
  <input type="checkbox" v-model="arr_2" value="немецкий" />
  <p>ты знаешь русский</p>
  <input type="checkbox" v-model="arr_2" value="русский" />
  <ul>
    ты знаешь:
    <li v-for="i in arr_2">{{ i }}</li>
  </ul>
  <br /><br />
  <!-- страница 49 -->
  <p>Из какой ты страны:</p>
  <br />
  <select v-model="selected">
    <option>Россия</option>
    <option>Америка</option>
    <option>Германия</option>
  </select>
  <br />

  <p>Я из {{ selected }}</p>
  <!-- страница 50 -->
  <br /><br />
  <select v-model="selected_1">
    <option v-for="i in mas_nedeli">{{ i }}</option>
  </select>
  <br />
  <p>{{ selected_1 }}</p>
  <br />
  <select v-model="selected_2">
    <option v-for="i in mas_day">{{ i }}</option>
  </select>
  <br />
  <select v-model="selected_3">
    <option v-for="i in mas_months">{{ i }}</option>
  </select>
  <br />

  <select v-model="selected_4">
    <option v-for="i in mas_year">{{ i }}</option>
  </select>
  <br />
  <p>День: {{ selected_2 }}, Месяц: {{ selected_3 }}, Год: {{ selected_4 }}</p>
  <br />

  <!-- 51 -->
  <br /><br />
  <button @click="rebinn">нажми</button>
  <input type="checkbox" v-model="rebin" />
  <input type="text" :disabled="rebin" />

  <!-- 52 -->
  <br /><br />
  <input
    type="text"
    v-model="inputText"
    @keyup.enter="displayEnteredText"
    placeholder="Введите текст и нажмите Enter"
  />
  <p v-if="displayedText">Вы ввели: {{ displayedText }}</p>
  <br />
  <br />
  <a href="#" @click.ctrl.prevent="showMessage"
    >Ссылка (кликни с зажатым Ctrl)</a
  >
  <p v-if="message">{{ message }}</p>
  <br />
  <br />
  <a
    href="#"
    @click.left.prevent="handleMouseButton('left')"
    @click.middle.prevent="handleMouseButton('middle')"
    @click.right.prevent="handleMouseButton('right')"
  >
    Кликни разными кнопками мыши
  </a>
  <p>Нажата кнопка: {{ mouseButton }}</p>

  <!-- 53 -->
  <br /><br /><br />
  <ul>
    <li v-for="(item, index) in itemsss" :key="index">
      {{ item }}
    </li>
  </ul>
  <input v-model="newItem" placeholder="Введите текст" />
  <button @click="addItemToEnd">Добавить в конец</button>
  <br /><br />
  <ul>
    <li v-for="(item, index) in itemsss" :key="index">
      {{ item }}
    </li>
  </ul>
  <input v-model="newItem" placeholder="Введите текст" />
  <button @click="addItemToStart">Добавить в начало</button>
  <!-- 54 -->
  <br /><br /><br />
  <ul>
    <li
      v-for="(item, index) in itemsss"
      :key="index"
      @click="removeItem(index)"
      style="cursor: pointer; margin: 5px 0"
    >
      {{ item }}
    </li>
  </ul>
  <br />
  <p v-if="itemsss.length === 0">Список пуст</p>

  <!-- 55 -->
  <br /><br /><br />
  <div>
  <table border="1" cellpadding="5" style="border-collapse: collapse">
    <thead>
      <tr>
        <th>ID</th>
        <th>Имя</th>
        <th>Зарплата</th>
        <th>Возраст</th>
        <th>Действие</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="user in users" :key="user.id">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.salary }}</td>
        <td>{{ user.age }}</td>
        <td>
          <a href="#" @click.prevent="removeUser(user.id)">Удалить</a>
        </td>
      </tr>
    </tbody>
    
  </table>
</div>
  <p v-if="users.length === 0">Нет данных для отображения</p>
  <!-- 56 -->
  <br /><br /><br /><br />
  <div>
    <table border="1" cellpadding="5" style="border-collapse: collapse">
      <thead>
        <tr>
          <th>ID</th>
          <th>Имя</th>
          <th>Зарплата</th>
          <th>Возраст</th>
          <th>Действия</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <!-- Режим отображения -->
          <template v-if="!user.isEdit">
            <td>{{ user.id }}</td>
            <td>{{ user.name }}</td>
            <td>{{ user.salary }}</td>
            <td>{{ user.age }}</td>
            <td>
              <a href="#" @click.prevent="editUser(user)">Редактировать</a> |
              <a href="#" @click.prevent="removeUser(user.id)">Удалить</a>
            </td>
          </template>

          <!-- Режим редактирования -->
          <template v-else>
            <td>{{ user.id }}</td>
            <td><input v-model="user.name" type="text" /></td>
            <td><input v-model="user.salary" type="number" /></td>
            <td><input v-model="user.age" type="number" /></td>
            <td>
              <a href="#" @click.prevent="saveUser(user)">Сохранить</a> |
              <a href="#" @click.prevent="cancelEdit(user)">Отмена</a>
            </td>
          </template>
        </tr>
      </tbody>
    </table>
    <p v-if="users.length === 0">Нет данных для отображения</p>
  </div>
</template>

<style>
p {
  color: blue;
}

button {
  background-color: blue;
  color: greenyellow;
}
.text_red {
  color: red;
}
.text_bold {
  font: bold;
}
p.hidden {
  display: none;
}
</style>
