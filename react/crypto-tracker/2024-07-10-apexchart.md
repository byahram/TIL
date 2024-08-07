# [가상화폐 트랙커] 3. ApexChart 사용하여 코인 차트 만들기

<br>

## 1. apexchart 설치하기

```sh
$ npx install react-apexcharts
```

<br>

## 2. components/Chart/Chart

```js
import ReactApexChart from "react-apexcharts";
import { useRecoilValue } from "recoil";
import { isDarkAtom } from "../../stores/atoms";
import { ChartHistoricalInterface } from "../../api/interface";

interface ChartProps {
  data: ChartHistoricalInterface[];
}

const chartOptions = {
  chart: {
    type: "candlestick",
    toolbar: {
      show: false,
    },
    background: "transparent",
  },
  title: {
    text: "CandleStick for 2 weeks",
    align: "left",
  },
  theme: {
    mode: isDark ? "dark" : "light",
  },
  stroke: {
    curve: "smooth",
    width: 2,
  },
  yaxis: {
    show: false,
  },
  xaxis: {
    labels: {
      formatter: function (val) {
        const day = new Date(val);
        return `${day.getMonth() + 1}/${day.getDate()}`;
      },
      style: {
        colors: "#9c88ff",
      },
    },
  },
  plotOptions: {
    candlestick: {
      colors: {
        upward: "#f23d3d",
        downward: "#13bf36",
      },
    },
  },
};

const chartSeries = {
  {
    data:
      data?.map((item) => ({
        x: new Date(Number(item.time_close) * 1000),
        y: [item.open, item.high, item.low, item.close],
      })) ?? [],
  },
};

function Chart({ data }: ChartProps) {
  const isDark = useRecoilValue(isDarkAtom);

  return (
    <ReactApexChart
      type="candlestick"
      series={chartSeries}
      options={chartOptions}
    />
  );
}

export default Chart;
```

<br>

## 결과!!!

![missing](../../assets/img/2024/20240710_1.png)

<br>
