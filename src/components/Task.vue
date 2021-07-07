<template>
    <div @dblclick="$emit('toggle-reminder', task.id)" class="card [ task.reminder ? 'text-success' : '', '']" style="margin:5px;">
        <h3 > {{ task.text }} 
            <i @click="$emit('delete-task', task.id)" class="fas fa-times text-danger"></i>
        </h3>  
        <p> {{ task.day}}</p>
    </div> 
</template>

<script>

export default{
    name: 'Task',
    props: {
        task: Object
        },
    }
</script>
