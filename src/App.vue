<template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :title="chartTitle"
    :primaryYAxis="chartPrimaryYAxis">
      <e-series-collection>
        <e-series type="Line" :dataSource="chartData" xName="date" yName="value" 
        :marker="chartMarker">
        </e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, LineSeries, DateTime } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [LineSeries, DateTime]},
  data() {
    return {
      chartMarker : {
        visible : true,
        height : 7,
        width : 7
      },
      chartPrimaryYAxis : { title : 'Temperature'},
      chartTitle : 'Weather Statistics',
      chartPrimaryXAxis : {
        valueType : 'DateTime',
        title : 'Date',
        edgeLabelPlacement : 'Shift',
        labelFormat : 'yyy MMM',
        minimum : new Date(2016, 12, 31),
        maximum : new Date(2022, 12, 1),
        interval : 6,
        intervalType : 'Months',
        rangePadding : 'None'
      },
      chartData : [
       { date : new Date(2017, 3, 1), value : 6.3 },
       { date : new Date(2017, 5, 1), value : 13.3 },
       { date : new Date(2018, 7, 1), value : 8.0 },
       { date : new Date(2018, 4, 1), value : 17.3 },
       { date : new Date(2019, 5, 1), value : 19.8 },
       { date : new Date(2019, 9, 1), value : 5.1 },
       { date : new Date(2020, 2, 1), value : 10.1 },
       { date : new Date(2020, 7, 1), value : 9.6 },
       { date : new Date(2021, 5, 1), value : 18.1 },
       { date : new Date(2021, 12, 15), value : 8.2 }
      ]
    };
  }
}
</script>






<!-- <template>
  <div id="app">
    <ejs-chart :primaryXAxis="chartPrimaryXAxis" :primaryYAxis="chartPrimaryYAxis"> 
      <e-series-collection>
        <e-series type="Column" :dataSource="chartData" xName="date" yName="profit">
        </e-series>
      </e-series-collection>   
    </ejs-chart>
  </div>
</template>

<script>
import Vue from "vue";
import { ChartPlugin, LineSeries, DateTime, ColumnSeries,
DateTimeCategory } from '@syncfusion/ej2-vue-charts';
Vue.use(ChartPlugin);

export default {
  provide : {chart : [LineSeries, DateTime, ColumnSeries, DateTimeCategory]},
  data() {
    return {
      chartPrimaryXAxis : {
        title : 'Business Days',
        valueType : 'DateTimeCategory'
      },
      chartPrimaryYAxis : {
        title: 'Profit'
      },
      chartData : [
         { date : new Date(2020, 12, 21), profit : 21 },
         { date : new Date(2020, 12, 22), profit :  24},
         { date : new Date(2020, 12, 24), profit : 25 },
         { date : new Date(2020, 12, 28), profit : 70 },
         { date : new Date(2021, 1, 4), profit : 82 },
         { date : new Date(2021, 1, 6), profit : 53 },
         { date : new Date(2021, 1, 8), profit : 45 },
         { date : new Date(2021, 1, 11), profit : 60 }
      ]
    };
  }
}
</script>
 -->
