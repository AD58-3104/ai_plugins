# ai_plugins

Claude Code の `~/.claude/settings.json`・`CLAUDE.md`・hooks を PC 間で共有するためのリポジトリ。

## セットアップ

```sh
git clone <this-repo> ~/ai_plugins
mkdir -p ~/.claude/hooks
cp ~/ai_plugins/settings.json ~/ai_plugins/CLAUDE.md ~/.claude/
cp ~/ai_plugins/hooks/* ~/.claude/hooks/
```

Claude Code を起動すると `extraKnownMarketplaces` / `enabledPlugins` に従ってプラグインが自動インストールされる。

## 反映(このリポジトリ → このPC の設定を更新した時)

```sh
sed "s|/home/$USER/.claude/hooks/|\$HOME/.claude/hooks/|" ~/.claude/settings.json > ~/ai_plugins/settings.json
cp ~/.claude/CLAUDE.md ~/ai_plugins/
cp ~/.claude/hooks/* ~/ai_plugins/hooks/
```
