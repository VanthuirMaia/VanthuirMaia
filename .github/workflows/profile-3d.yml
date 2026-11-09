# Salvar em .github/workflows/profile-3d.yml no repo VanthuirMaia/VanthuirMaia
name: Profile 3D Contrib

on:
  schedule:
    - cron: "0 3 * * *" # todo dia, 00h em Fortaleza
  workflow_dispatch:

permissions:
  contents: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - uses: yoshi389111/github-profile-3d-contrib@latest
        env:
          # troque por secrets.PAT_3D se quiser contar contribuições privadas
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          USERNAME: ${{ github.repository_owner }}

      - name: Commit
        run: |
          git config user.name github-actions
          git config user.email github-actions@github.com
          git add -A .
          git commit -m "update 3d contrib" || exit 0
          git push
