# Open-source church check-in

A kids check-in kiosk for your church. Parents check children in on a tablet and get a pickup code; your children's ministry team sees who is in the room right now.

This repository is the **Children Check-in** edition of [Church4Christ](https://github.com/leveo/church4christ), an open-source
church management system and website. It contains no separate code: the quick start below
installs Church4Christ v1.4.0 with only the Children Check-in features switched on (People & Households, Children Check-in).
Everything else stays off until you turn it on.

**[Try the live demo](https://church4christ.yunfei-song.com/en/sandbox)** · [Main repository](https://github.com/leveo/church4christ) · [Setup guide](https://github.com/leveo/church4christ/blob/v1.4.0/docs/setup.md)

## What you get

- **Self-serve kiosk on any tablet browser.** A parent searches by a child's name or their own phone number, taps the children they are dropping off, and checks in.
- **Pickup codes instead of badge printers.** Each check-in gets a 4-character code shown on screen; siblings checked in together share one code, and the code guards checkout.
- **A live roster for staff.** The Today tab lists every check-in with its code and times, with one-click staff checkout when a parent has lost the code.
- **Real numbers.** The dashboard shows this week's count, a 4-week average, distinct children this month, and a 12-week attendance chart.
- **Your classes, your schedule.** Add a class or service, optionally tied to a weekday; retiring one removes it from the kiosk and keeps its history.
- **Lost tablet? Regenerate the link.** The kiosk runs from a private URL; regenerating it shuts the old device out immediately.
- **Families come from People & Households.** Every child recorded under a household can check in; CSV import brings your existing family list in.
- **English and Chinese.** The kiosk switches language with one tap.

## Screenshots

![The kiosk: a parent finds their household by name or phone](https://raw.githubusercontent.com/leveo/church4christ/v1.4.0/docs/images/public/kiosk-search.png)

![The pickup code shown right after check-in](https://raw.githubusercontent.com/leveo/church4christ/v1.4.0/docs/images/public/kiosk-code.png)

![Children's ministry dashboard with the 12-week attendance chart](https://raw.githubusercontent.com/leveo/church4christ/v1.4.0/docs/images/admin/children-dashboard.png)

![Today's live roster with pickup codes and staff checkout](https://raw.githubusercontent.com/leveo/church4christ/v1.4.0/docs/images/admin/children-today.png)

## Try the live demo

Open the [public sandbox](https://church4christ.yunfei-song.com/en/sandbox). Choose **Administrator**, then open **Children** in the admin menu. The **Kiosk** tab opens the tablet view. All data is fictional and resets every night.

## Quick start

You need [Git](https://git-scm.com/) and [Node.js](https://nodejs.org/) 22.22.1 or newer.
These commands work in macOS and Linux terminals and in Windows PowerShell.

```bash
git clone --depth 1 --branch v1.4.0 https://github.com/leveo/church4christ.git my-church
cd my-church
npm ci
npm run onboard -- --preset checkin
```

`npm run onboard` opens a local form in your browser for your church's name, colors, logo,
and first administrator, with the Children Check-in features already checked. Save the form, press
Ctrl+C in the terminal, then apply it and start the site:

```bash
node scripts/setup/index.mjs --preferences .church/preferences.json --yes --dry-run
node scripts/setup/index.mjs --preferences .church/preferences.json --yes
npm run dev
```

Prefer the terminal only? Run `npm run setup -- --mode local --preset checkin`
instead of the form and answer the prompts.

Open the address the installer prints (usually `http://localhost:4321`). On your own
computer, sign-in links print to the terminal instead of being emailed.

## Good to know

- There is no label printing; the pickup code is shown on screen.
- Only children recorded in a household check in. Adult service headcounts come from the separate Service Attendance feature, which uses the service types from Volunteer Scheduling; turn both on later in **Settings → Modules** if you want combined adult and child totals.

## Grow into the full system

This is the complete Church4Christ codebase with a focused starting point. When you are
ready, an administrator can turn on more features (sermons, events, volunteers, groups,
check-in, and more) in **Settings → Modules**, without reinstalling. Upgrades follow the
main repository's [upgrade guide](https://github.com/leveo/church4christ/blob/v1.4.0/docs/upgrade.md).

## Learn more

- [Children's check-in](https://github.com/leveo/church4christ/blob/v1.4.0/docs/features/children-checkin.md)
- [People & households](https://github.com/leveo/church4christ/blob/v1.4.0/docs/features/people-households.md)
- [Service attendance (optional add-on)](https://github.com/leveo/church4christ/blob/v1.4.0/docs/features/service-attendance.md)
- [Putting it online with Cloudflare](https://github.com/leveo/church4christ/blob/v1.4.0/docs/setup.md)

## 中文简介

### 开源教会儿童报到系统

家长在平板上为孩子报到，拿到接送码；儿童事工同工随时看到现在谁在教室里。

- 自助报到机：任何平板浏览器都能用，按孩子姓名或家长电话查找家庭。
- 接送码取代打印标签：兄弟姐妹共用一个 4 位码，凭码接走孩子。
- 同工管理台：今日实时名单、12 周出席图表、班级管理。
- 平板丢失可一键重新生成报到链接，旧设备立即失效。
- 家庭资料来自「会友与家庭」，可用 CSV 导入现有名单。
- 中英文界面，报到机一键切换语言。

本仓库是 [Church4Christ](https://github.com/leveo/church4christ) 的单一功能版本，不包含另外的代码。按上面的快速开始安装后，
得到的是完整的 Church4Christ v1.4.0，只预先开启了这一组功能；以后可以在「设置 → 模块」里开启更多功能。

## Questions and issues

Please open issues and questions in the [main repository](https://github.com/leveo/church4christ/issues), where all the code
lives. Report security problems privately through its
[security advisories](https://github.com/leveo/church4christ/security/advisories/new).

## License

[GNU GPL v3](LICENSE), the same license as Church4Christ.
