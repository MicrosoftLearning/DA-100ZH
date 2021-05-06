---
lab:
    title: '在 Power BI Desktop 中加载数据'
    module: '模块 3: 在 Power BI 中清理、转换和加载数据'
---

# **在 Power BI Desktop 中加载数据**

**完成本实验室预计需要 45 分钟**

在本实验室中，你将开始对上一个实验室中创建的每个查询应用转换。然后，你将应用查询，以将每个查询作为表加载到数据模型。

在本实验室中，你将学习如何：

- 应用各种转换

- 应用查询以将其加载到数据模型

### **实验室故事**

本实验室是一个实验室系列中的诸多实验室之一，设计为从数据准备到作为报表和仪表板发布的完整故事。可以按任意顺序完成这些实验室。但是，如果你打算完成多个实验室，对于前 10 个实验室，建议你按以下顺序完成：

1. 在 Power BI Desktop 中准备数据

2. **在 Power BI Desktop 中加载数据**

3. 在 Power BI Desktop 中对数据建模，第 1 部分

4. 在 Power BI Desktop 中对数据建模，第 2 部分

5. 在 Power BI Desktop 中创建 DAX 计算，第 1 部分

6. 在 Power BI Desktop 中创建 DAX 计算，第 2 部分

7. 在 Power BI Desktop 中设计报表，第 1 部分

8. 在 Power BI Desktop 中设计报表，第 2 部分

9. 创建 Power BI 仪表板

10. 创建 Power BI 分页报表

11. 在 Power BI Desktop 中执行数据分析

## **练习 1：加载数据**

在本练习中，你将对上一个实验室中创建的每个查询应用转换。

### **任务 1：入门**

在此任务中，你将设置实验室环境。

*重要说明：如果你从上一个实验室继续操作（并且已成功完成该实验室），则无需完成此任务；而是继续执行下一个任务。*

1. 要打开 Power BI Desktop，请在任务栏上单击 Microsoft Power BI Desktop 快捷方式。

    ![图片 8](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image1.png)

1. 要关闭开始窗口，请单击窗口左上角的 **“X”**。

    ![图片 7](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image2.png)

1. 要打开入门 Power BI Desktop 文件，请单击 **“文件”** 功能区选项卡以打开 Backstage 视图。

1. 选择 **“打开报表”**。

	![图片 10](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image3.png)

1. 单击 **“浏览报表”**。

    ![图片 11](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image4.png)

1. 在“打开”窗口，导航到 **“D:\DA100\Labs\02-load-data-with-power-query-in-power-bi-desktop\Starter”** 文件夹。

1. 选择 **“Sales Analysis”** 文件。

1. 单击 **“打开”**。

	![图片 12](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image5.png)

1. 关闭可能打开的所有信息窗口。

1. 请注意功能区下方的黄色警告消息。

	*该消息会提醒你尚未应用查询来加载为模型表。你稍后将在本实验室中应用查询。*

1. 要关闭警告消息，请在黄色警告消息的左侧单击 **“X”**。

	![图片 13](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image6.png)

1. 要创建该文件的副本，请单击 **“文件”** 功能区选项卡以打开 backstage 视图。

1. 选择 **“另存为”**。

    ![图片 18](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image7.png)

1. 如果提示应用更改，请单击 **“稍后应用”**。

    ![图片 22](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image8.png)

1. 在 **“另存为”** 窗口中，导航到 **“D:\DA100\MySolution”** 文件夹。

1. 单击 **“保存”**。

    ![图片 15](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image9.png)

1. 若要打开 **“Power Query 编辑器”** 窗口，请在“主页”功能区选项卡上的 **“查询”** 组内，单击 **“转换数据”** 图标。

	![图片 20](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image10.png)

### **任务 2：配置 Salesperson 查询**

在此任务中，你将配置 **“Salesperson”** 查询。

1. 在 **“Power Query 编辑器”** 窗口的 **“查询”** 窗格中，选择 **“DimEmployee”** 查询。

	![图片 1](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image11.png)

2. 若要重命名查询，请在 **“查询设置”** 窗格（位于右侧）的 **“名称”** 框中将文本替换为 **“Salesperson”**，然后按 **Enter**。

	*查询名称将确定模型表名称。建议定义简明且容易记住的名称。*

