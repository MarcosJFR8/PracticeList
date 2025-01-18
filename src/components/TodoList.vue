<script setup lang="ts">
    import { ref } from 'vue';
    import type { Ref } from 'vue';
    import ListItem from './ListItem.vue';
    type Item = {
        title: string;
        checked?: boolean;
    }
    const GroupsItems: Ref<Item[]> = ref([
        { title: 'Visitar a la abuela', checked: false },
        { title: 'Hacer la compra', checked: false },
        { title: 'Estudiar Vue 3', checked: false },
    ]);

    const updateItem = (element : Item): void => {
        const updatedItem = findItemList(element);
        if (updatedItem) {
            tooggleItemCheck(updatedItem);
        }
    }

    const findItemList = (element : Item): Item | undefined => {
        return GroupsItems.value.find((elementItemInList) => elementItemInList.title === element.title);
    }

    const tooggleItemCheck = (element : Item): void => {
        element.checked = !element.checked;
    }
</script>

<template>
    <ul>
        <li :key="index" v-for="(element, index) in GroupsItems">
            <ListItem :isChecked="element.checked" @updateItem="updateItem(element)">
                {{ element.title }}
            </ListItem>
            
        </li> 
    </ul>
</template>

<style scoped>
    ul {
        list-style: none;
        padding: 0;
    }
</style>