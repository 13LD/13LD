#### [Wakatime](https://wakatime.com/integrations) for tracking your work

  1.1 If new to WakaTime

  WakaTime gives you an idea of the time you really spent on coding. This helps you boost your productivity and competitive edge.

  - Head over to <https://wakatime.com> and create an account.
  - Get your WakaTime API Key from your [Account Settings in WakaTime](https://wakatime.com/settings/account).
  - Install the [WakaTime plugin](https://wakatime.com/plugins) in your favourite editor / IDE.
  - Paste in your API key to start the analysis.

#### Profile repository setup flow

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

#### If you have any questions - send them to my public email or github issues :)
