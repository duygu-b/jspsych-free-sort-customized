# jsPsych Free Sort (Fixed Location Version)

This is a modified version of the original `jsPsych-free-sort` plugin.  
The main difference is that images are **positioned at pre-defined coordinates** instead of being randomly placed on the canvas.

## What This Plugin Does

- Allows precise control over the initial positions of draggable elements (images, words, etc.)
- Maintains all core features of the original free-sort plugin
- Ideal for tasks requiring spatial memory, attention tracking, or visual categorization

## Key Modifications

- Added support for fixed `x` and `y` coordinates for each item
- Removed the default random placement behavior
- Optionally includes boundary constraints if needed

## Tested With

- jsPsych version 7.3.0
- Chrome & Firefox (desktop)

## Files

- `plugin-free-sort-fixed.js` → the main modified plugin
- `example.html` → a minimal working demo

## Usage Example

```javascript
```javascript
const sorting_stimuli = [
  "images/horse.png",   
  "images/napkin.png",   
];

const start_positions = [
  { x: 100, y: 100 },
  { x: 300, y: 100 }

];

const sort_trial = {
  type: jsPsychFreeSort,
  stimuli: sorting_stimuli,
  start_positions: start_positions,
  stim_width: 80,
  stim_height: 60,
  sort_area_width: 500,
  sort_area_height: 500,
  stim_starts_inside: true,
  prompt: "<p>Click and drag the images below to sort them so that similar items are close together.</p>"
};

jsPsych.run([sort_trial]);
