# 广东城际时刻表

广州地铁城际线路时刻查询工具 | 支持广清、广惠、广肇、穗深等城际线路

## 项目简介

基于 Web 的广东城际铁路时刻查询工具，以广州地铁风格为设计蓝本，提供直观便捷的列车时刻查询体验。支持按站点查询、按车次查询，并可查看详细的列车停靠信息。

## 功能特点

- **双模式查询** - 支持按站点名称或车次号查询
- **热门站点推荐** - 快速选择常用站点
- **时间轴展示** - 按小时分组展示列车时刻
- **列车类型标识** - 区分特快、快车、站站停列车
- **特殊车次提示** - 标注节假日开行等特殊车次
- **线路分类展示** - 按城际线路归类站点
- **详情弹窗** - 点击时刻查看完整停靠信息

## 覆盖线路

| 线路名称 | 主要站点 |
|---------|---------|
| 广清城际 | 飞霞、清城、花都、广州白云 |
| 广州东环城际 | 番禺、琶洲、竹料、白云机场北 |
| 广肇城际 | 肇庆、鼎湖东、佛山西、番禺 |
| 广惠城际 | 番禺、东莞西、松山湖北、惠州北 |
| 琶莲城际 | 琶洲、广州莲花山 |
| 穗深城际 | 东莞西、虎门北、深圳机场 |
| 清远长隆磁浮 | 清远长隆、湖蝶湾、长隆森林王国 |

## 数据文件说明

| 文件 | 说明 |
|-----|------|
| `gzmtr_schedule.json` | 城际铁路主要时刻表数据 |
| `qingyuan_maglev.json` | 清远磁浮专线数据 |
| `express.json` | 快车/特快列车类型配置 |

### 数据格式示例

**express.json** - 列车类型配置：
```json
{
  "C6873": {
    "type": "特快",
    "typeColor": "#e63946"
  },
  "C4812": {
    "type": "快车",
    "typeColor": "#f5a623"
  }
}
```

**qingyuan_maglev.json** - 磁浮时刻表：
```json
{
  "note": "每周一停止对外运营服务（节假日除外）",
  "trains": [
    {
      "train_no": "00104",
      "direction": "清远长隆 → 长隆森林王国",
      "stops": [
        { "station": "清远长隆", "arrival_time": "09:38", "departure_time": "09:40" },
        { "station": "湖蝶湾", "arrival_time": "09:44", "departure_time": "09:45" },
        { "station": "长隆森林王国", "arrival_time": "09:55", "departure_time": null }
      ]
    }
  ]
}
```

## 本地运行

```bash
# 克隆仓库
git clone https://github.com/your-username/guangzhou-intercity-schedule.git

# 进入目录
cd guangzhou-intercity-schedule

# 使用任意 HTTP 服务器运行
python -m http.server 8000
# 或
npx serve
```

打开浏览器访问 http://localhost:8000

## 界面设计

- 广州地铁经典红黄配色
- 毛玻璃效果与现代化卡片设计
- 响应式布局，适配移动端
- 平滑动画与交互反馈

## 技术栈

- HTML5 / CSS3
- 原生 JavaScript (ES6)
- JSON 数据驱动
- Fetch API 异步加载

## 项目结构

```
├── index.html              # 主页面
├── gzmtr_schedule.json     # 城际时刻表数据
├── qingyuan_maglev.json    # 清远磁浮数据
├── express.json            # 快车类型配置
└── README.md               # 项目说明
```

## 致谢

数据来源于广州地铁官方时刻表，仅供学习交流使用。

> 提示：本工具为静态网页，所有数据存储在 JSON 文件中，可自行更新数据源以保持时刻表准确。
