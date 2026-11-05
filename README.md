# Marathon Game

A customizable trivia board game for the table. Six categories, one random category per turn, and every question card is written on demand by an AI model you choose (Gemini, Claude or ChatGPT), so you never run out of fresh cards.

The whole app is a single file, `index.html`. No build step, no dependencies, no server.

## How it plays

- **Six categories, six colors.** Each turn a random category is dealt. Rename any category, narrow its topics, set its level, or swap it for something else (a country, a hobby, a TV show).
- **Four levels per category:** Casual, Standard, Hard, Expert.
- **Typed answers by default.** If a player misses, the next player gets a try. A fuzzy matcher forgives typos and accents, and a "Count it as correct" button overrides it. Multiple choice is optional.
- **Closest-guess cards.** Every so often everyone estimates a number (for example, how many years ago the last mammoths died out) and the closest guess wins.
- **A curious fact** appears with every answer.
- **Race to the finish.** Every correct answer moves you 1 km. The game ends when someone reaches the goal: 10 km, 21 km, 42 km, or any distance you type.
- **Bonus round.** Collect all six category wedges to earn three bonus questions in your favorite category.
- **Animated trail** at the bottom shows every player climbing from the river valley to a snowy summit flag.
- Spanish and English interface, light and dark themes, wheel sound effects, and 1 to 6 players.

## Run it

1. Open `index.html` in a browser, or host it with GitHub Pages.
2. In **Setup**, pick who writes the cards and paste that provider's API key:
   - **Gemini**: free tier with daily limits. Create a key in [Google AI Studio](https://aistudio.google.com/apikey).
   - **Claude**: paid API (cents per batch of cards). Create a key in the [Anthropic Console](https://console.anthropic.com/settings/keys). It is separate from a Claude subscription.
   - **ChatGPT (OpenAI)**: paid API. Create a key on the [OpenAI platform](https://platform.openai.com/api-keys). It is separate from a ChatGPT subscription.
3. Go back to **Play** and deal a card.

Each provider keeps its own key and model. If you get a model error, tap **Find available models** in Setup and pick one from the list. Defaults: `gemini-3.5-flash-lite`, `claude-sonnet-5-5`, `gpt-6-luna`.

## Privacy

Your API key and settings are stored only in your browser (`localStorage`). Each key is sent only to its own provider to write cards. Nothing is stored on a server. If you publish this page, each visitor uses their own key.

## Limits

- The free Gemini tier has per-minute and daily limits. If you hit one, wait a moment and try again.
- Cards are written by an AI and can contain mistakes. The note under each answer helps you check.

## Customizing

All the code lives in `index.html`: styles at the top, then the interface texts, the category library, the game logic, and the Gemini request. Edit the file with any text editor.
