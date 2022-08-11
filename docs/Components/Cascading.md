# Cascading
The Cascading is the component serving as a muti-levels menu which provides options for users to select. Same as the popular Cascading menu, our Cascading menu supports expansion and collapse according to the event of the cursor. Our Cascading menus based on a npm package called [mui-nested-menu](https://www.npmjs.com/package/mui-nested-menu), however we extract ChevronRight.js, IconMenuItem.js and NestedMenuItem.js to enable scrolling on nested menu. 

The essential inputs for Cascading menu is a nested [variable-tree](../Methods/Flat_Files.md) and a [option-flat](../Methods/Flat_Files.md). The Cascading menu does recursive call on the nested variable-tree and map each variable to the option-flat file to get a correct option label. 

Those selected variables from Cascading menus are stored for other components, for example [filter](../Components/Filter.md) and [table](../Components/Table.md). 

`isChildren(node)` -> check if the node is valid.
``` javascript
  function isChildren(key) {
    if (key) return true;
    else return false
  }
```

`isLast(node)` -> check if the node is last node/tail. 
```javascript
  function isLast(node) {
    return node === null
  }
```

`containsOnly(node)` -> check if `dict[key]` contains only one variable. If there is only one variable, the recursive call will automatically extract it out to one level up. 
```javascript
  function containsOnly(node) {
    if (Object.keys(node).length === 1)
      return true;
    return false;
  }
```

`renderTree(node)` -> This example is from FilterSelector, and the `renderTree` in ColumnSelector is quite similar with that in FilterSelector. renderTree does recursive calls to nested variable-tree and render the menu. 
```javascript
    const renderTree = (nodes) => {
        return (
            Object.keys(nodes).map((key) =>
                isChildren(key)
                    ? isLast(nodes[key])
                        ? <MenuItem value={key} key={key} onClick={() => { handleOptionClick(key) }}>
                            {options_flat[key].flatlabel}
                        </MenuItem>
                        : containsOnly(nodes[key])
                            ? renderTree(nodes[key])
                            : <NestedMenuItem
                                key={key}
                                label={options_flat[key].flatlabel}
                                parentMenuOpen={open}
                                onClick={handleClose}
                            >
                                {renderTree(nodes[key])}
                            </NestedMenuItem>
                    : null
            )
        )
    };
```
## Cascading in Filter (FilterSelector)
There are some differences between FilterSelector cascading menu and ColumnSelector cascading menu. 

`handleOptionClick` in FilterSelector set the `filter_obj` when clicking event happens. 
```javascript
const handleOptionClick = (key) => {
    handleClose();
    if (key in filter_obj) {
        alert("The variable has been selected.")
    }
    else {
        set_filter_obj({ ...filter_obj, [key]: [] })
    }

}
```

Also, another differnce is that FilterSelector takes first level as a button not a menu, which means if the dict[key] is the only level in nested variable-tree, the cascading menu will not pop out, and the click events will happens on the button. 
```javascript
<Button
    variant="text"
    onClick={() => handleOptionClick(key)}
    style={{ maxWidth: '280px', maxHeight: '30px', color: "#fff" }}
>
    {options_flat[key].flatlabel}
</Button>
```
## Cascading in Table (ColumnSelector)

`handleOptionClick` in ColumnSelector set the lists of visiable column options.
```javascript
const handleOptionClick = (option) => {
    setColumnVisibilityModel({...columnVisibilityModel, [option]: true})
    handleClose();
}
```