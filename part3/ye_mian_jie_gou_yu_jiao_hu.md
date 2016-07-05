## 页面结构与交互

前端数据模型的定义示例: 

```
	var ctrlBathPath = ctx+'/goods';
	var app, viewModel, datas;
	var viewModel = {
		md: document.querySelector('#demo-mdlayout'),
		editoradd: '',
		searchText: ko.observable(''),
		searchFileds: ['productName','supplier'],
		mainDataTable: new u.DataTable({
			meta: {
				'productid':{
					type:'string'
				},
				'productName': {
					type: 'string'
				},
				'productNum': {
					type: 'integer'
				},
				'price': {
					type: 'float'
				},
				'supplier': {
					type: 'string'
				}, //供应商
				'proDate': {
					type: 'date'
				}, //生成日期
				'orgin': {
					type: 'string'
				} //原产地
			},
			pageSize: 10
		})
```


前后端交互ajax:  


![](/img/image019.jpg)