3. 在 **“查询”** 窗格中，确认查询名称已更新。

	![图片 87](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image12.png)

	*现在，你将筛选查询行以仅检索职位是销售员的员工。*

4. 要找到特定的列，请在 **“主页”** 功能区选项卡上的 **“管理列”** 组中，单击 **“选择列”** 向下箭头，然后选择 **“转到列”**。

	![图片 88](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image13.png)

	*提示：当查询包含许多列时，此方法很有用。如果列数不多，只需水平滚动即可找到感兴趣的列。*

5. 在 **“转到列”** 窗口中，要按列名对列表进行排序，请单击 **AZ** 排序按钮，然后选择 **“名称”**。

	![图片 94](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image14.png)

6. 选择 **“SalesPersonFlag”** 列，然后单击 **“确定”**。

7. 要筛选查询，请在 **“SalesPersonFlag”** 列标题中单击向下箭头，然后取消选中 **“False”**。

	![图片 95](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image15.png)

8. 单击 **“确定”**。

	![图片 96](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image16.png)

9. 在 **“查询设置”** 窗格中的 **“应用的步骤”** 列表中，请注意添加了 **“筛选的行”** 步骤。

	![图片 98](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image17.png)

	*你创建的每个转换都会生成其他步骤逻辑。可以编辑或删除步骤。在查询转换阶段，还可以选择一个步骤来预览查询结果。*

10. 要删除列，在 **“主页”** 功能区选项卡中的 **“管理列”** 组中，单击 **“选择列”** 图标。

	![图片 99](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image18.png)

11. 在 **“选择列”** 窗口中，要取消选中所有列，请取消选中 **“(选择所有列)”** 项。

	![图片 102](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image19.png)

12. 要包括列，请选中以下六列：

	- EmployeeKey

	- EmployeeNationalIDAlternateKey

	- FirstName

	- LastName

	- Title

	- EmailAddress

13. 单击 **“确定”**。

	![图片 104](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image20.png)

14. 在 **“应用的步骤”** 列表中，请注意添加了另一个查询步骤。

	![图片 112](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image21.png)

15. 要创建单个名称列，请首先选择 **“FirstName”** 列标题。

16. 按下 **Ctrl** 键的同时，选择 **“LastName”** 列。

	![图片 116](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image22.png)

17. 右键单击任一所选列标题，然后在上下文菜单中选择 **“合并列”**。

	![图片 117](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image23.png)

	*可以通过以下方式应用许多常见的转换：右键单击列标题，然后从上下文菜单中进行选择。但是请注意，功能区中还有更多转换可用。*

18. 在 **“合并列”** 窗口中的 **“分隔符”** 下拉列表中，选择 **“空格”**。

19. 在 **“新列名”** 框中，将文本替换为 **“Salesperson”**。

	![图片 119](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image24.png)

20. 单击 **“确定”**。

	![图片 5636](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image25.png)

21. 若要重命名 **“EmployeeNationalIDAlternateKey”** 列，双击 **“EmployeeNationalIDAlternateKey”** 列标题。

22. 将文本替换为 **“EmployeeID”**，然后按 **Enter**。

	*重要说明：当收到指示对列进行重命名时，请务必完全按照指示对其进行重命名。*

23. 使用前面的步骤将 **“EmailAddress”** 列重命名为 **“UPN”**。

	*UPN 是用户主体名称的缩写。在 **“在 Power BI Desktop 中对数据建模，第 2 部分”** 实验室中配置行级别安全性时，将使用此列中的值。*

24. 在状态栏的左下角，验证查询是否具有 5 列和 18 行。

	![图片 5638](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image26.png)

	*重要说明：如果查询未生成正确的结果，请不要继续，否则无法完成后面的实验室，这一点很重要。如果查询的列或行不匹配，请参考此任务中的步骤解决所有问题。*

### **任务 3：配置 SalespersonRegion 查询**

在此任务中，你将配置 **“SalespersonRegion”** 查询。

1. 在 **“查询”** 窗格中，选择 **“DimEmployeeSalesTerritory”** 查询。

	![图片 5639](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image27.png)

