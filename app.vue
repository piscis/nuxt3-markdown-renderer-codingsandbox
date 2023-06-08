<script setup lang="ts">
// @ts-expect-error avoid lint error
import markdownParser from '@nuxt/content/transformers/markdown'

export interface MarkdownRenderProps {
  md?: string
  cid?: string
}

const markdownMarkUp = `

## hello World


Hello this is markdown
`

const props = withDefaults(defineProps<MarkdownRenderProps>(), { md: '', cid: 'helloWorld' })
const parsedMarkdown = await markdownParser.parse(props.cid, markdownMarkUp)

</script>

<template>
      <ContentRendererMarkdown :value="parsedMarkdown" />
</template>
