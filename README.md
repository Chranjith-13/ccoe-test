For this particular scenario, I don't have much expertise so i tried to source the answers from google and found out that using JS, we can achieve the given requirement.

Method 1#

We can create a general method that access an element based on an array of property names that is interpreted as a path through the properties:

```javascript
function getValue(data, path) {
    var i, len = path.length;
    for (i = 0; typeof data === 'object' && i < len; ++i) {
        data = data[path[i]];
    }
    return data;
}

```

Then we could call it with:

```javascript
var a = getValue(b, ["c", "d"]);
```


Method 2#

```javascript
var object = {"a": { "b": { "c": "d" }}};

console.log("Result at 'a.b.c': ",_.get(object, 'a.b.c'));
console.log("Result at 'a.b.nonexistent key': ",_.get(object, 'a.b.nonexistent', "default result"));

var object2 = {"x":{"y":{"z":"a"}}};
console.log("Result at 'x.y.z': ",_.get(object2, 'x.y.z'));
```

```xml
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.11/lodash.js"></script>
```


Sample output:

`Result at 'a.b.c': d`

`Result at 'a.b.nonexistent key': default result`

`Result at 'x.y.z': a`


