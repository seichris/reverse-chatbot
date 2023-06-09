### Objective of this project

We want to build a (**GramJS**) Telegram server that reads incoming messages, and uses a **GPT API** to generate responses. A **React or Nextjs web app** should give the user an overview of incoming and outgoing / proposed messages.

The **web app (React)** should allow users to log in to their Telegram account
The web app should allow users to switch between auto-message-mode and manual mode settings.
The web app should allow users to pause and start the bot for individual channels
The web app should allow users to provide context for the responses by sending additional instruction messages to the GPT API provider.
The web app should allow users to add / remove individual chats to groups. These groups share the same instruction message.

To achieve this, we will use **GramJS** to read message history, incoming messages and send responses.
This service will work in the background and does not require an invitation to a chat.
Which means we will use **gramJS** with a user account, not a bot account.

And we will query **GPT API** send texts and receive responses. We might need a database like **MongoDB** or Firebase to store messages and manage the bot's state. And in that database, each Telegram chat will have one corresponding GPT history.

### Tech stack

1. TG API credentials
2. GPT API credentials
3. React web app in this repo
4. GramJS (https://github.com/gram-js/gramjs):

I already built the UI in this repository. The Webapp should have these features:

- GramJS to authenticate the user and begin listening for incoming messages 
- GramJS event listener for incoming messages
- GramJS to generate responses using the GPT API. sendMessage method

- **Display chats with history of messages**: Keep track of the messages that your bot has responded to and display them in your web app. You can use a database like MongoDB or Firebase to store the messages and retrieve them for display.
![image](https://user-images.githubusercontent.com/25006584/226182890-64e47115-bb24-4e80-ac0b-6af9d0690324.png)

- **Allow users to provide an initial prompt**: Build a text input field where users can enter a message that will be sent to the GPT API. For example “Answer in a friendly way” or “answer in Chinese”. Allow our users to group each chat by keyword. So they can provide this context message once, to make it work for a few different chats.
![image](https://user-images.githubusercontent.com/25006584/226182843-ffb9046e-528c-48f8-9bec-08fa71e200a3.png)

- **Toggle auto-answering mode or manual mode per individual channel**: Build a feature into your web app that allows users to toggle between auto-answering mode and manual mode. In auto-answering mode, the bot will generate and send responses automatically, while in manual mode, the bot will propose a response in the UI and let the user send it. You can do this by storing the mode state for each channel in your database and checking this state when incoming messages are received.
![image](https://user-images.githubusercontent.com/25006584/226182869-90b96eba-18a6-47e2-893e-aeba3c7c6951.png)


---

This is a [Next.js](https://nextjs.org/) project bootstrapped with [`create-next-app`](https://github.com/vercel/next.js/tree/canary/packages/create-next-app).

## Getting Started

First, run the development server:

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `pages/index.js`. The page auto-updates as you edit the file.

## Learn More

To learn more about Next.js, take a look at the following resources:

- [Next.js Documentation](https://nextjs.org/docs) - learn about Next.js features and API.
- [Learn Next.js](https://nextjs.org/learn) - an interactive Next.js tutorial.

You can check out [the Next.js GitHub repository](https://github.com/vercel/next.js/) - your feedback and contributions are welcome!

## Deploy on Vercel

The easiest way to deploy your Next.js app is to use the [Vercel Platform](https://vercel.com/import?utm_medium=default-template&filter=next.js&utm_source=create-next-app&utm_campaign=create-next-app-readme) from the creators of Next.js.

Check out our [Next.js deployment documentation](https://nextjs.org/docs/deployment) for more details.
