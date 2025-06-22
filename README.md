# vrr-# Venture Role Request Bot

A modern Discord bot for role verification using OCR (Optical Character Recognition) technology. Built for ERM-style servers with automated screenshot verification.

## Features

- 🤖 **Automatic OCR Verification** - Uses Tesseract OCR to verify department membership
- 📸 **Screenshot Analysis** - Analyzes uploaded images for department verification
- ⚡ **Instant Role Assignment** - Automatically assigns roles for verified requests
- 📋 **Admin Management** - Complete request management system
- 🔒 **Security Controls** - Admin-only commands with role-based permissions

## Supported Departments

- Queen City Police Department
- Harris County Sheriff's Office
- Harris County Police Department
- Harris County Fire Department
- Texas Department Of Public Safety

## Commands

### User Commands
- `/requestrole` - Request a department role with photo verification
- `/listroles` - View all available departments
- `/help` - Show all available commands

### Admin Commands
- `/viewrequests [count]` - View recent role requests
- `/viewrequest <id>` - View detailed request with screenshot
- `/approve <id>` - Approve a pending request
- `/deny <id>` - Deny a request
- `/addrole <name>` - Add new department
- `/removerole <name>` - Remove department
- `/setadminrole <name>` - Configure admin role

## Setup

### Prerequisites
- Python 3.11+
- Discord Bot Token
- Tesseract OCR installed

### Installation

1. Clone this repository
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Set up environment variables:
   - `DISCORD_BOT_TOKEN` - Your Discord bot token
4. Run the bot:
   ```bash
   python main.py
   ```

### Discord Bot Setup

1. Create a Discord application at [Discord Developer Portal](https://discord.com/developers/applications)
2. Create a bot and copy the token
3. Enable the following bot permissions:
   - Send Messages
   - Use Slash Commands
   - Manage Roles
   - Read Message History
   - Attach Files
4. Invite the bot to your server with proper permissions

## How It Works

1. **User Request**: User runs `/requestrole` and selects a department
2. **Image Upload**: User uploads a screenshot proving department membership
3. **OCR Analysis**: Bot analyzes the image using Tesseract OCR
4. **Verification**: Bot searches for department keywords in extracted text
5. **Role Assignment**: If verified, role is automatically assigned
6. **Manual Review**: If not auto-verified, request goes to admin queue

## Configuration

- Modify `allowed_roles` list to add/remove supported departments
- Use `/setadminrole` to configure which role can use admin commands
- Requests are stored in `requests.json` for persistence

## Health Monitoring

The bot includes a Flask server for uptime monitoring:
- Health endpoint: `http://your-bot-url/health`
- Status endpoint: `http://your-bot-url/`

## Technologies Used

- [Discord.py](https://discordpy.readthedocs.io/) - Discord bot framework
- [Tesseract OCR](https://github.com/tesseract-ocr/tesseract) - Image text recognition
- [Pillow](https://python-pillow.org/) - Image processing
- [Flask](https://flask.palletsprojects.com/) - Web server for health checks
- [aiohttp](https://docs.aiohttp.org/) - Async HTTP client

## License

This project is open source and available under the MIT License.

## Support

For support or questions, please open an issue on GitHub.
