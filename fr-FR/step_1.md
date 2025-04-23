L'Intersection Observer est utilisé pour détecter quand un élément (par exemple `<img>`, `<p>` ou `<div>`) entre ou quitte la fenêtre du navigateur de l'utilisateur.

Il peut être utilisé pour déclencher des actions dans son rappel. Ces actions peuvent être sur l'élément observé, ou sur un autre élément de la page.

Voici un exemple d'utilisation de l' `intersection Observer` pour déclencher une action lorsqu'un élément avec un attribut id spécifique ('trigger') entre (ou quitte) la fenêtre d'affichage :

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
    // METTRE L'ACTION ICI
  }
});
triggerObserver.observe(document.querySelector("#trigger"));

--- /code ---

À la ligne 1, `entries` est une collection de tous les éléments de la page web avec l'attribut `id="trigger"` (comme spécifié dans l'appel de l'observateur à la ligne 6).

Une collection d'éléments est appelée un « tableau ».

Le `triggerObserver` est configuré pour observer lorsque le premier (dans ce cas : le seul) élément du tableau `entries` arrive dans la fenêtre d'affichage (en utilisant `isIntersecting` à la ligne 2).

Lorsqu'il le fait, l'observateur 'callback' exécute les actions spécifiées à la ligne 3.

Voici un exemple d'utilisation de l' `intersection Observer` pour déclencher une action lorsque **un** élément avec un attribut spécifique ('trigger') entre (ou quitte) la fenêtre d'affichage :

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
        // METTRE L'ACTION ICI
    }
  });
});
triggers.forEach((trigger) => imageObserver.observe(trigger));

--- /code ---
