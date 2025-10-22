交叉观察器用于检测元素（例如 `<img>`，`<p>` 或 `<div>`）何时进入或离开用户的浏览器视口。

它可用于在回调中触发操作。 这些操作可以作用于观察到的元素，或者页面上的其他元素。

下面是使用 `IntersectionObserver` 的示例，当具有特定 id 属性（“trigger”）的元素进入（或离开）视口时触发操作：

--- code ---
---
language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights: 
---

const triggerObserver = new IntersectionObserver((entries) => {
  if (entries[0].isIntersecting) {
    // 在此处执行操作
  }
});
triggerObserver.observe(document.querySelector("#trigger"));

--- /code ---

在第 1 行中，`entries`是网页上所有具有 `id="trigger"` 属性的元素的集合（如第 6 行的观察器调用中所指定）。

项目的集合称为“数组”。

设置 `triggerObserver` 来观察 `entries` 数组中的第一个（在本例中是唯一的）项目何时进入视口（使用第 2 行的 `isIntersecting`）。

当它发生时，观察器的回调将执行第 3 行指定的操作。

下面是使用 `IntersectionObserver` 的示例，当任何具有特定属性（“trigger”）的元素进入（或离开）视口时，触发操作：

--- code ---
---
language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights: 
---

const triggers = document.querySelectorAll("trigger");
const triggerObserver = new IntersectionObserver((entries) => {
  entries.forEach(
    (entry) => {
      if (entry.isIntersecting) {
        // 在此处执行操作
    }
  });
});
triggers.forEach((trigger) => imageObserver.observe(trigger));

--- /code ---
