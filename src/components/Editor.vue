<template>
  <div>
    <textarea v-model="content" placeholder="Add Your Article here"></textarea>
<!--    <input v-model="content"/>-->
    <markdown-it-vue class="md-body" :content="content" :options="options" />
  </div>
</template>

<script>
import MarkdownItVue from 'markdown-it-vue'
import 'markdown-it-vue/dist/markdown-it-vue.css'
export default {
  name: "Editor",
  components: {
    MarkdownItVue
  },
  data() {
    return {
      options: {
        markdownIt: {
          linkify: true
        },
        linkAttributes: {
          attrs: {
            target: '_blank',
            rel: 'noopener'
          }
        }
      },
      // editor's content
      content: `# Enter your notes here.`,
    };
  },
};
</script>

<style scoped></style>
