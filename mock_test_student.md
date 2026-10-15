# MilcodeUni Mock Test: Weeks 1 to 4
### HTML, CSS, JavaScript, DOM, forms and validation

**Total: 100 points | Time: 2 hours | Taken alone, with your instructor watching your screen**

---

## Before you start

**Rules**
- You work alone. No AI, no chat, no phone.
- You may use your own lesson PDFs and the browser Console. You may **not** copy code from your old projects. Write everything again, in your own words.
- Use only what you have learned in the lessons.
- Read the points next to each exercise. Spend your time where the points are.
- If you get stuck, move on and come back later. A half-working answer still earns points.

**Setup (5 minutes)**
Open the folder `mock-test-starter`. Read its `README.md`. Copy it to a folder called `mock-test` and open it in VS Code.

**The story for the whole test:** a small restaurant called **Olive & Salt** needs a website where visitors can see the menu and book a table.

## How your time is split

| Part | Topic | Points | Suggested time |
|---|---|---|---|
| 1 | HTML | 15 | 20 min |
| 2 | CSS | 15 | 20 min |
| 3 | JavaScript basics | 20 | 20 min |
| 4 | DOM and events | 15 | 15 min |
| 5 | Forms and validation | 25 | 35 min |
| 6 | Explain your code (spoken) | 10 | 10 min |

---

# Part 1: HTML (15 points)
Work in `part-1/`.

**1.1 Repair the page (5 points, 1 per mistake)**
This page has exactly **5 mistakes**. Find them all and save the corrected page as `1-1-fixed.html`. Write a short comment above each fix saying what was wrong.

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Cafe Noor</title>
<body>
  <h1>Welcome to Cafe Noor
  <p>Open <strong>every day</p></strong>
  <ul>
    <li>Coffee
    <li>Tea</li>
  </ul>
  <img src="cafe.jpg">
</body>
</html>
```

**1.2 Semantic page (4 points)**
Create `1-2-page.html` for the restaurant **Olive & Salt**. It must have:
- the full page skeleton (`<!DOCTYPE html>`, `lang`, `charset`, `viewport`, `title`) (1 point)
- a `header` with an `h1` and a `nav` with 3 links (1 point)
- a `main` with 2 `section`s, each with an `h2` and a paragraph (1 point)
- a `footer`, and **no `<div>` anywhere** (1 point)

**1.3 A contact form (6 points)**
Create `1-3-form.html`: a contact form for a **driving school**. The form needs:
- Full name (text), email, phone (use the right input type for each), a **course** dropdown, a message box, and a submit button (2 points for the correct elements and types)
- Every field has a `<label>` connected with matching `for` and `id` (2 points)
- The dropdown has a first option with an **empty value** ("Choose a course") plus 3 real courses (1 point)
- The form has an `id`, every field has a `name`, and the button has `type="submit"` (1 point)

---

# Part 2: CSS (15 points)
Work in `part-2/`. The file `index.html` is given. You write **only `styles.css`**.

**2.1 Base styles and variables (4 points)**
- `box-sizing: border-box` on all elements (1 point)
- On `body`: a `background-color`, a `font-family` and a `line-height` (1 point)
- In `:root`: 3 color variables and 2 spacing variables (1 point)
- Use at least 3 of your variables with `var()`, for example on the buttons and headings (1 point)

**2.2 Navigation (3 points)**
Make the `nav` a row with Flexbox. Add a gap between the links and align them vertically in the middle.

**2.3 Responsive cards (5 points)**
The 3 cards (`.card` inside `.cards`) must be:
- stacked in **1 column** on a phone (1 point)
- in **3 columns** from 768px wide, using **one** media query (2 points)
- separated by a gap (1 point)
- styled as cards: a border, rounded corners and padding (1 point)

Test it in DevTools at 375px and at desktop width.

**2.4 Find the 3 CSS mistakes (3 points, 1 per mistake)**
This CSS has exactly **3 mistakes**. Write the corrected version in a comment at the bottom of your `styles.css`, with one sentence about each.

```css
:root {
  --primary: #4f46e5;
}

.card {
  background-color: #ffffff
  padding: 16px;
  border: 1px solid #dddddd;
}

.title {
  color: var(--main-color);
}

.row {
  display: flex;
  justfy-content: center;
}
```

---

# Part 3: JavaScript basics (20 points)
Work in `part-3/part-3.js`. Check your answers in the Console or with `node part-3.js`.

**3.1 Predict the output (4 points, 1 each)**
Write your prediction in a comment **first**, then run it.
```javascript
console.log(10 === "10");
console.log(typeof "7");
console.log(3 > 2 && 5 < 4);
console.log("Total: " + 2 + 3);
```

**3.2 Fix the type bug (3 points)**
A fee was stored as text, so the total is wrong. We want to print `Total: 13`.
```javascript
const tableFee = "10";
const guests = 3;
console.log("Total: " + (tableFee + guests));
```
- Fix it (1 point). Print the result with a template literal (1 point).
- In one sentence, explain why it was wrong (1 point).

**3.3 Discount function (4 points)**
Write `getDiscount(total)`:
- 100 or more: returns 10 (percent)
- 50 or more (but under 100): returns 5
- less than 50: returns 0

Points: a function with a parameter (1), it uses `return` and not `console.log` (1), correct `if / else if / else` with the right limits (1), you call it with 30, 50 and 120 and print the results (1).

**3.4 Array of objects (4 points)**
Create an array of 3 dishes, each an object with `name` and `price`. Then:
- print the name of the **second** dish (1)
- add a fourth dish with `.push()` (1)
- print how many dishes there are with `.length` (1)
- use a `for` loop to calculate and print the total price of all dishes (1)

**3.5 Trace the code (3 points, 1 each)**
Without running it, write what each line prints. Then run it to check.
```javascript
function check(age, hasTicket) {
  if (age < 12) {
    return "free";
  }
  if (hasTicket) {
    return "welcome";
  }
  return "buy a ticket";
}

