<script setup>
const state = reactive({
  tree: [],
});

// const { data: comments } = await useFetch(
//   'https://www.klerk.ru/yindex.php/v3/event/rubrics'
// );
// const { data: comments } = await useAsyncData('comments', () =>
//   $fetch('https://www.klerk.ru/yindex.php/v3/event/rubrics', {
//     mode: 'no-cors',
//   })
// );

const { data: comments } = await useFetch(
  'https://www.klerk.ru/yindex.php/v3/event/rubrics',
  {
    // pick: ['title']
    mode: 'no-cors',
  }
);
console.log('comments', comments);

// async function get() {
//   // let url ='https://api.github.com/repos/javascript-tutorial/en.javascript.info/commits';
//   let url = 'https://www.klerk.ru/yindex.php/v3/event/rubrics ';
//   let response = await fetch(url, {
//     method: 'GET',
//     // withCredentials: true,
//     // crossorigin: true,
//     mode: 'no-cors',
//   });
//   let commits = await response.json(); // читаем ответ в формате JSON
//   // state.tree = response;
//   console.log('commits', commits);
// }
// onMounted(() => {
//   get();
//   // console.log(state.tree);
// });
</script>

<template>
  <pre class="br">{{ comments }}</pre>
</template>

<style>
.br {
  border: 1px solid red;
  width: 100px;
  height: 100px;
}
</style>
