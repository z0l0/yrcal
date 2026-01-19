# yrcal — Your Year at a Glance

A privacy-first calendar visualization tool that helps you audit your life. Import your Google Calendar or .ICS files and see your entire year in one beautiful view.

![yrcal screenshot](https://via.placeholder.com/800x400?text=yrcal+screenshot)

## Features

- **Year-at-a-Glance View** — See your entire year on one screen
- **Google Calendar Sync** — Import events directly from Google Calendar
- **ICS Import** — Import .ics files from any calendar app
- **Smart Categorization** — Auto-categorize events with customizable rules
- **Energy Tracking** — Mark events as energy chargers ⚡️ or drains 🪫
- **Privacy-First** — All data stored locally in your browser
- **Custom Categories** — Create and color-code your own categories
- **Stats Dashboard** — Review your year with beautiful analytics
- **Print-Ready** — Print your year for physical planning

## Quick Start

1. Open `yrcal.html` in your browser
2. Click "Import Google Calendar" or "Import .ICS"
3. Review and categorize your events
4. Visualize your year!

## Google Calendar Setup (Optional)

To use Google Calendar import:

1. Go to [Google Cloud Console](https://console.cloud.google.com/)
2. Create a new project
3. Enable the Google Calendar API
4. Create OAuth 2.0 credentials (Web application)
5. Add authorized JavaScript origins: `http://localhost` and your domain
6. Download the credentials JSON file
7. Copy your Client ID into `yrcal.html` (line ~850, replace `GOOGLE_CLIENT_ID`)

**Note:** The app works perfectly fine with just .ICS file imports if you don't want to set up Google OAuth.

## Usage

### Importing Events

**Google Calendar:**
- Click "Import Google Calendar"
- Authorize access
- Events from 2024-2026 will be imported

**ICS Files:**
- Export your calendar as .ics from any calendar app
- Click "Import .ICS" and select your file(s)

### Categorizing Events

- Events are auto-categorized based on keywords
- Click any day to review and manually categorize events
- Create custom categories in the sidebar
- Bulk-apply categories to recurring events

### Energy Tracking

- Click any event and mark it as ⚡️ (charger) or 🪫 (drain)
- See patterns over time
- Identify energy vampires in your schedule

### Viewing Options

- Toggle between full year, half year, or quarter views
- Show/hide weekends
- Filter to show only uncategorized events
- Print your calendar for physical planning

## Data Privacy

All your calendar data is stored locally in your browser's localStorage. Nothing is sent to any server. Your events never leave your device.

## Browser Compatibility

Works best in modern browsers:
- Chrome/Edge 90+
- Firefox 88+
- Safari 14+

## Development

This is a single-file HTML app with no build process. Just open `yrcal.html` in your browser.

### Dependencies (loaded via CDN)
- ical.js — ICS file parsing
- Google Sign-In API — OAuth authentication

## Roadmap

See [prd.md](prd.md) for the full product vision.

- [ ] Mobile app (React Native)
- [ ] End-to-end encrypted cloud backup
- [ ] Annual "Life Resume" report
- [ ] Multi-calendar support
- [ ] Outlook/iCloud sync

## License

MIT License - feel free to use and modify!

## Credits

Inspired by Jesse Itzler's Big Ass Calendar philosophy and the year-at-a-glance format.

Built with ❤️ for people who want to own their time.
