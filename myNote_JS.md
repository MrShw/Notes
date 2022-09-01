# React.Component 用法

组件(Components)允许您将 UI 拆分为独立的可重用的部分，并单独的考虑每个部分。

React.Component 是一个抽象基类。这意味着直接引用 React.Component 是毫无意义的。你可以实现一个它的子类，并且至少定义一个 render()方法即可使用。

实例内部属性

       props
       state

组件属性

    defaultProps
    displayName
    propTypes

每个组件还提供了一些其他 API：

    setState()
    forceUpdate()

当创建组件的实例并将其插入 DOM 时，会依次调用这些方法：

- constructor()
- componentWillMount()
- render()
- componentDidMount()
