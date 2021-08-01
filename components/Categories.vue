<template>
<section class="text-gray-600 body-font">
  <div class="container px-5 py-24 mx-auto">
    <!--
    <div class="flex flex-wrap -m-4">

      <div class="lg:w-1/4 md:w-1/2 p-4 w-full" v-for="item in categories">
        <a class="block relative h-48 rounded overflow-hidden">
          <img alt="ecommerce" class="object-cover object-center w-full h-full block" v-bind:src=item.pict_url />
        </a>
        <div class="mt-4">
          <h3 class="text-gray-500 text-xs tracking-widest title-font mb-1">CATEGORY</h3>
          <h2 class="text-gray-900 title-font text-lg font-medium">{{ item.title }}</h2>
          <p class="mt-1">{{ item.price }}</p>
        </div>      
      </div>

    </div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatibus quia, nulla! Maiores et perferendis eaque, exercitationem praesentium nihil.
    -->
    <div class="container px-5 py-24 mx-auto">
      <div class="flex flex-wrap -m-4">
        <div class="lg:w-1/4 md:w-1/2 p-4 w-full"  v-for="category in categories">
          <div class="max-w-sm rounded overflow-hidden shadow-lg hover:bg-gray-50 hover:shadow-md" @click="selectCategory(category.categoryId)">
            <img class="w-full" v-bind:src=category.pictUrl alt="dummy image">
            <div class="px-6 py-4">
              <div class="font-bold text-xl mb-2">{{ category.title }}</div>
              <p class="text-gray-700 text-base">{{ category.detail }}</p>
            </div>
            <div class="px-6 pt-4 pb-2">
              <span class="inline-block bg-gray-200 rounded-full px-3 py-1 text-sm font-semibold text-gray-700 mr-2 mb-2" v-for="tag in category.tags">{{ tag }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>
</template>

<script>
export default {
  methods:{
    selectCategory: function(categoryId){
      this.$router.push('/category/' + categoryId);
    }
  },
  computed: {
    categories: function() {
      // パスからカテゴリIDを取得する。このカテゴリのサブカテゴリを取得して表示する。
      let parentCategoryId = this.$route.params.id;

      var arr = [];
      let catDepth = 0;

      // パスでカテゴリが指定されていない場合、トップカテゴリを取得する。
      if (parentCategoryId != undefined) {          
          let vals = parentCategoryId.split("-");
          catDepth = vals[1] + vals[2];
      }

      // サブカテゴリを取得して、画面表示用のパラメータを設定する。
      for(let i = 0; i < 10; i++){
        let catNum = i + 1;
        let categoryId = 'cat-' + catDepth + '-' + catNum;
        let pictPre = 420 + i;
        let pictPost = 260 + i;
        let price = 16 + i;
        let tags = [];

        for(let j = 0; j < 3; j++){
          tags.push('tag-' + i + '-' + j);
        }
        
        let cat = {
          depth: catDepth,
          categoryId: categoryId,
          title: 'Category ' + categoryId,
          pictUrl: 'https://dummyimage.com/' + pictPre + 'x' + pictPost,
          detail: 'This is category ' + categoryId + '. This price is $' +  price,
          tags: tags,
        }
        arr.push(cat);
      }
      return arr;
    }
  }
}
</script>

<style>
</style>
