De intersection observator wordt gebruikt om te detecteren wanneer een element (bijv. `<img>`, `<p>` of `<div>`) de browserviewport van de gebruiker binnenkomt of verlaat.

Het kan worden gebruikt om acties in de callback te activeren. Deze acties kunnen betrekking hebben op het waargenomen element, of op een ander element op de pagina.

Hier is een voorbeeld van het gebruik van `IntersectionObserver` om een actie te activeren wanneer een element met een specifiek id-attribuut ('trigger') de viewport binnenkomt (of verlaat):

## --- code ---

language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights:
-----------------------------------------------------

const triggerObserver = new IntersectionObserver((entries) => {
if (entries[0].isIntersecting) {
// PLAATS ACTIE HIER
}
});
triggerObserver.observe(document.querySelector("#trigger"));

\--- /code ---

Op regel 1 is `entries` een verzameling van alle elementen op de webpagina met het kenmerk `id="trigger"` (zoals gespecificeerd in de observator-aanroep op regel 6).

Een verzameling items wordt een 'array' genoemd.

De `triggerObserver` is ingesteld om te observeren wanneer het eerste (in dit geval, het enige) item in de `entries`-array in de viewport verschijnt (met behulp van `isIntersecting` op regel 2).

Wanneer dit het geval is, voert de observator's callback de acties uit die op regel 3 zijn gespecificeerd.

Hier is een voorbeeld van het gebruik van `IntersectionObserver` om een actie te activeren wanneer **een willekeurig** element met een specifiek kenmerk ('trigger') de viewport binnenkomt (of verlaat):

## --- code ---

language: js
filename:
line_numbers: true
line_number_start: 1
line_highlights:
-----------------------------------------------------

const triggers = document.querySelectorAll("trigger");
const triggerObserver = new IntersectionObserver((entries) => {
entries.forEach(
(entry) => {
if (entry.isIntersecting) {
// PLAATS ACTIE HIER
}
});
});
triggers.forEach((trigger) => imageObserver.observe(trigger));

\--- /code ---
