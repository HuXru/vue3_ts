<template>
    <div class="post-list">
        <article v-for="post in list" :key="post.id" class="card mb-3">
            <div class="card-body">
                <h4>{{ post.title }}</h4>
                <div class="row my-3 align-items-center">
                    <div class="col-3" v-if="post.image">
                        <img :src="post.image" :alt="post.title" />
                    </div>
                    <p :class="{'col-9': post.image}">{{ post.content }}</p>
                </div>
                <span class="text-muted">{{post.createdAt}}</span>
            </div>
        </article>
    </div>
</template>

<script lang="ts">
import { defineComponent, PropType } from 'vue'
import { PostProps } from '../testData'

export default defineComponent({
    props: {
        list: {
            require: true,
            type: Array as PropType<PostProps[]>
        }
    }
})
</script>
