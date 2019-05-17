<script src="../pkgs/echarts.min.js"></script>
# The Exploration of Landscape of Chengdu

<html><body><p><font size="4" color="gray">
The state comes into existence, originating in the bare needs of life, and continuing in existence for the sake of a good life. 

-- The Politics Of Aristotle, by Aristotle
</font></p></body></html>

## Change in Times
### Overview of Economy
Chengdu, located in the southwest of China, has been recently acknowledged as one of the fastest growing
cities in China. In recent years, its reputation has changed from "Heavenly Land of Plenty " with hot pots
and giant pandas to one of the most important engines of economy and technology in China.


While it is clear that the economy has dramatically changed over time, the answer to exactly how the economy has changed is a little more nuanced. One aim of this set of visualizations is to answer the question of how Chengdu's economic landscape has changed from 2009 to 2017.


The total economic output of Chengdu has a considerable proportion in Sichuan Province, and this uneven allocation of resources within the region will be further visualized.
```chart
{
	settings: {
    width: '100%',
    height: '300px',
    border: '1px solid red'
  },
    title: {
        text: 'GDP Data'
    },
    tooltip : {
        trigger: 'axis',
        axisPointer: {
            type: 'cross',
            label: {
                backgroundColor: '#6a7985'
            }
        }
    },
    legend: {
        data:['Chengdu','Sichuan']
    },
    toolbox: {
        feature: {
            saveAsImage: {}
        }
    },
    grid: {
        left: '3%',
        right: '4%',
        bottom: '3%',
        containLabel: true
    },
    xAxis : [
        {
            type : 'category',
            boundaryGap : false,
            data : ['2009','2010','2011','2012','2013','2014','2015','2016','2017']
        }
    ],
    yAxis : [
        {
            type : 'value'
        }
    ],
    series : [
        {
            name:'Chengdu',
            type:'line',
            stack: '总量',
            areaStyle: {},
            data:[4503, 5551.3, 6854.58, 8138.9, 9108.89, 10056.59, 10801.16,12170.23,13889.39]
        },
        {
            name:'Sichuan',
            type:'line',
            stack: '总量',
            areaStyle: {},
            data:[14151.28, 17185.48, 21026.68, 23872.8, 26392.07, 28536.66, 30053.1,32934.54,36980.22]
        }
    ]
}

```

<br/>
```chart
{
"backgroundColor" : "#344b57",
"title": {
        "text": 'GDP Structure of Chengdu',
		x:"4%",
	textStyle:{
		color:"#fff",
		fontSize:'22'
    },
	subtextStyle:{
		color:'#90979c',
		fontSize:'16',
		
	},
},
	'tooltip':{
		"trigger":"axis",
		"axisPointer":{
			"type":"shadow",
			textStyle:{
				color:"#fff"
			}
		},
	},
	"grid":{
		"borderWidth":0,
		"top":110,
		"bottom":95,
		textStyle:{
			color:"#fff"
		}
	},
	"legend":{
		x: "4%",
		top: '11%',
		textStyle:{
			color: '#90979c',
		},
		"data":["Primary Industry","Secondary Industry","Tertiary Industry","Whole GDP"]
	},
	
	"calculable":true,
	
    xAxis: [{
		'type':'category',
		
        data: ['2009','2010','2011','2012','2013','2014','2015','2016','2017'],
        'splitLine':{
			'show': false
		},
        axisTick: {
            show: false
        },
		"splitArea":{
			"show":false
		},
        axisLine: {
			lineStyle: {
				color: '#90979c'
			}
        },
    }],
    yAxis: [{
		"type":"value",
		"splitLine":{
			"show":false
		},
        "axisLine": {
            lineStyle:{
				color:"#90979c"
			}
        },
        "axisTick": {
            "show": false
        },
        axisLabel: {
            "interval":0,
        },
		"splitArea":{
			"show":false
		},
		
    }],
     dataZoom: [
        {   // 这个dataZoom组件，默认控制x轴。
            type: 'slider', // 这个 dataZoom 组件是 slider 型 dataZoom 组件
            start: 10,      // 左边在 10% 的位置。
            end: 60         // 右边在 60% 的位置。
        },
        {   // 这个dataZoom组件，也控制x轴。
            type: 'inside', // 这个 dataZoom 组件是 inside 型 dataZoom 组件
            start: 10,      // 左边在 10% 的位置。
            end: 60         // 右边在 60% 的位置。
        }
    ],
    series: [

		{
		"name":"Secondary Industry",
		'type':'bar',
		'stack':'总量',
		'barMaxWidth':35,
		'barGap':'10%',
		'itemStyle':{
			'normal':{
				'color':'rgba(255,144,128,1)',
				'label':{
					'show':true,
					'textStyle':{
						'color':"#fff"
					},
					'position':'insideTop',
					formatter: function(p){
						return p.value > 0 ? (p.value):"";
					}
				}
			}
		},
		'data':[2001.80,2480.90,3143.82,3143.820,3143.82,4508.53,4723.49,5232.02,5998.19]
		},
		
		{
		"name":"Tertiary Industry",
		'type':'bar',
		'stack':'总量',
		'barMaxWidth':35,
		'barGap':'10%',
		'itemStyle':{
			'normal':{
				'color':'rgba(0,191,183,1)',
				'label':{
					'show':true,
					'textStyle':{
						'color':"#fff"
					},
					'position':'insideTop',
					formatter: function(p){
						return p.value > 0 ? (p.value):"";
					}
				}
			}
		},
		'data':[2233.04, 2785.30, 3383.42, 4025.2, 4574.23, 5190.99, 5704.52,6463.27,7390.34]
		},
		
		{
		"name":"Whole GDP",
		'type':'line',
		'stack':'总量',
		symbolSize:10,
		symbol:'circle',
		'itemStyle':{
			'normal':{
				'color':'rgba(128,100,280,1)',
				'label':{
					'show':true,
					'textStyle':{
						'color':"#fff"
					},
					'position':'insideTop',
					formatter: function(p){
						return p.value > 0 ? (p.value):"";
					}
				}
			}
		},
		'data':[4503, 5551.3, 6854.58, 8138.9, 9108.89, 10056.59, 10801.16,12170.23,13889.39]
		},
		
		{
		"name":"Primary Industry",
		'type':'bar',
		'stack':'总量',
		'barMaxWidth':35,
		'barGap':'10%',
		'itemStyle':{
			'normal':{
				'color':'rgba(144,280,128,1)',
				'label':{
					'show':false,
					'textStyle':{
						'color':"#fff"
					},
					'position':'insideTop',
					formatter: function(p){
						return p.value > 0 ? (p.value):"";
					}
				}
			}
		},
		'data':[
		267.77,
		285.1,
		327.34,
		348.1,
		353.17,
		357.07,
		373.15,
		474.94,
		500.87
		]
		},
		
	]
	}

```

