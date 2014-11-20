# pagination

翻页器

## 特性

* `value`: 当前页码，默认为 1
* `min`: 最小页码，默认为 1
* `max`: 最大页码，默认为 1
* `range`: 从当前页码为中心展示的页码范围，负数表示展示所有页码，默认为 -1
* `siderange`: 从最小和最大页码为起点展示的页码范围，负数表示展示所有页码，默认为 0

## 属性/方法

### `value`

当前的页码，可读写

### `gotoPage(num)`

设置当前的页码，这时如果页码有改动会触发 `changed` 事件

### `setConfig(config)`

参数：`config` 可包含 `min`, `max`, `range`, `siderange`

### `calcMax(unit, amount[, min])`

工具方法，根据每页的单位、总数量和最小页码计算出最大页码

# Example

```
<jie-pagination max="9" value="3" range="3"></jie-pagination>

<script>
  var pagination = document.querySelector('jie-pagination');

  pagination.addEventListener('changed', function (event) {
    // event.detail.value
  });
</script>
```