console.log(check(8, false));
console.log(check(30, true));
console.log(check(30, false));
```

**3.6 Debug it (2 points)**
We want `1` to be printed, but it prints `0`.
```javascript
let count = 0;

function addGuest() {
  count + 1;
}

addGuest();
console.log(count);
```
Fix it (1 point) and explain the mistake in one sentence (1 point).

---

# Part 4: DOM and events (15 points)
Work in `part-4/`. The file `index.html` is given (do not change it). You write **only `script.js`**.

**4.1 Change the title (2 points)**
Select the heading with the id `page-title` and change its text to `Today's menu`.

**4.2 Create the menu (5 points)**
Create an array of 3 dishes (objects with `name` and `price`). With a `for` loop, create **one `article` element per dish**, give it the class `card`, set its text to `Grilled fish: $18` (use your own data and a template literal) and add it to the section with the id `menu`.
Points: the array (1), the loop with `.length` (1), `createElement` and the class (1), the text with a template literal (1), `appendChild` (1).

**4.3 Highlight button (3 points)**
When the button `#highlight-btn` is clicked, toggle the class `highlight` on **all** the cards. Clicking again removes it.
Points: the click listener (1), `querySelectorAll` inside the handler (1), a loop with `classList.toggle` (1).

**4.4 Find the 3 mistakes (3 points, 1 per mistake)**
This code should highlight the cards when the button is clicked. It has exactly **3 mistakes**. Write the corrected version in a comment at the bottom of your `script.js`, with one sentence for each.
```javascript
const button = document.querySelector("highlight-btn");
button.addEventListener("click", highlightAll());

function highlightAll() {
  const cards = document.querySelectorAll(".card");
  cards.textContent = "Selected";
}
```

**4.5 Live counter (2 points)**
When the visitor types in the input `#message`, show the number of characters in the paragraph `#char-info`, for example `5 characters`. Update it on every key press.

---

# Part 5: Forms and validation (25 points)
Work in `part-5/`. The files `index.html` and `styles.css` are given. You write **everything in `script.js`**, from an empty file.

The page is a **table booking form** with 6 fields: name, email, phone, number of guests, time, and special requests. Each field has an error paragraph (for example `#name-error`). The form is `#booking-form`. The summary paragraph is `#summary` and the WhatsApp link is `#whatsapp-link`. Both start hidden with the class `hidden`. Open `index.html` and read it first.

**5.1 Read the form (3 points)**
- On submit, stop the page from refreshing (1)
- Read all 6 values (1)
- Clean the text values with `.trim()`, and read the guests as a number (1)

**5.2 Validation rules (8 points)**
| Field | Rule | Points |
|---|---|---|
| Name | not empty, not even spaces | 1 |
| Email | must contain an `@` | 1 |
| Phone | at least 9 characters | 1 |
| Guests | a number from **1 to 6**. An empty box is also wrong | 2 |
| Time | the visitor must choose one (the first option is empty) | 1 |
| Time | the time **20:00 is full**. Keep the full times in an array and use `.includes()`. Show a different message | 1 |
| Special requests | optional, but **at most 100 characters** | 1 |

**5.3 Show the errors (5 points)**
- Each error appears in its own paragraph, under its own field (1)
- Old errors disappear when the visitor submits again (2)
- Only the wrong fields show an error. Valid fields show nothing (1)
- Nothing is printed in the Console, and the page keeps what the visitor typed (1)

**5.4 Success (3 points)**
If everything is valid:
- Show the `#summary` paragraph with: `Table for 4 at 19:00 booked for Sara.` (with the real values) (1)
- Build a WhatsApp message with the name, phone, guests, time and requests, turn it into a link with `encodeURIComponent`, and show the link (2). Use this start for the address: `https://wa.me/212600000000?text=`

**5.5 Save a draft (6 points)**
- Save all 6 fields in `localStorage` while the visitor types (2)
- Restore them when the page opens (2)
- Remove the draft after a successful booking (1)
- The **Clear draft** button empties the form and removes the saved draft (1)

**Test yourself before you finish** (your instructor will do the same tests):
1. Submit an empty form: you see 5 errors.
2. Fill only the name, submit again: only the name error disappears.
3. Try 7 guests, 0 guests, the time 20:00, a phone with 8 characters, an email without `@`.
4. Type half a form, refresh the page: it comes back.
5. Submit a valid form: the summary and the link appear, and the draft is gone after a refresh.

---

# Part 6: Explain your code (10 points)
Your instructor will ask you 5 questions about **your own code** from Part 5. Each answer is worth 2 points. You explain it aloud, with your code on the screen. If you cannot explain a line you wrote, you cannot get the points for it, so rewrite anything you do not understand before you finish.

---

## When you finish
- Check the Console for red errors on every page.
- Make sure every file is saved in the right folder.
- Tell your instructor you are ready.

## A note on honesty
This test is not for grading you as a person. It shows you and your instructor exactly what to practice next. A wrong answer you attempted alone helps you more than a correct answer you copied.

**MilcodeUni** | milcodeuni.tech