### Dive into Economy data

<span style="font-size: 20px; font-weight: 600">Employment</span> is the most important economic indicator besides economic growth, and the employment population that the city can accommodate is an important symbol to determine the scale of its urban development.We select the employment population data of Sichuan Province in 2016 to analyze the employment population of each major city.
```chart
{
    backgroundColor: '#2c343c',

    title: {
        text: 'Employment Population of Sichuan in 2016',
        left: 'center',
        top: 20,
        textStyle: {
            color: '#ccc'
        }
    },

    tooltip : {
        trigger: 'item',
        formatter: "{a} <br/>{b} : {c} ({d}%)"
    },

    visualMap: {
        show: false,
        min: 80,
        max: 600,
        inRange: {
            colorLightness: [0, 1]
        }
    },
    series : [
        {
            name:'Cities',
            type:'pie',
            radius : '55%',
            center: ['50%', '50%'],
            data:[
                {value:879.02, name:'Chengdu'},
                {value:222.97, name:'Deyang'},
                {value:303.80, name:'Mianyang'},
                {value:253.15, name:'Luzhou'},
                {value:297.86, name:'Nanchong'},
				{value:332.00,name:"Dazhou"},
				{value:169.46,name:'Zigong'},
				{value:164.50,name:'Guangyuan'},
				{value:162.72,name:'Suining'},
				{value:176.57,name:'Neijiang'},
				{value:185.13,name:'Leshan'},
				{value:315.81,name:'Yibin'},
				{value:218.26,name:'Guangyuan'},
				{value:1178.75,name:'Others'}
            ].sort(function (a, b) { return a.value - b.value; }),
            roseType: 'radius',
            label: {
                normal: {
                    textStyle: {
                        color: 'rgba(255, 255, 255, 0.3)'
                    }
                }
            },
            labelLine: {
                normal: {
                    lineStyle: {
                        color: 'rgba(255, 255, 255, 0.3)'
                    },
                    smooth: 0.2,
                    length: 10,
                    length2: 20
                }
            },
            itemStyle: {
                normal: {
                    color: '#c23531',
                    shadowBlur: 200,
                    shadowColor: 'rgba(0, 0, 0, 0.5)'
                }
            },

            animationType: 'scale',
            animationEasing: 'elasticOut',
            animationDelay: function (idx) {
                return Math.random() * 200;
            }
        }
    ]
}
```


In addition to employment, the level of growth in personal income can reflect the rise in the living standards of residents in the region.


