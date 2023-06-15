<template>
    <div class="item-task d-flex align-items-start border-bottom pt-3 pb-4">
        <input type="checkbox" :name="`status-${index}`" :id="`task-${index}`" class="me-2 mt-2" v-model="task.isDone" />
        <div class="d-flex flex-column">
            <div class="title-task mb-1" :class="{ 'text-decoration-line-through': task.isDone }">{{ task.title }}</div>
            <div class="description-task small text-muted">{{ task.description }}</div>
            <a href="#" class="add-button" @click="deleteTask(index)">Delete</a>
        </div>
    </div>
</template>
  
<script>
export default {
    props: {
        task: Object,
        index: Number
    },
    methods: {
        deleteTask(index) {
            this.$emit('delete-task', index);
        }
    }
}
</script>    