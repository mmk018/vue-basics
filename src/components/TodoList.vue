<template>
    <div>
        <ul>
            {{todos}}
            <TodoItem></TodoItem>
        </ul>
    </div>
</template>

<script>
import TodoItem from '@/components/TodoItem'
export default {
 props: ['todos'],   
 components: {
     TodoItem
 }
}
</script>