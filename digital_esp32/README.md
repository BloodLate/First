# 🌡️ ESP32 数字孪生实时监控系统

> 基于 ESP32 + MQTT + ECharts/Three.js 的数字孪生原型系统，实现物理设备数据实时驱动可视化与远程控制。

## 📸 效果展示

<!-- 稍后添加截图 -->

---

## 🏗️ 系统架构

┌─────────────┐ ┌─────────────┐ ┌─────────────┐
│ 硬件层 │ │ 通信层 │ │ 应用层 │
│ ESP32 │───▶│ MQTT │───▶│ ECharts │
│ + DHT11 │ │ + EMQX │ │ Three.js │
└─────────────┘ └─────────────┘ └─────────────┘
采集温湿度 加密传输 实时可视化
执行控制命令 双向通信 远程控制

**数据流：**

- **上行**：DHT11 → ESP32 → MQTT(Broker:8883) → Web Browser
- **下行**：Web Browser → MQTT → ESP32 → LED(GPIO2)

---

## ✨ 功能特性

- 📡 **实时数据采集** - ESP32 + DHT11 采集温湿度数据
- 🔐 **加密MQTT通信** - 8883端口 TLS/SSL 加密传输
- 📊 **实时曲线图** - ECharts 温湿度历史曲线
- 🎮 **3D可视化** - Three.js 3D模型实时驱动
- 💡 **远程控制** - 网页端控制 ESP32 LED 灯
- 🔄 **双向通信** - 完整的上行+下行数据链路

---

## 🛠️ 技术栈

| 层级 | 技术 |
|------|------|
| 硬件 | ESP32-WROOM-32, DHT11 |
| 嵌入式 | Arduino IDE, C++ |
| 通信协议 | MQTT 5.0 (TLS/SSL) |
| 云端 | EMQX Cloud (Serverless) |
| 前端 | HTML/CSS/JavaScript |
| 图表库 | ECharts 5.x |
| 3D引擎 | Three.js 0.150 |
| MQTT客户端 | mqtt.js 5.x |

---

## 🚀 快速开始

### 硬件准备

- ESP32 开发板 × 1
- DHT11 温湿度模块 × 1
- 杜邦线若干

### 接线方式

DHT11 ESP32
───── ─────
VCC → 3.3V
DATA → GPIO13
GND → GND

### 烧录步骤

1. 安装 Arduino IDE 2.x
2. 安装 ESP32 开发板支持
3. 安装依赖库：DHT sensor library、PubSubClient
4. 打开 `hardware/esp32_dht11_mqtt.ino`
5. 修改 WiFi 和 MQTT 配置
6. 上传到 ESP32

### 打开网页

双击 web/index.html 即可打开
或用本地服务器：
cd web
python -m http.server 8080
浏览器打开 http://localhost:8080

---

## 📁 项目结构


├── README.md # 项目说明
├── LICENSE # MIT 开源协议
├── .gitignore # Git 忽略规则
├── hardware/
│ └── esp32_dht11_mqtt.ino # ESP32 Arduino 代码
├── web/
│ ├── index.html # ECharts 图表版
│ └── threejs.html # Three.js 3D 版
├── docs/ # 文档截图
└── images/ # 实物照片

---

## 📝 协议

本项目基于 MIT License 开源。

---

## 👤 Author

**your_name**

---

> ⭐ 如果这个项目对你有帮助，请给个 Star！
