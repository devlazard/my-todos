<template>
    <v-card class="todo pt-1 mb-2" :class="(todo.done)?'done':'not-done'" flat dark>
        <v-layout>
            <v-list dense style="width: 100%">
                <v-list-tile>
                    <v-list-tile-action>
                        <v-checkbox v-model="todo.done"></v-checkbox>
                    </v-list-tile-action>
                    <v-list-tile-content class="pt-4">
                        <span @click="todo.editable = true" @keyup.enter="todo.editable = false;" style="width: 100%;">
                            <v-text-field
                                @blur="todo.editable = false"
                                @change="$emit('savetodos')"
                                label="What needs to be done?"
                                style="width: 100%;"
                                solo flat
                                v-model="todo.text"
                                :disabled="!todo.editable"
                                color="white"
                            ></v-text-field>
                        </span>
                    </v-list-tile-content>
                    <v-list-tile-action right>
                        <v-btn flat small @click="$emit('deltodo', index)">
                            <v-icon>fa-3x fa-times</v-icon>
                        </v-btn>
                    </v-list-tile-action>
                </v-list-tile>
            </v-list>
        </v-layout>
    </v-card>
</template>
<script>
export default {
    props: {
        todo: {},
        index: Number
    }
}
</script>

<style scoped>
.todo {
    border-left: 4px solid var(--border-color,orangle);
}
.done {
    --border-color: black;
}
.not-done {
    --border-color: white;
}
</style>
