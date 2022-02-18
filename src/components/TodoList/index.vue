<script  lang="ts"> 
    import { computed, defineComponent, nextTick } from "vue";

    export default defineComponent({
        props: {
            count: Number,
            books: [String] ,
        },
        data() {
            return {
                firstName: 'John',
                lastName: 'Doe'
            }
        },
        computed: {
            fullName: {
            // getter
            get():String {
                return this.firstName + ' ' + this.lastName
            },
            // setter
            set(newValue: String): void {
                // Note: we are using destructuring assignment syntax here.
                [this.firstName, this.lastName] = newValue.split(' ')
            }
            }
        }

        
    });

</script>

<template>
    <div>
        <p>Have a book</p>
        <p>{{fullName}}</p>
        <!-- <button @click="count++" >{{count}}</button> -->
    </div>
</template>