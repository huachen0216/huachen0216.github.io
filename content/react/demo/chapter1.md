### React Demo 
#### 第一章 React相关概念

##### React的生命周期

1. 实例化

	* getDefaultProps
	* getInitialState
	* componentWillMount(重点)
	* render
	* componentDidMount

2. 存在期

	组件已存在时的状态改变
	* componentWillReceiveProps(重点)
	* shouldComponentUpdate
	* componentWillUpdate
	* render（重点）
	* componentDidUpdate

3. 销毁&清理期

	* componentWillUnmount（重点）

***

说明：生命周期共提供了10个不同的API，但在我们的代码中主要用到以下几个API

### componentWillMount 
	
在完成首次渲染之前调用，此时仍可以修改组件的state。
	
### componentWillReceiveProps

组件接收到新的props时调用，并将其作为参数nextProps使用，此时可以更改组件props及state。
```
	componentWillReceiveProps: function(nextProps) {
		if (nextProps.bool) {
        	this.setState({
            	bool: true
        	});
    	}
	}
```

### render

必选的方法，创建虚拟DOM，该方法具有特殊的规则：

+ 只能通过this.props和this.state访问数据
+ 可以返回null、false或任何React组件
+ 只能出现一个顶级组件（不能返回数组）	
+ 不能改变组件的状态
+ 不能修改DOM的输出

### componentWillUnmount

组件被移除之前被调用，可以用于做一些清理工作，在componentDidMount方法中添加的所有任务都需要在该方法中撤销，比如
创建的定时器或添加的事件监听器。

![](http://huachen0216.github.io/images/react_flow.png)