2. 在 **“查询设置”** 窗格中，将查询重命名为 **“SalespersonRegion”**。

3. 要删除最后两列，请先选择 **“DimEmployee”** 列标题。

4. 在按下 **Ctrl** 键的同时，选择 **“DimSalesTerritory”** 列标题。

5. 右键单击任一选择列标题，然后在上下文菜单中选择 **“删除列”**。

	![图片 5640](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image28.png)

6. 在状态栏中，验证查询是否具有 2 列和 39 行。

	![图片 5641](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image29.png)

### **任务 4：配置 Product 查询**

在此任务中，你将配置 **“Product”** 查询。

*重要说明：由于已提供了详细说明，因此，实验室步骤现将提供更简洁的说明。如果需要详细说明，可以参考前面任务的步骤。*

1. 选择 **“DimProduct”** 查询。

	![图片 5643](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image30.png)

2. 将该查询重命名为 **“Product”**。

3. 找到 **“FinishedGoodsFlag”** 列，然后筛选该列以检索制成品的产品（即 TRUE）。

4. 删除所有列，以下列除外：

	- ProductKey

	- EnglishProductName

	- StandardCost

	- Color

	- DimProductSubcategory

5. 请注意 **“DimProductSubcategory”** 列代表相关表（它包含 **“值”** 链接）。

6. 在 **“DimProductSubcategory”** 列标题中，在列名称右侧，单击展开按钮。

	![图片 5644](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image31.png)

7. 要取消选中所有列，请取消选中 **“(选择所有列)”** 项。

8. 选中 **“EnglishProductSubcategoryName”** 和 **“DimProductCategory”** 列。

	![图片 5646](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image32.png)

	*通过选择这两列，将应用转换以联接到 **“DimProductSubcategory”** 表，然后包含这些列。 **“DimProductCategory”** 列实际上是数据源中的另一个相关表。*

9. 取消选中 **“使用原始列名作为前缀”** 复选框。

	![图片 5647](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image33.png)

	*查询列名必须始终是唯一的。选中后，此复选框将为每个列添加扩展列名作为前缀（在本例中为 **“DimProductSubcategory”**）。因为已知所选列名不会与 **“Product”** 查询中的列名冲突，可以取消选择此选项。*

10. 单击 **“确定”**。

	![图片 5648](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image34.png)

11. 请注意，转换导致添加了两列，并且 **“DimProductSubcategory”** 列已被删除。

12. 展开 **“DimProductCategory”** 列，然后仅引入 **“EnglishProductCategoryName”** 列。

13. 重命名以下四列：

	- 将 **“EnglishProductName”** 重命名为 **“Product”**

	- 将 **“StandardCost”** 重命名为 **“Standard Cost”** （含空格）

	- 将 **“EnglishProductSubcategoryName”** 重命名为 **“Subcategory”**

	- 将 **“EnglishProductCategoryName”** 重命名为 **“Category”**

14. 在状态栏中，验证查询是否具有 6 列和 397 行。

	![图片 5651](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image35.png)

### **任务 5：配置 Reseller 查询**

在此任务中，你将配置 **“Reseller”** 查询。

1. 选择 **“DimReseller”** 查询。

	![图片 5653](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image36.png)

2. 将查询重命名为 **“Reseller”**。

3. 删除所有列，以下列除外：

	- ResellerKey

	- BusinessType

	- ResellerName

	- DimGeography

4. 展开 **“DimGeography”** 列，以便仅包括以下三列：

	- City

	- StateProvinceName

	- EnglishCountryRegionName

	![图片 5656](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image37.png)

5. 在 **“Business Type”** 列标题中，单击向下箭头，然后查看各个列的值，并注意 warehouse 是否存在拼写错误。

	![图片 2](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image38.png)

  
‎ 

6. 右键单击 **“Business Type”** 列标题，然后选择 **“替换值”**。

	![图片 4](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image39.png)

7. 在 **“替换值”** 窗口，配置以下值：

	- 在 **“要查找的值”** 框中，输入 **“Ware House”**

	- 在 **“替换对象”** 框，输入 **“Warehouse”**

	![图片 5](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image40.png)

