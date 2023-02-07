<script>
export default {
    name: 'App',

    data() {

        return {
            firstName: 'Alessio',
            lastName: 'Vietri',
            counter: 0
        };

    },

    methods: {

        getFullName() {

            console.log('CHIAMATO METHOD');

            let fullName = '';

            fullName += this.firstName;
            fullName += ' ';
            fullName += this.lastName;

            return fullName;

        }

    },

    computed: {

        fullName() {

            console.log('CHIAMATA COMPUTED');

            let fullName = '';

            fullName += this.firstName;
            fullName += ' ';
            fullName += this.lastName;

            return fullName;

        }

    }
}
</script>

<template>

    <div>
        <label>firstName</label>
        <input type="text" v-model="firstName">
    </div>

    <div>
        <label>lastName</label>
        <input type="text" v-model="lastName">
    </div>

    <div>
        <h3>
            Il click su questi 2 bottoni fa ri-eseguire il method, ma non fa ricalcolare la computed property
        </h3>
        <button @click="counter--">
            -
        </button>
        {{ counter }}
        <button @click="counter++">
            +
        </button>
    </div>
    
    <div id="methods">
        <h2>
            Full Name restituito da un metodo
        </h2>
        <p>
            "{{ getFullName() }}"
        </p>
    </div>
    
    <div id="computed">
        <h2>
            Full Name restituito da una computed property
        </h2>
        <p>
            "{{ fullName }}"
        </p>
    </div>

</template>

<style scoped>

</style>
