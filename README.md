# English Learning Game — Demo 3-1

Demo 3-1 is a rebuilt version of Demo 3 with the requested upgrades.

## 1. Writing — structure-based checking

Writing no longer depends on one exact answer.

Each writing question has:

- `template`
- `requirements.subjects`
- `requirements.verbs`
- `requirements.keywords`
- `requirements.punctuation`
- `requirements.minWords`
- `sampleAnswer`

Example:

```js
template: "I + verb + after school.",
requirements: {
  subjects: ["i"],
  verbs: ["do", "play", "watch", "read"],
  keywords: ["after school"],
  punctuation: ".",
  minWords: 4
}
```

A student's answer can be different from the sample answer and still be accepted if it meets the configured requirements.

## 2. Writing — multiple checking levels

The game displays:

- ✓ / ✗ Subject
- ✓ / ✗ Verb
- ✓ / ✗ Keyword
- ✓ / ✗ Punctuation
- ✓ / ✗ Word count

If the answer is wrong, the question remains active. The sample answer is shown and the student must rewrite it before moving on.

## 3. Unscramble — direct editing

Click any selected word in the sentence area to return it to the Word Bank.

The selected words also receive immediate position feedback:

- green = correct position
- red = wrong position

## 4. Multiple Choice — Retry

A wrong answer does not immediately finish the question.

- Attempt 1: Try again
- Attempt 2: one more try
- Attempt 3: correct answer is revealed and the question ends

Only a correct answer earns the point/star.

## 5. Stars

There are three stars.

Each correctly completed question earns one star until the maximum of three is reached.

## 6. Result breakdown

The result screen reports:

- Multiple Choice
- Unscramble
- Writing

with correct answers / total attempted.

## 7. Theme system

Five pastel themes are included:

- Candy
- Sky
- Mint
- Sunshine
- Lavender

The selected theme is saved in `localStorage`, so it remains after refresh.

## 8. Background image

Open `style.css` and find:

```css
--game-background-image: none;
```

To use an image:

```css
--game-background-image: url("images/background.jpg");
```

The pastel gradient remains as a fallback underneath.

## 9. Add more questions

For Multiple Choice:

```js
{
  type: "multipleChoice",
  question: "Your question",
  choices: ["A", "B", "C", "D"],
  answer: "B"
}
```

For Unscramble:

```js
{
  type: "unscramble",
  question: "Put the words in the correct order.",
  words: ["is", "This", "book", "a"],
  answer: ["This", "is", "a", "book"]
}
```

For Writing:

```js
{
  type: "writing",
  question: "Write one sentence.",
  template: "I + verb + every day.",
  requirements: {
    subjects: ["i"],
    verbs: ["play", "read", "study"],
    keywords: ["every day"],
    punctuation: ".",
    minWords: 4
  },
  sampleAnswer: "I read every day."
}
```

## Note

This writing checker is deliberately rule-based. It checks the structure configured by the teacher; it is not a full grammar or AI evaluator.
