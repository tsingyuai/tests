**任务说明书**

**任务要求**

对多篇pdf文件（10篇）进行信息挖掘工作。

具体地，用户会使用自然语言输入一个问题或任务，希望大模型能根据这10篇文档的内容作出回答。

为了实现精确地提取信息，你需要对pdf文件预处理，并设计工作流对每个文件逐一提取信息。如果文档过长，可能需要切分。最后，将每个文档的信息拼接在一起，完成对用户问题的回答或执行要求。

**建议完成时间**

72 h内

**成果形式**

Python服务，以RESTFUL API形式暴露接口，用户传入pdf目录字符串和问题，输出字符串形式的答案。

**提示：思路与工作流**

1. 对PDF文件进行预处理，将图片和文本提取出来，分开保存；

2. 构建提示词模板，基于用户的提问，编写提示词，获取需要分析和挖掘的指标是什么，注意，对于文本和图像的提示词可能不同；

3. 根据构建的提示词，对于每个PDF文件，分别以文本和图像作为输入，进行提问，基于商用的大模型API，完成信息获取，生成结构化表格，表格可以以json或markdown形式呈现；文本处理使用gpt-3.5-turbo；图片处理使用gpt-4o

4. 将结构化表格拼接在一起，需要具体回答用户问题。返回字符串。

**PDF文档示例**

VR/AR眼镜相关行研报告，见/PDF_example文件夹

**问题示例**

1. AR领域内的头部企业有哪些？

2. 总结VR产品的性能数据信息。 

3. 总结AR出货量每年的数据。
