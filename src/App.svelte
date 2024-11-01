<script>
  import FlexShow from "./lib/FlexShow.svelte";

 //массивы для select'ов убрать в модуль и импортировать
 import { display  } from "./lib/select_values.svelte";
 import  {flex_direction} from "./lib/select_values.svelte";
 import {just_content} from "./lib/select_values.svelte"

 // let disp_selected = $state("block");
 // let direct_selected = $state("row");
 // let just_content_selected = $state("flex-start");

 // Объект для биндинга выбранных в select'ах значений
 let flexvals = $state({
   disp: "block",
   direct: "row",
   just_content: "flex-start",
 });

</script>

<main>
 <div>
   <h1>START</h1>

   <div class="combos">
     <div>
       <select bind:value={flexvals.disp}>
         {#each display as item}
           <option>
             {item}
           </option>
         {/each}
       </select>
     </div>

     <div>
       <select bind:value={flexvals.direct}>
         {#each flex_direction as item}
           <option>
             {item}
           </option>
         {/each}
       </select>
     </div>

     <div>
       <select bind:value={flexvals.just_content}>
         {#each just_content as item}
           <option>
             {item}
           </option>
         {/each}
       </select>
     </div>
   </div>

   <div>
     <!-- Оптимизация кода 1 -->
     <!-- <FlexShow
       --disp={disp_selected}
       --direct={direct_selected}
       --justcont={just_content_selected}
       display={disp_selected}
       flex_dir={direct_selected}
       just_cont={just_content_selected}
     
     <!-- Оптимизация кода 2 -->
     <!-- <FlexShow
     display={disp_selected}
     flex_dir={direct_selected}
     just_cont={just_content_selected}
   /> -->
     <!-- Оптимизация кода 3 -->
     <FlexShow selected={flexvals} />
   </div>
 </div>
</main>

<style>
 .combos {
   display: flex;
 }
 main {
   display: flex;
   justify-content: center;
 }
</style>


<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Вывод GIF картинки</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@600&display=swap" rel="stylesheet">
    <style>
        /* Основные стили для body */
        body {
            display: flex;
            flex-direction: column; /* Вертикальное расположение элементов */
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #282c34; /* Темный фон для контраста */
            color: #ffffff; /* Белый текст */
            font-family: 'Montserrat', sans-serif; /* Используем шрифт Montserrat */
            animation: flashBackground 3s infinite; /* Анимация фона */
        }

        /* Контейнер для GIF */
        .gif-container {
            width: 300px;
            height: 300px;
            background-image: url('https://media.tenor.com/NM-HUmZ_y2cAAAAM/%D0%B7%D1%83%D0%B1%D0%B0%D1%80%D0%B5%D0%B2-%D0%B0%D0%BB%D0%B5%D0%BA%D1%81%D0%B0%D0%BD%D0%B4%D1%80.gif');
            background-size: cover;
            background-position: center;
            border: 4px solid #ff4757; /* Яркая граница */
            border-radius: 15px; /* Скругленные углы */
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.2); /* Тень для глубины */
            transition: transform 0.3s; /* Плавный переход при наведении */
        }

        /* Эффект при наведении на контейнер */
        .gif-container:hover {
            transform: scale(1.05); /* Увеличение при наведении */
        }

        /* Стиль для текста */
        .message {
            font-size: 28px; /* Увеличенный размер шрифта */
            margin-bottom: 20px; /* Отступ снизу */
            text-align: center; /* Центрирование текста */
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.5); /* Тень для текста */
        }

        /* Анимация мигания фона */
        @keyframes flashBackground {
            0% {
                background-color: rgb(230, 197, 155);
            }
            50% {
                background-color: rgb(233, 192, 105);
            }
            100% {
                background-color: rgb(230, 197, 155);
            }
        }
    </style>
</head>
<body>
    <div class="message">Я бы все отдал за эти пельмени!!</div>
    <div class="gif-container"></div>
</body>
</html>