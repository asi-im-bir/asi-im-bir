name: WakaTime Readme Stats

on:
  schedule:
    # Runs at 12 AM UTC every day
    - cron: '0 0 * * *'
  workflow_dispatch:

jobs:
  update-readme:
    name: Update Dev Metrics
    runs-on: ubuntu-latest
    steps:
      - uses: anmol098/waka-readme-stats@v2
        with:
          # This is the secret you created in Step 2
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          # This is the section where the metrics will be injected in your README.md
          SECTION_NAME: waka
          # Display the most used editors and operating systems
          SHOW_OS: "True" 
          SHOW_TIME_MACHINE: "True"
          SHOW_EDITORS: "True"
          SHOW_PROJECTS: "False" # Optional: set to True if you want to show projects