8. 单击 **“确定”**。

	![图片 6](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image41.png)

9. 重命名以下四列：

	- 将 **“BusinessType”** 重命名为 **“Business Type”** （含空格）

	- 将 **“ResellerName”** 重命名为 **“Reseller”**

	- 将 **“StateProvinceName”** 重命名为 **“State-Province”**

	- 将 **“EnglishCountryRegionName”** 重命名为 **“Country-Region”**

10. 在状态栏中，确认查询具有 6 列和 701 行。

	![图片 5657](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image42.png)

### **任务 6：配置 Region 查询**

在此任务中，你将配置 **“Region”** 查询。

1. 选择 **“DimSalesTerritory”** 查询。

	![图片 5659](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image43.png)

2. 将查询重命名为 **“Region”**。

3. 向 **“SalesTerritoryAlternateKey”** 列应用筛选器以删除值 0（零）。

	![图片 5660](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image44.png)

4. 删除所有列，以下列除外：

	- SalesTerritoryKey

	- SalesTerritoryRegion

	- SalesTerritoryCountry

	- SalesTerritoryGroup

5. 重命名以下三列：

	- 将 **“SalesTerritoryRegion”** 重命名为 **“Region”**

	- 将 **“SalesTerritoryCountry”** 重命名为 **“Country”**

	- 将 **“SalesTerritoryGroup”** 重命名为 **“Group”**

6. 在状态栏中，验证查询是否具有 4 列和 10 行。

	![图片 5661](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image45.png)

### **任务 7：配置 Sales 查询**

在此任务中，你将配置 **“Sales”** 查询。

1. 选择 **“FactResellerSales”** 查询。

	![图片 5663](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image46.png)

2. 将查询重命名为 **“Sales”**。

3. 删除所有列，以下列除外：

	- SalesOrderNumber

	- OrderDate

	- ProductKey

	- ResellerKey

	- EmployeeKey

	- SalesTerritoryKey

	- OrderQuantity

	- UnitPrice

	- TotalProductCost

	- SalesAmount

	- DimProduct

	*回想一下，在 **“在 Power BI Desktop 中准备数据”** 实验室中，有一小部分 **“FactResellerSales”** 行缺少 **“TotalProductCost”** 值。为了修复缺少的值，已将 **“DimProduct”** 列包含在内，用于检索产品标准成本。*

4. 展开 **“DimProduct”** 列，取消选中所有列，然后仅包括 **“StandardCost”** 列。

5. 要创建自定义列，请在 **“添加列”** 功能区选项卡上的 **“常规”** 组中，单击 **“自定义列”**。

	![图片 5664](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image47.png)

6. 在 **“自定义列”** 窗口的 **“新列名”** 框中，将文本替换为 **“Cost”**。

	![图片 5665](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image48.png)

7. 在 **“自定义列公式”** 框中，输入以下表达式（等号后面的文本）：

8. 为了方便使用，你可以从 **D:\DA100\Labs\load-data-with-power-query-in-power-bi-desktop\Assets\Snippets.txt** 文件中复制表达式。


   **Power Query**
   ```
   if [TotalProductCost] = null then [OrderQuantity] * [StandardCost] else [TotalProductCost]
   ```


*此表达式用于测试 **“TotalProductCost”** 值是否缺失。如果缺失，则通过将 **“OrderQuantity”** 值乘以 **“StandardCost”** 值来生成一个值；否则，它使用现有的 **“TotalProductCost”** 值。*

9. 单击 **“确定”**。

	![图片 5666](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image49.png)

10. 删除以下两列：

	- TotalProductCost

	- StandardCost

11. 重命名以下三列：

	- 将 **“OrderQuantity”** 重命名为 **“Quantity”**

	- 将 **“UnitPrice”** 重命名为 **“Unit Price”** （含空格）

	- 将 **“SalesAmount”** 重命名为 **“Sales”**

12. 要修改列数据类型，请在 **“Quantity”** 列标题（位于列名称的左侧）中单击 **“1.2”** 图标，然后选择 **“整数”**。

	![图片 5667](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image50.png)

	*必须配置正确的数据类型。当列中包含数值时，如果想进行数学计算，也必须选择正确的类型。*

