<template>
  <!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <title>BookMark App</title>
  </head>
  <body>
    <header>Bookmark App</header>
        <bookmarkItem :items="bookmarkList" @delete-item="deleteItem" />


  </body>
</html>

</template>

<script>
import bookmarkItem from "@/components/bookmarkItem"
export default {
  data() {
    return {
       bookmarkList: [{id: 1, name: 'Bookmark 1',description:"Açıklama", link:"https://www.google.com/"},
       {id: 2, name: 'Bookmark 2',description:"Açıklama", link:"https://www.yandex.com/"},
       {id: 3, name: 'Bookmark 3',description:"Açıklama", link:"https://www.twitter.com/"},
       {id: 4, name: 'Bookmark 4',description:"Açıklama", link:"https://www.youtube.com/"},
       {id: 4, name: 'Bookmark 4',description:"Açıklama", link:"https://www.youtube.com/"}],
    }
  },
  methods: {
    deleteItem(id){
      this.bookmarkList=this.bookmarkList.filter(x => x.id !== id);
    }
  },
  components : {
    // "pogaca" : appCounter,
     bookmarkItem
  }
}
</script>


<style >

@import 'assets/style.css';
</style>
