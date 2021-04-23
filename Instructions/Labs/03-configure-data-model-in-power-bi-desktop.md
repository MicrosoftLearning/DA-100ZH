

# **在 Power BI Desktop 中对数据建模，第 1 部分**

**完成本实验室预计需要 45 分钟**

在本实验室中，你将开始开发数据模型。这涉及在表之间创建关系，然后配置表和列属性，以提高数据模型的友好性和可用性。你还将创建层次结构并创建快速度量。

在本实验室中，你将学习如何：

- 创建模型关系

- 配置表和列属性

- 创建层次结构

- 创建快速度量

### **实验室故事**

本实验室是一个实验室系列中的诸多实验室之一，设计为从数据准备到作为报表和仪表板发布的完整故事。可以按任意顺序完成这些实验室。但是，如果你打算完成多个实验室，对于前 10 个实验室，建议你按以下顺序完成：

1. 在 Power BI Desktop 中准备数据

2. 在 Power BI Desktop 中加载数据

3. **在 Power BI Desktop 中对数据建模，第 1 部分**

4. 在 Power BI Desktop 中对数据建模，第 2 部分

5. 在 Power BI Desktop 中创建 DAX 计算，第 1 部分

6. 在 Power BI Desktop 中创建 DAX 计算，第 2 部分

7. 在 Power BI Desktop 中设计报表，第 1 部分

8. 在 Power BI Desktop 中设计报表，第 2 部分

9. 创建 Power BI 仪表板

10. 创建 Power BI 分页报表

11. 在 Power BI Desktop 中执行数据分析

## **练习 1：创建模型关系**

在此练习中，你将创建模型关系。

### **任务 1：入门**

在此任务中，你将设置实验室环境。

*重要说明：如果你从上一个实验室继续操作（并且已成功完成该实验室），则无需完成此任务；而是继续执行下一个任务。*

