<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" :class="[task.reminder ? 'reminder' : '', 'task']">
        <h3>
            {{ task.text }}
                <img src="./delred.svg"  @click="$emit('delete-task', task.id)"
                class="delete-icon" width="15" height="15" alt="Button Image">
            <img>
        </h3>
        <p>{{ task.day }}</p>
    </div> 
</template>

<script>
export default {
    name: 'Task',
    props: {
        task: Object,
    },
}
</script>

<style scoped>

.delete-icon {
    position: absolute;
    top: 0;
    right: 0;
}
.task {
    background: #f4f4f4;
    margin: 5px;
    padding: 10px 20px;
    cursor: pointer;
    border-radius: 7px;
    color: rgb(107, 107, 107);
}
p {
    margin-left: 3px;
}
.task.reminder {
    border: 3.5px solid green;
    border-radius: 5px;
    color: black;
}
.task h3 {
    display: flex;
    align-items: center;
    justify-content: space-between;
    color: black;
}
</style>