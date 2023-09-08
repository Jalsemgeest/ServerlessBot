## Serverless Discord Bot

### Note: This repo is heavily based off of the repo by imptype here: https://github.com/imptype/serverless-chatgpt-discord-bot

I found that the repo that this is based off of was not working when I tried it out, I think it was based off of an old version of discohook.

In order to run this in deta.space you need to do the following:

1. Create an account at deta.space.
2. Download this code and create a deta space project within this directory using `space new`.
3. Create a discord app and copy the necessary fields into the example.env file and rename it to .env.
4. Run `space push` to push the file to deta.space.
5. Once the program is running, then copy the builder instance address: `https://<builder-id>.deta.app/bot/interactions` and add it to your Discord app's INTERACTIONS ENDPOINT URL.
6. Then go to your builder's url config: `https://<builder-id>.deta.app/bot/api/dash`. You will then need to open up the console and paste the contents of `dashworker.txt` into it to override some Javascript. It's because `discohook` assumes it's the root API, but it's hosted under the `/bot` endpoint. So we need to update the functions to respect that.
7. Enter the password `jakeiscool` - unless you've updated it within the `main.py` file, then enter that password instead :)
8. Then it should work!