<template>
<div class="container">
<div v-for="item in items" :key="item.id" class="bookmark--app--container">
     <div class="bookmark-item">
          <div class="header">
            <h3>{{item.name}}</h3>
            <button @click="deleteItem(item.id)"  class="btn-sm btn-danger">Kaydı Sil</button>
          </div>
          <p class="mt-20 mb-20">{{item.description}}</p>
          <button @click="navigatetoUrl(item.link)" class="btn-primary btn-sm">Göster</button>
        </div>
      </div>
      </div>
</template>

<script>
export default {
    props: {
    items: {
      type: Array,
      required: true,
      default: () => []
    }
  },
  methods: {
      navigatetoUrl(link) {
          location.href=link;
      },
      deleteItem(id){
          this.$emit("delete-item", id);
      }
  },
}
</script>