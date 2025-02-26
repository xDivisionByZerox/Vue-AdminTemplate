<template>
    <div>
        <slot/>
    </div>
</template>

<script>
    // jvectormap
    import '@/libs/default/plugins/jquery-jvectormap-2.0.5/jquery-jvectormap-2.0.5.css'
    import '@/libs/default/plugins/jquery-jvectormap-2.0.5/jquery-jvectormap-2.0.5.min.js'
    // jvectormap - world
    import '@/libs/default/plugins/jquery-jvectormap-2.0.5/jquery-jvectormap-world-mill.js'

    export default {
        mounted: function() {
            'use strict';

            /* ChartJS
             * -------
             * Here we will create a few charts using ChartJS
             */

            //-----------------------
            //- MONTHLY SALES CHART -
            //-----------------------

            // Get context with jQuery - using jQuery's .get() method.
            var salesChartCanvas = $('#salesChart').get(0).getContext('2d');
            // This will get the first returned node in the jQuery collection.
            var salesChartData = {
                labels  : ['January', 'February', 'March', 'April', 'May', 'June', 'July'],
                datasets: [
                    {
                        label               : 'Digital Goods',
                        backgroundColor     : 'rgba(60,141,188,0.9)',
                        borderColor         : 'rgba(60,141,188,0.8)',
                        pointRadius          : false,
                        pointColor          : '#3b8bba',
                        pointStrokeColor    : 'rgba(60,141,188,1)',
                        pointHighlightFill  : '#fff',
                        pointHighlightStroke: 'rgba(60,141,188,1)',
                        data                : [28, 48, 40, 19, 86, 27, 90]
                    },
                    {
                        label               : 'Electronics',
                        backgroundColor     : 'rgba(210, 214, 222, 1)',
                        borderColor         : 'rgba(210, 214, 222, 1)',
                        pointRadius         : false,
                        pointColor          : 'rgba(210, 214, 222, 1)',
                        pointStrokeColor    : '#c1c7d1',
                        pointHighlightFill  : '#fff',
                        pointHighlightStroke: 'rgba(220,220,220,1)',
                        data                : [65, 59, 80, 81, 56, 55, 40]
                    },
                ]
            }

            var salesChartOptions = {
                maintainAspectRatio : false,
                responsive : true,
                legend: {
                    display: false
                },
                scales: {
                    xAxes: [{
                        gridLines : {
                            display : false,
                        }
                    }],
                    yAxes: [{
                        gridLines : {
                            display : false,
                        }
                    }]
                }
            }

            //Create the line chart
            var salesChart = new Chart(salesChartCanvas, {
                type: 'line',
                data: salesChartData,
                options: salesChartOptions
            });
            salesChart.render();
            //---------------------------
            //- END MONTHLY SALES CHART -
            //---------------------------

            //-------------
            //- PIE CHART -
            //-------------
            // Get context with jQuery - using jQuery's .get() method.
            var pieChartCanvas = $('#pieChart').get(0).getContext('2d');
            var PieData        = {
                labels: ["Chrome", "IE", "FireFox", "Safari", "Opera", "Navigator"],
                datasets: [
                    {
                        label: " users ",
                        backgroundColor: ["#f56954", "#00a65a","#f39c12","#00c0ef","#3c8dbc", "#d2d6de"],
                        data: [700,500,400,600,300,100]
                    }
                ]
            };
            var pieOptions     = {
                //Boolean - Whether we should show a stroke on each segment
                //segmentShowStroke    : true,
                //String - The colour of each segment stroke
                //segmentStrokeColor   : '#fff',
                //Number - The width of each segment stroke
                //segmentStrokeWidth   : 1,
                //Number - The percentage of the chart that we cut out of the middle
                //percentageInnerCutout: 50, // This is 0 for Pie charts
                //Number - Amount of animation steps
                //animationSteps       : 100,
                //String - Animation easing effect
                //animationEasing      : 'easeOutBounce',
                //Boolean - Whether we animate the rotation of the Doughnut
                //animateRotate        : true,
                //Boolean - Whether we animate scaling the Doughnut from the centre
                //animateScale         : false,
                //Boolean - whether to make the chart responsive to window resizing
                //responsive           : true,
                //String - A legend template
                //legendTemplate       : '<ul class="<%=name.toLowerCase()%>-legend"><% for (var i=0; i<segments.length; i++){%><li><span style="background-color:<%=segments[i].fillColor%>"></span><%if(segments[i].label){%><%=segments[i].label%><%}%></li><%}%></ul>',
                //String - A tooltip template
                //tooltipTemplate      : '<%=data %> <%=labels%> users'
                // Boolean - whether to maintain the starting aspect ratio or not when responsive, if set to false, will take up entire container
                maintainAspectRatio  : false,
                tooltips           : {
                    enabled: true,
                    mode     : 'index',
                    intersect: true,

                },
                legend             : {
                    display: false
                }
            };
            //Create pie or douhnut chart
            // You can switch between pie and douhnut using the method below.
            new Chart(pieChartCanvas, {
                type: 'doughnut',
                data: PieData,
                options: pieOptions
            });
            //-----------------
            //- END PIE CHART -
            //-----------------


           /* SPARKLINE CHARTS
            * ----------------
            * Create a inline charts with spark line
            */

            //-----------------
            //- SPARKLINE BAR -
            //-----------------

            $('.sparkbar').each(function () {
                var $this = $(this)
                $this.sparkline('html', {
                    type    : 'bar',
                    height  : $this.data('height') ? $this.data('height') : '30',
                    barColor: $this.data('color')
                })
            })

            //-----------------
            //- SPARKLINE PIE -
            //-----------------
            $('.sparkpie').each(function () {
                var $this = $(this)
                $this.sparkline('html', {
                    type       : 'pie',
                    height     : $this.data('height') ? $this.data('height') : '90',
                    sliceColors: $this.data('color')
                })
            })

            //------------------
            //- SPARKLINE LINE -
            //------------------
            $('.sparkline').each(function () {
                var $this = $(this)
                $this.sparkline('html', {
                    type     : 'line',
                    height   : $this.data('height') ? $this.data('height') : '90',
                    width    : '100%',
                    lineColor: $this.data('linecolor'),
                    fillColor: $this.data('fillcolor'),
                    spotColor: $this.data('spotcolor')
                })
            })

            /* jVector Maps
             * ------------
             * Create a world map with markers

            */
            var mapObject = {
                map: 'world_mill',
                scaleColors: ['#C8EEFF', '#0071A4'],
                normalizeFunction: 'polynomial',
                hoverOpacity: 0.7,
                hoverColor: false,
                markerStyle: {
                    initial: {
                        fill: '#F8E23B',
                        stroke: '#383f47'
                    }
                },
                backgroundColor: '#383f47',
                markers: [
                    {latLng: [41.90, 12.45], name: 'Vatican City'},
                    {latLng: [43.73, 7.41], name: 'Monaco'},
                    {latLng: [-0.52, 166.93], name: 'Nauru'},
                    {latLng: [-8.51, 179.21], name: 'Tuvalu'},
                    {latLng: [43.93, 12.46], name: 'San Marino'},
                    {latLng: [47.14, 9.52], name: 'Liechtenstein'},
                    {latLng: [7.11, 171.06], name: 'Marshall Islands'},
                    {latLng: [17.3, -62.73], name: 'Saint Kitts and Nevis'},
                    {latLng: [3.2, 73.22], name: 'Maldives'},
                    {latLng: [35.88, 14.5], name: 'Malta'},
                    {latLng: [12.05, -61.75], name: 'Grenada'},
                    {latLng: [13.16, -61.23], name: 'Saint Vincent and the Grenadines'},
                    {latLng: [13.16, -59.55], name: 'Barbados'},
                    {latLng: [17.11, -61.85], name: 'Antigua and Barbuda'},
                    {latLng: [-4.61, 55.45], name: 'Seychelles'},
                    {latLng: [7.35, 134.46], name: 'Palau'},
                    {latLng: [42.5, 1.51], name: 'Andorra'},
                    {latLng: [14.01, -60.98], name: 'Saint Lucia'},
                    {latLng: [6.91, 158.18], name: 'Federated States of Micronesia'},
                    {latLng: [1.3, 103.8], name: 'Singapore'},
                    {latLng: [1.46, 173.03], name: 'Kiribati'},
                    {latLng: [-21.13, -175.2], name: 'Tonga'},
                    {latLng: [15.3, -61.38], name: 'Dominica'},
                    {latLng: [-20.2, 57.5], name: 'Mauritius'},
                    {latLng: [26.02, 50.55], name: 'Bahrain'},
                    {latLng: [0.33, 6.73], name: 'São Tomé and Príncipe'}
                ]
            };
            $('#world-map-markers').vectorMap( mapObject );
        },

        beforeDestroy () {
           //var mapObj = $('#world-map-markers').vectorMap('get','mapObject');
           $('#world-map-markers').remove();
        }
    }
</script>
