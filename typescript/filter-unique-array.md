```javascript
private filterUnique(arg: any[]): any[] {
    const list = new Set();
    for (const item of arg) {
        list.add(item);
    }
    return Array.from(list);
}
```
