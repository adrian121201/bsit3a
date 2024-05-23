<template>
    <v-card>
        <v-card-title>
            Students List Page
            <v-spacer></v-spacer>
            <v-text-field v-model="search" append-icon="mdi-magnify" label="Search" single-line
                hide-details></v-text-field>
        </v-card-title>
        <v-data-table :headers="headers" :items="StudentData" :search="search">
            <template slot="item.actions" slot-scope="{item}">
                <v-btn color="green accent-4"> DELETE</v-btn>
                <v-btn color="red accent-4"> EDIT</v-btn>
            </template>
        </v-data-table>

    </v-card>
</template>
<script>
export default {
    data() {
        return {
            search: '',
            headers: [
                {
                    text: 'Student Number',
                    align: 'start',
                    sortable: false,
                    value: 'attributes.Student_no',
                },
                { text: 'First Name', value: 'attributes.First_name' },
                { text: 'Last Name', value: 'attributes.Last_name' },
                { text: 'Middle Initial', value: 'attributes.Middle_initial' },
                { text: 'Course', value: 'attributes.Course' },
                { text: 'Section', value: 'attributes.Section' },
                { text: 'Year', value: 'attributes.Year' },
                { text: '', value: "actions" }
            ],
            StudentData: [



            ],
        };
    },

    // All function

    methods: {

        getStudentList() {

             this.$axios.get("http://localhost:1337/api/student-lists")
             .then(response => {
                console.log("Success");
                console.log(response.data.data);
                this.StudentData = response.data.data
             })
             .catch(error =>{
                console.log("Error!");
             })

        }

    },


    mounted() {
                   
        this.getStudentList();
    }
};
</script>
