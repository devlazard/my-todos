<template>
    <v-card
        class="todo pt-1 mb-2"
        :class="(todo.done)?'done':'not-done'"
        flat dark
        style="border-left: 4px solid orange"
        >
        <v-layout style="width: 100%">
            <v-list dense style="width: 100%;">
                <v-list-tile>
                    <v-list-tile-action left style="max-width:10px !important;">
                        <span class="hoverResetAll" left @click="$emit('delalltodos')">
                            <v-icon color="orange">fa-trash-alt</v-icon>
                        </span>
                    </v-list-tile-action>
                    <v-list-tile-content class="pt-4">
                        <span style="width: 100%;" @keyup.enter="$emit('addtodo');todo.text=''">
                            <v-text-field
                                style="width: 100%;"
                                solo flat
                                v-model="todo.text"
                                label="What needs to be done?"
                                color="white"
                            ></v-text-field>
                        </span>
                    </v-list-tile-content>
                    <v-list-tile-action>
                        <v-btn flat small @click="$emit('addtodo');todo.text=''">
                            <v-icon color="orange">fa-plus</v-icon>
                        </v-btn>
                    </v-list-tile-action>
                </v-list-tile>
            </v-list>
        </v-layout>
    </v-card>
    <!-- <v-card
        class="todo pt-1 mb-2"
        :class="(todo.done)?'done':'not-done'"
        flat dark
        style="border-left: 4px solid white"
        >
        <v-list dense>
            <v-list-tile>
                <v-list-tile-action left style="max-width:10px !important;">
                    <span class="hoverResetAll" left @click="$emit('delalltodos')">
                        <v-icon>fa-trash-alt</v-icon>
                    </span>
                </v-list-tile-action>
                <v-list-tile-content class="pt-4">
                    <span style="width: 100%;" @keyup.enter="$emit('addtodo');todo.text=''">
                        <v-text-field
                            style="width: 100%;"
                            solo flat
                            v-model="todo.text"
                            label="What needs to be done?"
                            color="white"
                        ></v-text-field>
                    </span>
                </v-list-tile-content>
                <v-list-tile-action>
                    <v-btn flat small @click="$emit('addtodo');todo.text=''">
                        <v-icon>fa-plus</v-icon>
                    </v-btn>
                </v-list-tile-action>
            </v-list-tile>
        </v-list>
    </v-card> -->
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
    transition: 200ms all;
}
.hoverResetAll:hover{
    transform: scale(1.2);
}
</style>