1. 要打开 Power BI Desktop，请在任务栏上单击 Microsoft Power BI Desktop 快捷方式。

    ![图片 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

1. 要关闭开始窗口，请单击窗口左上角的 **“X”**。

 	![图片 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

1. 要打开入门 Power BI Desktop 文件，请单击 **“文件”** 功能区选项卡以打开 Backstage 视图。

1. 选择 **“打开报表”**。

 	![图片 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

1. 单击 **“浏览报表”**。

 	![图片 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

1. 在“打开”窗口，导航到 **“D:\DA100\Labs\03-configure-data-model-in-power-bi-desktop\Starter”** 文件夹。

1. 选择 **“Sales Analysis”** 文件。

1. 单击 **“打开”**。

 	![图片 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

1. 关闭可能打开的所有信息窗口。

1. 要创建该文件的副本，请单击 **“文件”** 功能区选项卡以打开 Backstage 视图。

1. 选择 **“另存为”**。

 	![图片 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

1. 如果系统提示应用更改，请单击 **“应用”**。

 	![图片 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

1. 在 **“另存为”** 窗口中，导航到 **“D:\DA100\MySolution”** 文件夹。

1. 单击 **“保存”**。

 	![图片 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### **任务 2：创建模型关系**

在此任务中，你将创建模型关系。

1. 在 Power BI Desktop中，单击左侧的 **“模型”** 视图图标。

	![图片 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. 如果不能看到所有七个表，可以向右水平滚动，然后将这些表拖放到一起，这样就可以同时看到它们。

	*提示：你也可以使用窗口底部的缩放控件。*

	*在“模型”视图中，可以查看每个表和关系（表之间的连接器）。目前，没有任何关系存在，因为你在 **“在 Power BI Desktop 中准备数据”** 实验室中禁用了数据加载关系选项。*

3. 若要返回“报表”视图，请单击左侧的 **“报表”** 视图图标。

	![图片 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. 若要查看所有表字段，请右键单击 **“字段”** 窗格中空白区域，然后选择 **“展开全部”**。

	![图片 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. 要创建表视觉对象，请在 **“字段”** 窗格的 **“Product”** 表中，选中 **“Category”** 字段。

	![图片 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

	*实验室将使用速记表示法来引用字段。如下所示： **Product | Category**。在此示例中， **“Product”** 是表名， **“Category”** 是字段名。*

6. 若要在表中添加更多列，请在 **“字段”** 窗格中，选中 **“Sales | Sales”** 字段。

7. 请注意，表视觉对象列出了四个产品类别，每个类别的销售额值相同，总计也相同。

	![图片 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

	*问题在于该表基于不同表中的字段。期望每个产品类别都显示该类别的销售额。但是，由于这些表之间没有模型关系， **“Sales”** 表未经过筛选。现在，你将添加一个关系以在表之间传播筛选。*

8. 在 **“建模”** 功能区选项卡上的 **“关系”** 组内，单击 **“管理关系”**。

	![图片 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. 在 **“管理关系”** 窗口中，可以看到尚未定义任何关系。

10. 若要创建关系，请单击 **“新建”**。

	![图片 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. 在 **“创建关系”** 窗口的第一个下拉列表中，选择 **“Product”** 表。

	![图片 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. 在第二个下拉列表中（在 **“Product”** 表网格下方），选择 **“Sales”** 表。

	![图片 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. 注意，每个表中的 **“ProductKey”** 列均处于选中状态。

	*由于这些列具有相同名称和数据类型，因此自动将其选中。*

14. 在 **“基数”** 下拉列表中，可以看到已选择 **“一对多(1:*)”**。

	*由于 Power BI 认为 **“Product”** 表中的 **“ProductKey”** 列包含唯一值，因此已自动检测到基数。一对多关系是最常见的基数，本实验室中创建的所有关系都将是这种类型。在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中，你将处理多对多基数。*

15. 在 **“交叉筛选方向”** 下拉列表中，可以看到 **“单向”** 处于选中状态。

	*单一筛选方向表示筛选从“一侧”传播到“多侧”。在本例中，这意味着应用于 **“Product”** 表的筛选将传播到 **“Sales”** 表，但传播方向不能反过来。在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中，你将处理双向关系。*

16. 可以看到 **“将此关系标记为可用”** 处于选中状态。

	*活动关系传播筛选。可以将关系标记为非活动状态，这样筛选就不会传播。当表之间存在多个关系路径时，可能存在不活动的关系。在这种情况下，模型计算可以使用特殊函数来激活它们。在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中，你将处理不活动的关系。*

17. 单击 **“确定”**。

	![图片 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. 在 **“管理关系”** 窗口中，请注意新关系已列出，然后单击 **“关闭”**。

	![图片 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. 在报表中，可以看到表视觉对象已更新为针对每个产品类别显示不同的值。

	![图片 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

	*现在，应用于 **“Product”** 表的筛选会传播到 **“Sales”** 表。*

20. 切换到“模型”视图，然后注意到两个表之间现在有一个连接器（两个表是否并排放置没有关系）。

	![图片 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. 在下图中，注意你可以解释由 **1** 和 **“*”** 指标表示的基数。

	*筛选方向由箭头表示。实线表示活动关系，虚线表示不活动关系。*

22. 将光标悬停在关系上以突出显示相关列。

	*创建关系还有更简单的方法。在模型图中，可以拖放列以新建关系。*

23. 若要使用其他方法创建新关系，请将 **“Reseller”** 表中的 **“ResellerKey”** 列拖放到 **“Sales”** 表中的 **“ResellerKey”** 列上。

	![图片 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

	*提示：有时候，有的列无法正常拖动。如果出现这种情况，请选择其他列，然后再次选择要拖动的列，然后重试。确保显示添加到该图的新关系。*

24. 使用新方法创建以下两个模型关系：

	- **Region | SalesTerritoryKey** 对 **Sales | SalesTerritoryKey**

	- **Salesperson | EmployeeKey** 对 **Sales | EmployeeKey**

	*在此实验室中， **“SalespersonRegion”** 和 **“Targets”** 表将保持未联接关系。销售员与区域之间存在多对多关系，在 **“在 Power BI Desktop 对数据建模，第 2 部分”** 实验室中，你将使用这种高级方案。*

25. 在该图中，排列表，以使 **“Sales”** 表位于图的中心，并围绕该表排列相关的表。将断开联接的表放在一边。

	![图片 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)

26. 保存 Power BI Desktop 文件。

## **练习2：配置表**

在本练习中，你将通过创建层次结构和隐藏、格式化列以及对其进行分类来配置每个表。

### **任务 1：配置 Product 表**

在此任务中，你将配置 **“Product”** 表。

1. 在“模型”视图中的 **“字段”** 窗格中，展开 **“Product”** 表以显示所有字段（如有必要）。

2. 要创建层次结构，请在 **“字段”** 窗格中右键单击 **“Category”** 列，然后选择 **“创建层次结构”**。

	![图片 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. 在 **“属性”** 窗格（位于 **“字段”** 窗格左侧）中，将 **“名称”** 框中的文本替换为 **“Products”**。

	![图片 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. 要将第二个级别添加到层次结构，请在 **“属性”** 窗格中的 **“层次结构”** 下拉列表中，选择 **“Subcategory”** （可能需要在窗格内部向下滚动）。

5. 要向层次结构添加第三个级别，请在 **“层次结构”** 下拉列表中选择 **“Product”**。

6. 要完成层次结构设计，请单击 **“应用级别更改”**。

	![图片 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

	*提示：务必单击 **“应用级别更改”**，忽略此步骤是一种常见错误。*

7. 在 **“字段”** 窗格中，请注意 **“Products”** 层次结构。

	![图片 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. 若要显示层次结构级别，请展开 **“Products”** 层次结构。

	![图片 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. 若要将列组织到显示文件夹中，请先在 **“字段”** 窗格中选择 **“Background Color Format”** 列。

10. 在按住 **Ctrl** 键的同时，选择 **“Font Color Format”** 列。

11. 在 **“属性”** 窗格中的 **“显示文件夹”** 框内，输入 **“格式设置”**。

	![图片 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. 在 **“字段”** 窗格中，注意这两列现在位于一个文件夹中。

	![图片 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

	*显示文件夹是整理表的一种好方法，尤其是对于包含许多字段的表来说。*

### **任务 2：配置 Region 表**

在此任务中，你将配置 **“Region”** 表。

1. 在 **“Region”** 表中，创建一个名为 **“Regions”** 的层次结构，分为以下三个级别：

	- Group

	- Country

	- Region

	![图片 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. 选择 **“Country”** 列（不是 **“Country”** 层次结构级别）。

3. 在 **“属性”** 窗格中，展开 **“高级”** 部分（位于窗格底部），然后在 **“数据类别”** 下拉列表中，选择 **“Country/Region”**。

	![图片 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

	*数据分类可以为报表设计者提供提示。本例将列分类为国家或地区，可在 Power BI 呈现地图可视化效果时提供更准确的信息。*

### **任务 3：配置 Reseller 表**

在此任务中，你将配置 **“Reseller”** 表。

1. 在 **“Reseller”** 表中，创建一个名为 **“Reseller”** 的层次结构，分为以下两个级别：

	- Business Type

	- Reseller

	![图片 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. 创建名为 **“Geography”** 的第二个层次结构，分为以下四个级别：

	- Country-Region

	- State-Province

	- City

	- Reseller

	![图片 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. 将以下三列分类：

	- 将 **“Country-Region”** 分类为 **“Country/Region”**

	- 将 **“State-Province”** 分类为 **“State or Province”**

	- 将 **“City”** 分类为 **“City”**

### **任务 4：配置 Sales 表**

在此任务中，你将配置 **“Sales”** 表。

1. 在 **“Sales”** 表中，选择 **“Cost”** 列。

2. 在 **“属性”** 窗格中的 **“描述”** 框内输入： **Based on standard cost**

	![图片 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

	*说明可应用于表、列、层次结构或度量。在 **“字段”** 窗格中，当报表作者将光标悬停在字段上时，说明文本会显示在工具提示中。*

3. 选择 **“Quantity”** 列。

4. 在 **“属性”** 窗格中的 **“格式”** 部分内，将 **“千位分隔符”** 属性滑动至 **“开”**。

	![图片 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. 选择 **“Unit Price”** 列。

6. 在 **“属性”** 窗格的 **“格式”** 部分，将 **“小数位数”** 属性滑动至 **“2”**。

7. 在 **“高级”** 组（可能需要向下滚动才能找到）的 **“汇总方式”** 下拉列表中选择 **“平均值”**。

	![图片 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

	*默认情况下，数值列通过将值相加进行汇总。此默认行为不适用于 **“Unit Price”** 之类的代表比率的列。将默认汇总设置为平均值将生成有意义的结果。*

### **任务 5：批量更新属性**

在此任务中，你将使用单个批量更新来更新多个列。将使用此方法来隐藏列，并设置列值的格式。

1. 在 **“字段”** 窗格中，选择 **“Product | ProductKey”** 列。

2. 在按下 **_Ctrl** 键时，选择以下 13 个列（跨多个表）：

	- Region | SalesTerritoryKey

	- Reseller | ResellerKey

	- Sales | EmployeeKey

	- Sales | ResellerKey

	- Sales | SalesOrderNumber

	- Sales | SalesTerritoryKey

	- Salesperson | EmployeeID

	- Salesperson | EmployeeKey

	- Salesperson | UPN

	- SalespersonRegion | EmployeeKey

	- SalespersonRegion | SalesTerritoryKey

	- Targets | EmployeeID

3. 在 **“属性”** 窗格中将 **“隐藏”** 属性滑动至 **“开”**。

	![图片 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

	*这些列是隐藏的，因为它们要么被关系使用，要么将在行级别安全性配置或计算逻辑中使用。*

	*在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中，你将使用 **UPN** 列定义行级别安全性。在 **“在 Power BI Desktop 中创建 DAX 计算，第 1 部分”** 实验室中，你将在计算中使用 **“SalesOrderNumber”**。*

4. 同时选择以下三列：

	- Product | Standard Cost

	- Sales | Cost

	- Sales | Sales

5. 在 **“属性”** 窗格中，从 **“格式设置”** 部分内将 **“小数位数”** 属性设置为 **“0”** （零）。

	![图片 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## **练习 3：查看模型接口**

在本练习中，将切换到“报表”视图，查看模型接口。

### **任务 1：查看模型接口**

在此任务中，将切换到“报表”视图，查看模型接口。

1. 切换到“报表”视图。

2. 请注意在 **“字段”** 窗格中：

	- 列、层次结构及其级别均为字段，可用于配置报表视觉对象

	- 仅与报表创作相关的字段可见

	- **“SalespersonRegion”** 表不可见 - 因为其所有字段都处于隐藏状态

	- **“Region”** 和 **“Reseller”** 表中的空间字段标有空间图标

	- 默认情况下，标有 sigma 符号 (Ʃ) 的字段将进行汇总

	- 将光标悬停在 **“Sales | Cost”** 字段上会出现工具提示

3. 展开 **“Sales | OrderDate”** 字段，然后注意其展示了一个日期层次结构。

	![图片 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

	***“Targets | TargetMonth”** 字段提供类似的层次结构。这些层次结构不是由你创建。它们是自动创建的。但是，有一个问题。Adventure Works 财政年度始于每年的 7 月 1 日。但是，在这些自动创建的日期层次结构中，日期层次结构年份始于每年的 1 月 1 日。*

	*现将关闭此自动行为。在 **“在 Power BI Desktop 中创建 DAX 计算，第 1 部分”** 实验室中，你将使用 DAX 创建日期表，并对其进行配置以定义 Adventure Works 的日历。*

4. 单击 **“文件”** 功能区选项卡打开 backstage 视图即可关闭自动/日期时间。

5. 选择左侧的 **“选项和设置”**，然后选择 **“选项”**。

	![图片 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. 在 **“选项”** 窗口左侧的 **“当前文件”** 组中选择 **“数据加载”**。

	![图片 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. 在 **“时间智能”** 部分，取消选中 **“自动日期/时间”**。

	![图片 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. 单击 **“确定”**。

	![图片 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. 请注意 **“字段”** 窗格中的日期层次结构不再可用。

	![图片 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)

## **练习 4：创建快速度量**

在本练习中，你将创建两个快速度量。

### **任务 1：创建快速度量**

在此任务中，你将创建两个快速度量来计算利润和利润率。

1. 在 **“字段”** 窗格中，右键单击 **“Sales”** 表，然后选择 **“新建快速度量”**。

	![图片 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

2. 在 **“快速度量”** 窗口的 **“计算”** 下拉列表中，从 **“数学运算”** 组内选择 **“减法”**。

	![图片 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

3. 在 **“快速度量”** 窗口的 **“字段”** 窗格中，展开 **“Sales”** 表。

4. 将 **“Sales”** 字段拖到 **“基值”** 框内。

5. 将 **“Cost”** 字段拖动到 **“要减去的值”** 框内。

	![图片 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

6. 单击 **“确定”**。

	![图片 369](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image49.png)

	*快速度量会为你创建计算公式。对于简单而通用的计算，可以轻松快速地创建。在 **“在 Power BI Desktop 中创建 DAX 计算，第 1 部分”** 实验室中，无需使用此工具即可创建度量。*

7. 注意 **“字段”** 窗格 **“Sales”** 表中的新度量。

	![图片 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

	*度量标有计算器图标。*

8. 若要重命名度量，请右键单击度量，然后选择 **“重命名”**。

	![图片 371](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image51.png)

	*提示：要重命名字段，也可以双击它，或选择它并按 **F2**。*

9. 将度量重命名为 **“Profit”**，然后按 **Enter**。

10. 在 **“Sales”** 表中，根据以下要求添加第二个快速度量：

	- 使用 **“除法”** 数学运算

	- 将 **“分子”** 设为 **“Sales | Profit”** 字段

	- 将 **“分母”** 设置为 **“Sales | Sales”** 字段

	- 将度量重命名为 **“Profit Margin”**

	![图片 372](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image52.png)

	![图片 373](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image53.png)

11. 确保 **“Profit Margin”** 度量处于选中状态，然后在 **“度量工具”** 上下文功能区中，将格式设置为 **“百分比”**，保留两位小数。

	![图片 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

12. 若要测试这两种度量，请首先选择报表页面上的表视觉对象。

13. 在 **“字段”** 窗格中，检查这两个度量。

	![图片 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

14. 单击并拖动右参考线以拓宽表视觉对象。

	![图片 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

15. 验证这些度量是否生成了格式正确的合理结果。

	![图片 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### **任务 2：完成**

在此任务中，你将完成实验室。

1. 若要删除表，请通过单击选择表，然后按 **Delete** 键。

2. 保存 Power BI Desktop 文件。

3. 如果系统提示应用查询，请单击 **“稍后应用”**。

4. 如果你打算开始下一个实验室，请让 Power BI Desktop 保持打开状态。

	*在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中，你将通过配置多对多关系和行级别安全性来增强数据模型。*
