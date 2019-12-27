<template>
    <v-card
        class="todo pt-1 mb-2"
        :class="(todo.done)?'done':'not-done'"
        flat dark
        style="border-left: 7px solid #2196f3"
        >
        <v-layout style="width: 100%">
            <v-list dense style="width: 100%;">
                <v-list-tile>
                    <v-list-tile-action left style="max-width:10px !important;">
                        <span class="hoverResetAll" left @click="$emit('delalltodos')">
                            <v-icon color="blue">fa-trash</v-icon>
                        </span>
                    </v-list-tile-action>
                    <v-list-tile-content class="pt-4">
                        <span style="width: 100%;" @keyup.enter="$emit('addtodo');todo.text=''">
                            <v-text-field
                                color="white"
                                style="width: 100%;"
                                solo flat
                                v-model="todo.text"
                                label="What needs to be done?"
                            ></v-text-field>
                        </span>
                    </v-list-tile-content>
                    <v-list-tile-action>
                        <v-btn flat small @click="$emit('addtodo');todo.text=''">
                            <v-icon color="blue">fa-plus</v-icon>
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
        todo: {
            done: Boolean,
            text: String,
            editable: Boolean
        }
    }
}
</script>
<style scoped>
.hoverResetAll{
    transition: 1000ms all;
}
.hoverResetAll:hover{
    transform: scale(1.1);
    /* color: #4e4e4e; */
}
</style>
