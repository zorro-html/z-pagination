# `<z-pagination>`

Pagination with style, config  and event

## Import

```
<link rel="import" href="z-pagination/z-pagination.html">
```

## Attributes

- `value`: current page number, `1` by default
- `min`: min page number, `1` by default
- `max`: max page number, `1` by default
- `range`: how many numbers of pages shown around the current page, `-1` means show all, `-1` by default
- `siderange`: how many numbers of pages shown from beginning and ending, `-1` means show all, `0` by default

## Properties

- `value`: read / write current page number

## Methods

- `gotoPage(num)`: change current page and fire `changed` event if `value` changed
- `setConfig(config)`: set `min`, `max`, `range`, `siderange` at once
- `calcMax(unit, amount[, min])`: util method, get max page number by certain page unit and item amount

## Examples

### Show 3 pages beside the current page

```
<p>Now jump into page: <span id="pagination-number"></span></p>
<z-pagination id="z-pagination" max="20" value="7" range="3"></z-pagination>

<script>
  (function (global) {
    var pagination = document.querySelector('html /deep/ #z-pagination');
    var number = document.querySelector('html /deep/ #z-pagination-number');

    pagination.addEventListener('changed', function (e) {
      number.textContent = e.detail.value;
    });
  })(this);
</script>
```

### Show 1 page at beginning and ending

```
<p>Now jump into page: <span id="z-pagination-number2"></span></p>
<z-pagination id="z-pagination2" max="20" value="7" range="3" siderange="1"></z-pagination>

<script>
  (function (global) {
    var pagination = document.querySelector('html /deep/ #z-pagination2');
    var number = document.querySelector('html /deep/ #z-pagination-number2');

    pagination.addEventListener('changed', function (e) {
      number.textContent = e.detail.value;
    });
  })(this);
</script>
```

### Show all pages

```
<p>Now jump into page: <span id="z-pagination-number3"></span></p>
<z-pagination id="z-pagination3" max="10" value="3"></z-pagination>

<script>
  (function (global) {
    var pagination = document.querySelector('html /deep/ #z-pagination3');
    var number = document.querySelector('html /deep/ #z-pagination-number3');

    pagination.addEventListener('changed', function (e) {
      number.textContent = e.detail.value;
    });
  })(this);
</script>
```
