# 瀑布流
## 瀑布流布局效果
![](https://upload-images.jianshu.io/upload_images/12904618-8434d6e6894619ca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

即多行等宽元素排列，后面的元素依次添加到其后，等宽不等高，根据图片原比例缩放直至宽度达到我们的要求，依次按照规则放入指定位置。

## 图解瀑布流算法
当第一排排满足够多的等宽图片时（如下图情况），自然而然的考虑到之后放置的图片会往下面排放。

![](https://upload-images.jianshu.io/upload_images/12904618-e8ca00f6a68cd60d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

那么第六张图片，放置在什么位置呢？是下图的位置么？

![](https://upload-images.jianshu.io/upload_images/12904618-c0ec0344aaa5572d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

我们通过瀑布流算法实验得到，后面紧跟的第六张图片的位置应该是这个位置。

![](https://upload-images.jianshu.io/upload_images/12904618-3831a23b5fa09225.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

为什么呢？
因为放置它之前，这一列的高度为所有列中最小，所以会放置在这个地方。
所以我们知道了，如果再继续放置下去，第七张图片应该是这个位置，对吗？

![](https://upload-images.jianshu.io/upload_images/12904618-c4ba20d0b9cca772.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

通过瀑布流算法实验得出位置正确。看懂这个图示应该就能理解了瀑布流的原理算法。

![](https://upload-images.jianshu.io/upload_images/12904618-8a01d8236519e745.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## 总结瀑布流布局原理
- 设置图片宽度一致
- 根据浏览器宽度以及每列宽度计算出列表个数，列表默认0
- 当图片加载完成，所有图片依次放置在最小的列数下面
- 父容器高度取列表数组的最大值