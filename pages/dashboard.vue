<template>
    <v-card>
        <v-card-title>
            Students
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
                    text: 'ID',
                    align: 'start',
                    sortable: false,
                    value: 'StudentID',
                },
                { text: 'First Name', value: 'First_Name' },
                { text: 'Last Name', value: 'Last_Name' },
                { text: 'Middle Initial', value: 'Middle_Initial' },
                { text: 'Course', value: 'Course' },
                { text: 'Year', value: 'Year' },
                { text: '', value: "actions" }
            ],
            StudentData: [
                {

                    First_Name: 'Adrian',
                    StudentID: '21-00034',
                    Last_Name: 'Icalina',
                    Middle_Initial: 'A',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Rolly',
                    StudentID: '21-00035',
                    Last_Name: 'Arellano',
                    Middle_Initial: 'A',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Charliemane',
                    StudentID: '21-00035',
                    Last_Name: 'Delos Santos',
                    Middle_Initial: 'B',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Jerdy',
                    StudentID: '21-00036',
                    Last_Name: 'Delos Esguerra',
                    Middle_Initial: 'C',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Franz Gerald',
                    StudentID: '21-00037',
                    Last_Name: 'Anasco',
                    Middle_Initial: 'D',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Jean Brandon',
                    StudentID: '21-00038',
                    Last_Name: 'Calilung',
                    Middle_Initial: 'E',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Billy Joe',
                    StudentID: '21-00039',
                    Last_Name: 'Racines',
                    Middle_Initial: 'F',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Christian',
                    StudentID: '21-00040',
                    Last_Name: 'Salvador',
                    Middle_Initial: 'G',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Joanne',
                    StudentID: '21-00041',
                    Last_Name: 'Tolentino',
                    Middle_Initial: 'H',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Marc Ghio',
                    StudentID: '21-00042',
                    Last_Name: 'Pineda',
                    Middle_Initial: 'I',
                    Course: 'BSIT',
                    Year: '3',
                },
                {

                    First_Name: 'Mike Johnces',
                    StudentID: '21-00043',
                    Last_Name: 'Nogoy',
                    Middle_Initial: 'J',
                    Course: 'BSIT',
                    Year: '3',
                },

            ],
        }
    },
}
</script>
