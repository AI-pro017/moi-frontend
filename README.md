# Mother of Invention Baby Name Generator (Frontend)

An AI baby name generator built for Mother of Invention. Parents answer a few quick questions and get a list of name ideas that fit what they're looking for, with the names appearing on screen as they're generated.

The names come from [moi-backend](https://github.com/AI-pro017/moi-backend), which runs the AI side.

## How it works

1. You pick the baby's gender, a preferred name origin (anything from Irish or Japanese to Elvish or Hogwarts), a theme or meaning, popular or unique, any names to skip, and whether you'd like a name with a nickname.
2. If you add a due date, the app works out the baby's star sign and includes it in the request. You can tick "I'm not pregnant yet" to skip this.
3. While the names load, there's an optional sign up for the Mother of Invention mailing list. It only shows once per browser.
4. Names stream in live from the backend using server sent events, with the zodiac sign shown at the top.

## Tech stack

- Next.js 15 (App Router), React 19 and TypeScript
- Tailwind CSS with custom Futura and Copper fonts
- validator for the email form

## Running it locally

```bash
git clone https://github.com/AI-pro017/moi-frontend.git
cd moi-frontend
npm install
npm run dev
```

Open http://localhost:3000.

The backend address is currently hardcoded to the deployed Render service in `src/app/page.tsx` (the `/generate` stream) and `src/components/user_email.tsx` (the `/user` sign up). Change both if you want to run against a local copy of the backend.

## Project structure

```
src/
  app/              Layout, SEO metadata and the main page
  components/
    user_form.tsx         The questionnaire
    user_email.tsx        Newsletter sign up
    waiting.tsx           Loading screen with the zodiac sign
    generated_names.tsx   Streamed results
  context/          Shared form state and streamed results
  utils/            Zodiac sign lookup from the due date
public/             Logos, images and fonts
```
