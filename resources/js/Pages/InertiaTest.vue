<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue' //　リアクティブ

const newTitle = ref("")
const newContent = ref("")
</script>

<template>
  <div class="link-group">
    Inertiaテストです。 <br>
    <a href="/">aタグ経由でうｓ</a> <br>
    <Link href="/">LINK経由です </Link><br>
    <Link :href="route('inertia.index')">namae付きルートの確認です。</Link> <br>
    <Link :href="route('inertia.show', {id: 236})">button</Link>
  </div>

  <div class="mb-8"></div>

  <div class="input-group">
    <input type="text" name="newtitle" v-model="newTitle">{{ newTitle }} <br>
    <input type="text" name="newContent" v-model="newContent"> {{ newContent }} <br>
    <Link as="button" method="post" :href="route('inertia.store')" 
    :data="{
      title: newTitle,
      content: newContent
    }">保存テスト</Link>
  </div>

</template>