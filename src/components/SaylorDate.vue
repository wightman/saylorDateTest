<template>
    <v-container>
        <v-row>
            <v-column class="col-md-2">
                <v-select
                dense light
                v-model="year"
                :items="years"
                label="Year"
                v-on:blur="$emit('dateString',{year, month, day})"
                ></v-select>

                <v-select
                dense light
                v-model="month"
                :items="months"
                label="Month"
                v-on:blur="$emit('dateString',{year, month, day})"
                ></v-select>

                <v-select
                dense light
                v-model="day"
                :items="days"
                label="Day"
                v-on:blur="$emit('dateString',{year, month, day})"
                ></v-select>
                <p>{{year}}-{{month}}-{{day}}</p>
            </v-column>
        </v-row>
    </v-container>
</template>
<script>
    export default {
        data: () => ({
            year: '  ',
            month: '  ',
            day: '  ',
            years: ['  ','1600', '1601', '1602', '1603', '1604', '1605', '1606',
                '1607','1608', '1609', '1610', '1611', '1612', '1613', '1614', 
                '1615','1616', '1617', '1618', '1619', '1620', '1621', '1622', '1623', '1624', '1625'],
            months: ['  ', '1', '2', '3', '4', '5','6','7','8', '9',
                    '10', '11', '12'],
            days:   ['  ', '1','2','3','4','5','6','7','8', '9',
                    '10', '11', '12','13','14','15','16','17','18','19',
                    '20', '21', '22','23','24','25','26','27','28','29',
                '30','31'],
        }),
    }
</script>
