[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://makeapullrequest.com)

# Deploy your own Candy Machine easily

This repository is for Candy Machine V3, Account Version V2. (This is what you have when using the latest sugar version to create the candy machine)

# How to use

## Prerequisites

- [pnpm](https://pnpm.io/installation) as package manager - I used 8.1.0
- [sugar](https://docs.metaplex.com/developer-tools/sugar/guides/sugar-for-cmv3) to create your candy machine

## How to use

1. Clone this repo
2. Run `pnpm install`
3. copy the `.env.example` file to a new `.env` file and fill in the NEXT_PUBLIC_CANDY_MACHINE_ID value. You should have this value after creating your candy machine with sugar.
4. Run `pnpm run dev`
5. Open your browser at `http://localhost:3000`
6. Connect your wallet which you used to create the candy machine
7. You should see a red `initialize` button. Click it and then click `create LUT`
8. Copy the LUT address that you see in the green success box and paste it into the `.env` file as the value for `NEXT_PUBLIC_LUT`
9. Add your candy machine groups to the `settings.tsx` file. E.g. if one of your groups is called `WL` you should have an entry for it in there, too
10. Deploy your Candy Machine e.g. to Vercel or Cloudflare Pages

Done!

### customization

You can customize the UI by changing the code. If you just want to modify some values you can instead

- modify `settings.tsx` to change the texts and Image.
  - `image` is the main image that is shown. You could change it to your project logo.
  - `headerText` is the website header. You could change it to your project name.
- Decide if you want to allow multiple mints by a single user at the same time and in your `.env` file set `NEXT_PUBLIC_MULTIMINT` accordingly to `true` or `false`

### Fees

This ui has a buy me a beer feature. Each mint will transfer a very small amount (0.005) of SOL to a tip wallet. If you do not want to support me feel free to change the NEXT_PUBLIC_OZONETHANKS variable to false. I would appreachiate it though if you leave it on. 🍻

This is not an official project by the Metaplex team. You can use that code at your own risk. I am not responsible for any losses that you might incur by using this code.
