<template>

  <div class="basket">
    <h2>Ваша корзина</h2>
    <h3>Товары резервируются на ограниченное время</h3>

    <div class="basket_table">
      <div class="basket_table-head">
        <div class="basket_tabele-head_item">Фото</div>
        <div class="basket_tabele-head_item biggest">Наименование</div>
        <div class="basket_tabele-head_item">Размер</div>
        <div class="basket_tabele-head_item">Количество</div>
        <div class="basket_tabele-head_item">Стоимость</div>
        <div class="basket_tabele-head_item">Удалить</div>
      </div>
      <div class="basket_table-body">
        <div class="basket_table-body_item">фото</div>
        <div class="basket_table-body_item biggest">
          <div class="title">Название</div>
          <div class="vendor_code">Артикул</div>
        </div>
        <div class="basket_table-body_item">размер</div>
        <div class="basket_table-body_item">
          <input type="number" name="count" value="1"/>
          <div class="control">
            <span class="plus">+</span>
            <span class="minus">-</span>
          </div>
        </div>
        <div class="basket_table-body_item">стоимость</div>
        <div class="basket_table-body_item">Х</div>
      </div>
      <div class="basket_table-footer">
        <div></div>
        <div></div>
        <div></div>
        <div>Итого:</div>
        <div class="Summary">12500руб.</div>
        <div></div>
      </div>
    </div>
    <div class="basket_zigzag">
      <div></div>
      <div></div>
      <div></div>
    </div>
    <form>
      <h2>Адрес доставки</h2>
      <h3>Все поля обязательны для заполнения</h3>

      <div class="form_body">
      <label for="delivery">
        <div>Выберите вариант доставки</div>
        <select>
          <option>Курьерская служба - 500руб</option>
          <option>Самовывоз - 250руб</option>
          <option>Почта России - 150руб</option>
        </select>
      </label>

      <label for="first_name">
        <div>Имя</div>
        <input type="text" id="first_name" name="first_name"/>
      </label>

      <label for="last_name">
        <div>Фамилия</div>
        <input type="text" id="last_name" name="last_name"/>
      </label>

      <label for="adress" class="long">
        <div>Адрес</div>
        <input type="text" id="adress" name="adress"/>
      </label>

      <label for="city">
        <div>Город</div>
        <input type="text" id="city" name="city"/>
      </label>

      <label for="zip_code">
        <div>Индекс</div>
        <input type="text" id="zip_code" name="zip_code"/>
      </label>

      <label for="phone">
        <div>Номер телефона</div>
        <input type="text" id="phone" name="phone"/>
      </label>
      </div>
    </form>
    <div class="basket_zigzag">
      <div></div>
      <div></div>
      <div></div>
    </div>
    <form>
      <h2>Варианты оплаты</h2>
      <h3>Все поля обязательны для заполнения</h3>

      <div class="summary">
        <div></div>
      </div>
    </form>
  </div>

</template>

<script>

  export default {
    name: "Basket"
  }

</script>

<style scoped>

  .basket h2{
    text-align: center;
    margin-top: 6rem;
    text-transform: uppercase;
    font-size: 2rem;
    margin-bottom: .6rem;
  }
  .basket h3{
    text-align: center;
    color: grey;
    font-style: italic;
    margin-top: 0; 
  }
  .basket .basket_table{
    margin-top: 6rem;
    color: grey;
    display: table;
    width: 100%;
    border-collapse: collapse;
  }
  .basket .basket_table .basket_table-head{
    display: table-row;
    border-bottom: 2px solid lightgrey;
    padding-bottom: 10px;
  }
  .basket .basket_table .basket_table-head .basket_table-head_item{
    display: table-cell;
    width: calc(100% / 6);
    border-bottom: 2px solid lightgrey;
    padding-bottom: 10px;
  }

  /* body */

  .basket .basket_table .basket_table-body{
    display: table-row;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item{
    display: table-cell;
    width: calc(100% / 6);
    border-bottom: 2px solid lightgrey;
    padding-bottom: 10px;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item:first-child{
    height: 95px;
    align-items: center;
    display: flex;
    justify-content: center;
    width: 100%;
    margin: 5px;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item{
    color: black;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item.count{
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 100%;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item input{
    border: none;
    width: 20px;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item input::-webkit-inner-spin-button{
    display: none;
  }

  /* плюс/минус */

  .basket .basket_table .basket_table-body .basket_table-body_item .control{
    display: flex;
    flex-direction: column;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item .control span{
    width: 10px;
    height: 10px;
    background-color: black;
    color: white;
    font-size: 10px;
    text-align: center;
  } 
  .basket .basket_table .basket_table-body .basket_table-body_item input:focus{
    outline: none;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item .vendor_code{
    color: grey;
    font-size: .8rem;
  }
  .basket .basket_table .basket_table-body .basket_table-body_item:last-child{
    text-align: center;
  }
  .basket .basket_table .basket_table-head .basket_table-head_item:not(:last-child){
    margin-right: 30px;
  }

  /* Дно */

  .basket .basket_table .basket_table-footer{
    display: table-row;
    background-color: rgba(27, 70, 80, .1);
  }
  .basket .basket_table .basket_table-footer div{
    display: table-cell;
    padding: 10px 0;
  }
  .basket .basket_table .basket_table-footer div.summary{
    color: orange;
    font-weight: bold;
  }
  .basket_zigzag{
    display: flex;
    width: 100%;
    flex-direction: row;
    justify-content: center;
    margin: 6rem 0;
  }
  .basket_zigzag div{
    border-right: 1px solid orange;
    border-bottom: 1px solid orange;
    width: 15px;
    height: 15px;
    transform: rotate(45deg);
    margin-right: 5px;
  }
  .basket form{
    border: 2px solid lightgrey;
    margin: 10px;
    padding-bottom: 6rem;
  }
  .basket form .form_body{
    display: flex;
    margin: 0 auto;
  }
  .basket form .form_body label{
    width: 45%;
    margin-bottom: 2rem;
  }
  .basket

  /* biggest */

  .biggest{
    width: 50% !important;
  }
</style>