```chart
{
	color: ['#5793f3','#d14a61','#675bba'],
	
	tooltip:{
		trigger:'axis',
		axisPointer:{type:'cross'}
	},
	grid:{
		right:'20%'
	},
	toolbox:{
		feature:{
			dataView:{show:true,readOnly:false},
			restore:{show:true},
			saveAsImage:{show:true}
		}
	},
	legend:{
		data:['Average wage of Chengdu','Average wage of Sichuan','Per capita GDP of Chengdu']
	},
	xAxis:[
		{
			type:'category',
			axisTick:{
				alignWithLabel:true
			},
			data:['2010','2011','2012','2013','2014','2015','2016']
		}
	],
	yAxis:[{
		type:'value',
		name:'Chengdu',
		min: 0,
		max: 60000,
		position:'right',
		axisLine:{
			lineStyle:{
				color:'#5793f3'
			}
		},
		axisLabel:{
			formatter:'{value}'
		}
		},
		{type:'value',
		name:'Sichuan',
		min: 0,
		max: 70000,
		position:'right',
		offset:80,
		axisLine:{
			lineStyle:{
				color:'#d14a61'
			}
		},
		axisLabel:{
			formatter:'{value}'
		}
		},
		{type:'value',
		name:'Per capita GDP',
		min: 0,
		max: 85000,
		position:'left',
		axisLine:{
			lineStyle:{
				color:'#675bba'
			}
		},
		axisLabel:{
			formatter:'{value}'
		}
		}
	],
	series:[
	{
		name:'Average wage of Chengdu',
		type:'bar',
		data:[
		30515,
		34008,
		38221,
		48358,
		51681,
		56872,
		61330
		]
	},
	{
		name:'Average wage of Sichuan',
		type:'bar',
		yAxisIndex:1,
		data:[
		26952,
		31489,
		35873,
		41795,
		45697,
		50466,
		54425
		]
	},
	{
		name:'Per capita GDP of Chengdu',
		type:'line',
		yAxisIndex:2,
		data:[
		41253,
		49438,
		57624,
		63977,
		70019,
		74273,
		76960
		]
	}
	]
}
```



## Rapid urban expansion:The microcosm of urbanization of China

### Population
The Population of Chengdu in 2009 was 9339734, increasing at an average annual rate of 6.8%
since 2000. Although the increase speed has slowed down since 2010, its population annual increase rate is much higher than those of Asia and the world.
					
<table width="800" style="margin-left: auto; margin-right: auto;">
        <tr>
            <td width="400">
```chart
{
    title: {
        text: 'Population',
		subtext:'Million'
    },
    tooltip: {
        trigger: 'axis'
    },
    legend: {
		x: "20%",
		top: '10%',
        data:['Chengdu Population']
    },
    toolbox: {
        show: true,
        feature: {
            dataZoom: {
                yAxisIndex: 'none'
            },
            dataView: {readOnly: false},
            magicType: {type: ['line', 'bar']},
            restore: {},
            saveAsImage: {}
        }
    },
	settings: {
	width: '100%',
	height: '300px',
	border: '1px solid red'
  },
    xAxis:  {
        type: 'category',
        boundaryGap: false,
        data: ['1988','2000','2009','2017']
    },
    yAxis: {
        type: 'value',
        axisLabel: {
            formatter: '{value} '
			
        }
		
    },
    series: [
        {
            name:'Population',
            type:'line',
            data:[2.019420,5.117629,9.339734,14.353300],
        
    }]
}
```
            </td>
            <td width="400">
```chart
{
    title: {
        text: 'Population Avg Change'
    },
    tooltip: {
        trigger: 'axis',
        axisPointer: {
            type: 'shadow'
        }
    },
    legend: {
        data: ['1988-2000', '2000-2009', '2010-2018'],
		x: "2%",
		top: '10%'
    },
    grid: {
        left: 100
    },
    toolbox: {
        show: true,
        feature: {
            saveAsImage: {}
        }
    },
		settings: {
	width: '100%',
	height: '300px',
	border: '1px solid red'
  },
    xAxis: {
        type: 'value',
        name: '%',
        axisLabel: {
            formatter: '{value}'
        }
    },
    yAxis: {
        type: 'category',
        inverse: true,
        data: ['Chengdu', 'East Asia', 'World'],
        axisLabel: {
            formatter: function (value) {
                return '{' + value + '| }\n{value|' + value + '}';
            },
            margin: 20,
            rich: {
                value: {
                    lineHeight: 30,
                    align: 'center'
                },
                Sunny: {
                    height: 40,
                    align: 'center'
                },
                Cloudy: {
                    height: 40,
                    align: 'center'
                },
                Showers: {
                    height: 40,
                    align: 'center'
                  
                }
            }
        }
    },
    series: [
        {
            name: '1988-2000',
            type: 'bar',
            data: [7.7, 3.4, 4.5],
        },
        {
            name: '2000-2009',
            type: 'bar',
            data: [6.8, 3.4, 4.5]
        },
        {
            name: '2010-2018',
            type: 'bar',
            data: [2.21,1.03,1.21]
        }
    ]
}
```
            </td>
        </tr>
    </table>


## Businesses
### What about tech? 
### A short look at the taxi industry.

## But Chengdu is big
### Let's take a look at housing. 
### Supply and demand: days on market.

## Data Sources

## About Us
Our names are [Xiao Feiyu](https://github.com/feiyuxiaothu), Fang Xiaonan and Zhang yusheng.

This project was created for the 2019Spring course : Data Visualization, at the Department os Computer Science within Tsinghua University.

Special thanks to our professor: Prof. Zhang Songhai

 


