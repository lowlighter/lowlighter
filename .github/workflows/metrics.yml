# Licensed under The Unlicense
# Feel free to reuse, edit and redistribute this workflow as you wish, no credits needed
# See https://github.com/lowlighter/metrics for documentation about how to use metrics action

name: Metrics
on:
  # 🌏 Think about the planet! No need to update stats too frequently
  schedule: [{cron: "0 16 * * *"}]
  # 💡 The following line lets you run workflow manually from the action tab!
  workflow_dispatch:
jobs:
  metrics:
    runs-on: ubuntu-latest
    steps:

      - name: 🦑 Medias
        if: ${{ success() || failure() }}
        uses: lowlighter/metrics@latest
        with:
          filename: medias.svg
          token: ${{ secrets.TOKEN }}
          base: ""
          config_order: anilist, music
          output_action: gist
          committer_gist: ${{ secrets.GIST }}
          plugin_anilist: yes
          plugin_anilist_medias: anime
          plugin_anilist_sections: favorites, characters
          plugin_anilist_limit: 2
          plugin_anilist_limit_characters: 22
          plugin_music: yes
          plugin_music_playlist: ${{ secrets.PLAYLIST }}
          plugin_music_limit: 9

      - name: 🦑 Achievements
        if: ${{ success() || failure() }}
        uses: lowlighter/metrics@latest
        with:
          filename: achievements.svg
          token: ${{ secrets.TOKEN }}
          base: ""
          output_action: gist
          committer_gist: ${{ secrets.GIST }}
          plugin_achievements: yes
          plugin_achievements_display: compact
          plugin_fortune: yes

      - name: 🦑 Sponsors
        if: ${{ success() || failure() }}
        uses: lowlighter/metrics@latest
        with:
          filename: sponsors.svg
          token: ${{ secrets.TOKEN }}
          base: ""
          output_action: gist
          committer_gist: ${{ secrets.GIST }}
          plugin_sponsors: yes
          plugin_sponsors_past: yes
          plugin_sponsorships: yes
          plugin_sponsorships_sections: amount

      - name: 🦑 General
        if: ${{ success() || failure() }}
        uses: lowlighter/metrics@latest
        with:
          filename: general.svg
          token: ${{ secrets.TOKEN }}
          base: header
          base_indepth: yes
          config_order: base.header, isocalendar, languages, notable, discussions, topics
          output_action: gist
          committer_gist: ${{ secrets.GIST }}
          plugin_isocalendar: yes
          plugin_languages: yes
          plugin_languages_ignored: html, css, tex, less, dockerfile, makefile, qmake, lex, cmake, shell, gnuplot, vue, scala, c, c++, python, ejs
          plugin_languages_details: lines, bytes-size, percentage
          plugin_languages_sections: most-used, recently-used
          plugin_languages_indepth: yes
          plugin_languages_limit: 2
          plugin_topics: yes
          plugin_topics_limit: 0
          plugin_topics_mode: icons
          plugin_notable: yes
          plugin_discussions: yes
          
      - name: 🦑 Splatoon
        uses: lowlighter/metrics@latest
        if: ${{ success() || failure() }}
        with:
          filename: splatoon.svg
          token: ${{ secrets.TOKEN }}
          base: ""
          output_action: gist
          committer_gist: ${{ secrets.GIST }}
          plugin_splatoon: yes
          plugin_splatoon_token: ${{ secrets.SPLATOON_TOKEN }}
          plugin_splatoon_statink: yes
          plugin_splatoon_statink_token: ${{ secrets.SPLATOON_STATINK_TOKEN }}
          plugin_splatoon_sections: salmon-run
          plugin_splatoon_salmon_limit: 2
          extras_css: |
            h2 { display: none !important; }
            .match:not(:last-child) { padding-bottom: 4px; }
