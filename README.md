# Visual-analysis-of-stock-data
Visual analysis of stock data
以下是一个基于您提供的内容编写的 `README.md` 文件。此文件总结了代码的功能、依赖项以及如何运行代码等内容：

---

# 数据分析与可视化项目

## 项目简介

本项目通过使用 Python 的数据科学库（如 NumPy、Pandas、Matplotlib 和 Seaborn），对股票数据进行分析和可视化。主要功能包括：

1. **股票价格趋势分析**：绘制指定时间段内的股票收盘价趋势图。
2. **交易量对比**：比较两家公司（BYD 和 GWM）的股票交易量。
3. **年度数据可视化**：展示特定年份（如 2021 年）内某公司的股票价格趋势。

## 项目结构

项目包含多个代码单元，每个单元实现不同的功能模块：
- **数据加载与预处理**：导入必要的库并加载股票数据。
- **单公司股票价格趋势图**：绘制某公司（如 GWM）的股票价格趋势。
- **双公司交易量对比图**：比较 BYD 和 GWM 的交易量。
- **年度数据可视化**：专注于某一年度的股票价格趋势分析。

## 依赖项

运行本项目需要安装以下 Python 库：
- `numpy`
- `pandas`
- `matplotlib`
- `seaborn`

可以通过以下命令安装依赖项：
```bash
pip install numpy pandas matplotlib seaborn
```

## 如何运行

1. 克隆或下载本项目到本地。
2. 确保已安装所有依赖项。
3. 运行 Jupyter Notebook 或 Python 脚本以生成图表。

### 示例代码片段

以下是项目中的核心功能代码示例：

#### 绘制 GWM 股票价格趋势图
```python
import matplotlib.pyplot as plt

fig = plt.figure()
ax2 = fig.add_subplot(1, 1, 1)
ax2 = GWM['Close'].plot(title='GWM Stock Prices')
ax2.set_xlabel('Date')
ax2.set_ylabel('Close (Currency in CNY)')
plt.savefig('GWM_Stock_Prices.png', dpi=400, bbox_inches='tight')
```

#### 比较 BYD 和 GWM 的交易量
```python
fig = plt.figure(figsize=(15, 6))
BYD['Volume'].plot(label='BYD', title='Volume comparison of BYD and GWM')
GWM['Volume'].plot(label='GWM')
plt.legend(loc='best')
plt.savefig('BYD_vs_GWM_Volume.png', dpi=400, bbox_inches='tight')
```

#### 绘制 2021 年 GWM 股票价格趋势
```python
fig = plt.figure()
ax2 = GWM.loc['2021-1-1':'2021-12-31', 'Close'].plot(marker='>', color='g', figsize=(15, 6))
ax2.set_title('2021 GWM Stock Prices Trend')
ax2.set_xlabel('Date')
ax2.set_ylabel('Close (Currency in CNY)')
plt.savefig('GWM_2021_Stock_Prices.png', dpi=400, bbox_inches='tight')
```

## 输出结果

运行代码后，将生成以下图表文件：
- `GWM_Stock_Prices.png`：GWM 股票价格趋势图。
- `BYD_vs_GWM_Volume.png`：BYD 和 GWM 交易量对比图。
- `GWM_2021_Stock_Prices.png`：2021 年 GWM 股票价格趋势图。

## 注意事项

1. **数据准备**：确保项目中使用的股票数据（如 `GWM` 和 `BYD`）已正确加载。
2. **日期格式**：在绘制年度趋势图时，请确保日期列的格式为 `Datetime` 类型。
3. **保存路径**：图表文件默认保存在当前工作目录下。如果需要更改保存路径，请修改 `plt.savefig()` 中的路径参数。
