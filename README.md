### Hi there 👋
This is the place where I opensource stuff/do my job and break things :rofl:

- 🔭 I’m currently working on something cool :wink:
- 🌱 I’m currently learning all things related to web 🤪
- 💬 Ask me about anything related to Ruby/Javascript/Python
- 📫 How to reach me: [@erasu3](https://t.me/erasu3)
- ⚡ Fun fact: I :heart: :cat:s

📊 **This week I spent my time on**
<!--START_SECTION:waka-->
```text
Ruby    11 hrs 24 mins  ████████████████████████░   96.54 % 
YAML    12 mins         ░░░░░░░░░░░░░░░░░░░░░░░░░   01.70 % 
Other   7 mins          ░░░░░░░░░░░░░░░░░░░░░░░░░   01.10 % 
HTML    4 mins          ░░░░░░░░░░░░░░░░░░░░░░░░░   00.61 % 
Slim    0 secs          ░░░░░░░░░░░░░░░░░░░░░░░░░   00.02 %
```
<!--END_SECTION:waka-->

👨‍🏫 **You can create repo with your github Username and this board will appear on your profile page**


ℹ️ **Additional info**
1. [Wakatime](https://wakatime.com/integrations) for tracking your work

1.1 New to WakaTime

  WakaTime gives you an idea of the time you really spent on coding. This helps you boost your productivity and competitive edge.

  - Head over to <https://wakatime.com> and create an account.
  - Get your WakaTime API Key from your [Account Settings in WakaTime](https://wakatime.com/settings/account).
  - Install the [WakaTime plugin](https://wakatime.com/plugins) in your favourite editor / IDE.
  - Paste in your API key to start the analysis.

2. Profile repository setup flow

*If you're executing the workflow on your Profile Repository (`<username>/<username>`)*

> You wouldn't need an GitHub Access Token since GitHub Actions already makes one for you.

Please follow the steps below:

2.1. Go to your `<username>/<username>/actions`, hit `New workflow`, `set up a workflow yourself`, delete all the default content github made for you.

2.2. Copy the following code and paste it to your new workflow you created at step 1:
  ```yml
  name: Update stats

  on:
    schedule:
      # Runs at 12am UTC
      - cron: '0 0 * * *'
    workflow_dispatch:

  jobs:
    update-readme:
      name: Update Readme with Metrics
      runs-on: ubuntu-latest
      steps:
        - uses: athul/waka-readme@master
          with:
            WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
            GH_TOKEN: ${{ secrets.GH_TOKEN}}
            USERNAME: <username>
            SHOW_TITLE: false
  ```
2.3. Go to your repo secrets by hitting `Settings => Secrets` tab in your profile repo. You can also enter the url  https://github.com/USERNAME/USERNAME/settings/secrets . Please replace the `USERNAME` with your own username.

2.4. Create a new `Secret`. `Name`: `WAKATIME_API_KEY`, `Value`: Paste the Wakatime API key here. If you don't know what is the key, please go to  [Account Settings in WakaTime](https://wakatime.com/settings/account) to find your API Key there.

2.5. Add a comment to your `README.md` like this:

  ```md
  <!--START_SECTION:waka-->
  <!--END_SECTION:waka-->
  ```
2.6. Go to Workflows menu (mentioned in step 1), click `Waka Readme`, click `Run workflow`.

2.7. Go to your profile page. you will be able to see it. 

3. If you have any questions - send them to my public email or github issues :)
