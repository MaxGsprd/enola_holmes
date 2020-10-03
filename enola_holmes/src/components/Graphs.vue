<template>
    <div class="charts">
        <div id="chart-wrapper">
            <chart :options="chartOptionsLine"></chart>
        </div>
        <hr>
    </div>
</template>

<script>
    export default {
        name: "Graphs",
        props: ["dataDates", "dataVal"], 
        data() {
            return {
                chartOptionsLine: {
                    xAxis: {
                        name: "dates",
                        data: this.dataDates,
                    },
                    yAxis: {
                        name: 'valeurs',
                        type: "value"
                    },
                    series: [
                        {
                            type: "line",
                            data: this.dataVal
                        }
                    ],
                    title: {
                        text: 'coucou',
                    },
                    color: ["#f03482"]
                },
            }
        }
    }
</script>

<style scoped>
    .charts {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: start;
        width: 900px;
        color: #fff;
    }
        #chart-wrapper {
        width: 100%;
        height: 400px;
        -webkit-box-shadow: 10px 16px 57px 1px rgba(89,84,89,1);
        -moz-box-shadow: 10px 16px 57px 1px rgba(89,84,89,1);
        box-shadow: 10px 16px 57px 1px rgba(89,84,89,1);
        }

    .echarts {
        width: 100%;
        height: 100%;
        background:#fff;
    }




</style>