13. 将以下三列数据类型修改为 **“定点十进制数”**。

	- Unit Price

	- Sales

	- Cost

	![图片 5668](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image51.png)

	*定点十进制数数据类型以完整精度存储值，因此需要比十进制数更多的存储空间。务必为财务值或费率（例如汇率）使用定点十进制数类型。*

14. 在状态栏中，确认查询具有 10 列和超过 999 行。

	![图片 5669](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image52.png)

	*每个查询最多可加载 1000 行作为预览数据。*

### **任务 8：配置 Targets 查询**

在此任务中，你将配置 **“Targets”** 查询。

1. 选择 **“ResellerSalesTargets”** 查询。

	![图片 5672](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image53.png)

2. 将查询重命名为 **“Targets”**。

3. 若要逆透视 12 个月的列 (**“M01”**- **“M12”**)，请先多重选择 **“Year”** 和 **“EmployeeID”** 列标题。

	![图片 5673](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image54.png)

4. 右键单击任一选择列标题，然后在上下文菜单中选择 **“逆透视其他列”**。

	![图片 5674](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image55.png)

5. 请注意，列名称现在显示在 **“Attribute”** 列中，并且值显示在 **“Value”** 列中。

6. 将筛选器应用于 **“Value”** 列以删除连字符 (-) 值。

	*回想一下，在源 CSV 文件中使用连字符表示零 (0)。*

7. 重命名以下两列：

	- 将 **“Attribute”** 重命名为 **“MonthNumber”** （两个词之间没有空格，稍后会将其删除）

	- 将 **“Value”** 重命名为 **“Target”**

	*现在，你将应用转换来生成一个日期列。日期将从 **“Year”** 和 **“MonthNumber”** 列中得出。你将使用 **“示例中的列”** 功能来创建列。*

8. 要准备 **“MonthNumber”** 列值，请右键单击 **“MonthNumber”** 列标题，然后选择 **“替换值”**。

	![图片 5676](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image56.png)

9. 在 **“替换值”** 窗口的 **“要查找的值”** 框中，输入 **“M”**。

	![图片 5677](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image57.png)

10. 单击 **“确定”**。

11. 将 **“MonthNumber”** 列数据类型修改为 **“整数”**。

	![图片 5678](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image58.png)

12. 在 **“添加列”** 功能区选项卡上，从 **“常规”** 组内，单击 **“示例中的列”** 图标。

	![图片 5675](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image59.png)

13. 请注意，第一行对应年份 **“2017”** 和月份 **“7”**。

14. 在 **“Column1”** 列的第一个网格单元中，开始输入 **“7/1/2017”**，然后按 **Enter**。

	*由于虚拟机使用美国区域设置，因此此日期实际上将显示为 2020 年 7 月 1 日。*

15. 请注意，网格单元格会使用预测值进行更新。

	*该功能已准确预测你正在合并 **“Year”** 和 **“MonthNumber”** 列中的值。*

16. 还要注意查询网格上方显示的公式。

	![图片 5679](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image60.png)

17. 要重命名新列，请双击 **“已合并”** 列标题。

18. 将列重命名为 **“TargetMonth”**。

	![图片 5680](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image61.png)

19. 若要添加新列，请单击 **“确定”**。

	![图片 5681](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image62.png)

20. 删除以下列：

	- Year

	- MonthNumber

21. 修改以下列的数据类型：

	- 将 **“Target”** 修改为定点十进制数

	- 将 **“TargetMonth”** 修改为日期

22. 要将 **“Target”** 值乘以 1000，请选择 **“Target”** 列标题，然后在 **“转换”** 功能区选项卡上的 **“数字列”** 组内，单击 **“标准”**，然后选择 **“相乘”**。

	*回想一下，已存储了数千个目标值。*

	![图片 5682](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image63.png)

23. 在 **“相乘”** 窗口的 **“值”** 框中，输入 **“1000”**。

	![图片 5683](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image64.png)

24. 单击 **“确定”**。

	![图片 5684](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image65.png)

25. 在状态栏中，确认查询具有 3 列和 809 行。

	![图片 5685](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image66.png)

