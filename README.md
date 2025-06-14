# Wizarding Bank & Shop Discord Bot

A feature-rich Discord bot that implements a Harry Potter themed economy system with a bank, virtual currency (Galleons, Sickles, and Knuts), shop system, and customizable items.

## Features

### Banking System
- **Currency Management**: Uses the Harry Potter currency system with Galleons, Sickles, and Knuts
- **Balance Checking**: View your own balance or other users' balances
- **Income Collection**: Earn regular income based on your server roles
- **Work Command**: Earn money by working with customizable cooldowns
- **Transaction Logging**: All financial activities are tracked

### Shop System
- **Item Shop**: Browse and purchase various magical items
- **Custom Items**: Several item categories including:
  - Wands (with customizable wood, core, length, flexibility, and power)
  - Brooms (with customizable wood, bristle, length, and speed)
  - Accessories (with customizable material, type, and enchantments)
  - And other custom item categories
- **Inventory Management**: View and manage your purchased items

### User Profiles
- **Customizable Profiles**: Set your favorite spells, pets, and bio
- **Display Profile**: View your own or other users' profiles
- **House Affiliations**: Display your Hogwarts house with custom emojis

### VIP & Membership System
- **VIP Purchase**: Users can buy VIP memberships for special perks
- **Cooldown Notifications**: VIP members receive notifications when their cooldowns are over
- **VIP Status**: Check your current VIP membership status
- **Admin VIP Management**: Admins can grant or revoke VIP status and list all VIP members

### Administrative Features
- **Balance Modification**: Administrators can modify user balances
- **Transaction Logs**: Review logs of all financial transactions
- **Leaderboards**: View rankings for wealth, transactions, and income
- **Item Management**: Add, modify, or remove items from the shop

## Setup

1. Contact me for the code
2. Install dependencies: `pip install discord.py`
3. Configure the `config.json` file:
   - Add your Discord bot token
   - Configure banker and shop manager roles
   - Set up currency emojis
   - Configure work and income roles and amounts
   - Set up house roles and emojis

```json
{
    "token": "YOUR_BOT_TOKEN",
    "owner_id": YOUR_DISCORD_ID,
    "banker_roles": [ROLE_ID],
    "shop_manager_roles": [ROLE_ID],
    "currency_emoji": {
        "galleon": "<:Galleon:EMOJI_ID>",
        "sickle": "<:Sickle:EMOJI_ID>",
        "knut": "<:Knut:EMOJI_ID>"
    },
    "work_roles": {
        "ROLE_ID": {
            "currency": "galleon",
            "min": 3,
            "max": 8
        }
    },
    "income_roles": {
        "ROLE_ID": {
            "currency": "galleon",
            "amount": 50
        }
    },
    "default_work": {
        "currency": "knut",
        "min": 5,
        "max": 15
    },
    "default_income": {
        "currency": "knut",
        "amount": 123
    },
    "house_roles": {
        "gryffindor": ROLE_ID,
        "slytherin": ROLE_ID,
        "ravenclaw": ROLE_ID,
        "hufflepuff": ROLE_ID
    },
    "house_emoji": {
        "gryffindor": "<:Gryffindor:EMOJI_ID>",
        "slytherin": "<:Slytherin:EMOJI_ID>", 
        "ravenclaw": "<:Ravenclaw:EMOJI_ID>",
        "hufflepuff": "<:Hufflepuff:EMOJI_ID>"
    }
}
```

4. Run the bot: `python bank.py`

## Commands

### General Commands
- `/balance [user]` - Check your balance or another user's balance
- `/work` - Work to earn money (1-hour cooldown)
- `/collect_income` - Collect weekly income based on your roles
- `/shop` - Browse and buy items from the shop
- `/profile [user]` - View your or another user's profile
- `/destroy [item_type]` - Destroy your wand or broom
- `/use` - Use an item from your inventory
- `/buy_vip <tier>` - Purchase a VIP membership for cooldown notifications
- `/vip_status` - Check your VIP membership status
- `/leaderboard <category>` - Show various leaderboards

### Administrative Commands
- `/modify_balance <user> <amount> <currency>` - Modify a user's balance
- `/reset_cooldown <user> <cooldown_type>` - Reset cooldowns for a user
- `/bulk_modify_balance <role> <amount> <currency> [reason]` - Modify multiple users' balances at once
- `/bulk_reset_cooldown <role> <cooldown_type>` - Reset cooldowns for multiple users at once
- `/get_logs <user> [transaction_type] [sort_order] [date_range] [limit] [export]` - Get detailed transaction logs for a user with optional export
- `/backup_db` - Manually create a database backup
- `/sync_commands` - Manually sync commands with Discord
- `/admin_vip <action> <user> [tier]` - Grant or revoke VIP membership for a user
- `/list_vip` - List all active VIP members


### Shop Management Commands
- `/add_item <name> <price> <currency> <category> <description> [required_role]` - Add an item to the shop
- `/create_wand <name> <price> <currency> <wood> <core> <length> <flexibility> <power>` - Add a wand to the shop
- `/create_broom <name> <price> <currency> <wood> <bristle> <length> <speed>` - Add a broom to the shop
- `/craft_accessories <name> <price> <currency> <material> <type> <enchantment> <description>` - Create a custom accessory
- `/remove_item <category>` - Remove an item from the shop
- `/remove_user_item <user>` - Remove an item from a user's inventory

## Database Structure

The bot uses SQLite to store all data, including:
- User accounts and balances
- Shop items and their properties
- User inventories
- Transaction logs
- Cooldown timers

## Requirements

- Python 3.8+
- discord.py 2.0+
- sqlite3
