# YYYY-MM-Daily-Standup template

## Tasks 📌

```dataviewjs
const tasks = dv.page(dv.current().file.path).file.tasks
    .sort(t => t.completed, 'asc');

if (tasks.length > 0) {
    dv.taskList(tasks);
}
```

## DD-MM-YYYY ↔️ DD-MM-YYYY

- Holiday! 🌴 😎

## DD-MM-YYYY 👈

- 