### **任务 9：配置 ColorFormats 查询**

在此任务中，你将配置 **“ColorFormats”** 查询。

1. 选择 **“ColorFormats”** 查询。

	![图片 5687](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image67.png)

2. 请注意，第一行包含列名。

3. 在 **“主页”** 功能区选项卡中，单击 **“转换”** 组内的 **“将第一行用作标题”**。

	![图片 5688](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image68.png)

4. 在状态栏中，确认查询具有 3 列和 10 行。

	![图片 5689](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image69.png)

### **任务 10：更新 Product 查询**

在此任务中，你将通过合并 **“ColorFormats”** 查询来更新 **“Product”** 查询。

1. 选择 **“Product”** 查询。

	![图片 5690](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image70.png)

2. 要合并 **“ColorFormats”** 查询，请在 **“主页”** 功能区选项卡上的 **“组合”** 组内，单击 **“合并查询”**。

	![图片 5654](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image71.png)

	*合并查询能够实现集成数据，在本例中，这些数据来自不同的数据源（SQL Server 和 CSV 文件）。*

3. 在 **“合并”** 窗口的 **“Product”** 查询网格中，选择 **“Color”** 列标题。

	![图片 5655](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image72.png)

4. 在 **“Product”** 查询网格下方的下拉列表中，选择 **“ColorFormats”** 查询。

	![图片 21](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image73.png)

5. 在 **“ColorFormats”** 查询网格中，选择 **“Color”** 列标题。

6. 当 **“私有级别”** 窗口打开时，对于两个数据源中的每一个，在相应的下拉列表中，选择 **“组织”**。

	![图片 5691](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image74.png)

	*可以为数据源配置隐私级别来确定数据是否可以在源之间共享。将每个数据源设置为 **“组织”** 允许它们共享数据（如有必要）。请注意，私有数据源永远不能与其他数据源共享。这并不意味着不能共享专用数据，这只是表示 Power Query 引擎无法在源之间共享数据。*

7. 单击 **“保存”**。

	![图片 5692](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image75.png)

8. 在 **“合并”** 窗口中，单击 **“确定”**。

	![图片 5693](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image76.png)

9. 展开 **“ColorFormats”** 列以包括以下两列：

	- Background Color Format

	- Font Color Format

	![图片 5694](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image77.png)

10. 在状态栏中，确认查询现在具有 8 列和 397 行。

	![图片 5695](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image78.png)

### **任务 11：更新 ColorFormats 查询**

在此任务中，你将更新 **“ColorFormats”** 以禁用其负载。

1. 选择 **“ColorFormats”** 查询。

	![图片 321](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image79.png)

2. 在 **“查询设置”** 窗格中，单击 **“所有属性”** 链接。

	![图片 322](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image80.png)

3. 在 **“查询属性”** 窗口中，取消选中 **“启用加载到报表”** 复选框。

	![图片 323](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image81.png)

	禁用加载意味着它将不会作为表加载到数据模型。这样做是因为查询已经与已启用的 **“Product”** 查询合并，以便加载到数据模型。

4. 单击 **“确定”**。

	![图片 324](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image82.png)

### **任务 12：完成**

在此任务中，你将完成实验室。

1. 验证你是否有 8 个按照如下命名的查询：

	- Salesperson

	- SalespersonRegion

	- Product

	- Reseller

	- Region

	- Sales

	- Target

	- ColorFormats（不会加载到数据模型中）

2. 要加载数据模型，请在 **“文件”** backstage 视图，选择 **“关闭并应用”**。

	![图片 326](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image83.png)

	*所有已启用加载的查询现已加载到数据模型。*

3. 在 **“字段”** 窗格（位于右侧）中，请注意已加载到数据模型的七个表。

	![图片 3](Linked_image_Files/02-load-data-with-power-query-in-power-bi-desktop_image84.png)

4. 保存 Power BI Desktop 文件。

5. 如果你打算开始下一个实验室，请让 Power BI Desktop 保持打开状态。

	*在 **“在 Power BI Desktop 中对数据建模，第 1 部分”** 实验室中，你将配置数据模型表和关系。*
