<script setup lang="ts">
// @ts-expect-error avoid lint error
import markdownParser from '@nuxt/content/transformers/markdown'

const markdown = `

## hello World

Hello this is markdown
`

const parsedMarkdown = await markdownParser.parse('helloWorld', markdown)

</script>

<template>
  Markdown manually rendered 👇 <br /> 
  <pre>
    <ContentRendererMarkdown :value="parsedMarkdown" />
  </pre>
</template>
