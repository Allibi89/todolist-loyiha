<script>
export default {
    data() {
        return {
            newTask: '',
            tasks: []
        };
    },
    methods: {
        addTask() {
            if (this.newTask.trim() !== '') {
                this.tasks.unshift(this.newTask);
                this.newTask = '';
            }
        },
        removeTask(index) {
            this.tasks.splice(index, 1);
        }
    }
};
</script>

<template>
    <div class="row  justify-content-md-center">
        <div class="col-md-auto" style="width: 500px">
            <div class="card">
                <div class="card-body">
                    <h5 class="card-title">
                        <div class="row">
                            <div class="col-9">
                                <input  class="form-control" v-model="newTask" @keyup.enter="addTask" placeholder="you text">
                            </div>
                            <div class="col-2">
                                <button @click="addTask" class="btn btn-primary mb-3">Add</button>
                            </div>
                        </div>
                    </h5>
                    <p class="card-text">
                        <ul class="list-group">
                            <li class="list-group-item mb-2 list-group-item-success" v-for="(task, index) in tasks" :key="index">
                                {{ task }}
                            <button @click="removeTask(index)" class="btn btn-primary float-end">
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-trash3-fill" viewBox="0 0 16 16">
                                    <path d="M11 1.5v1h3.5a.5.5 0 0 1 0 1h-.538l-.853 10.66A2 2 0 0 1 11.115 16h-6.23a2 2 0 0 1-1.994-1.84L2.038 3.5H1.5a.5.5 0 0 1 0-1H5v-1A1.5 1.5 0 0 1 6.5 0h3A1.5 1.5 0 0 1 11 1.5m-5 0v1h4v-1a.5.5 0 0 0-.5-.5h-3a.5.5 0 0 0-.5.5M4.5 5.029l.5 8.5a.5.5 0 1 0 .998-.06l-.5-8.5a.5.5 0 1 0-.998.06m6.53-.528a.5.5 0 0 0-.528.47l-.5 8.5a.5.5 0 0 0 .998.058l.5-8.5a.5.5 0 0 0-.47-.528M8 4.5a.5.5 0 0 0-.5.5v8.5a.5.5 0 0 0 1 0V5a.5.5 0 0 0-.5-.5"/>
                                </svg>
                            </button>
                            </li>

                        </ul>

                    </p>

                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>

</style>