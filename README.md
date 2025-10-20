# Bot-lr
from telegram import Update, InlineKeyboardButton, InlineKeyboardMarkup, BotCommand
from telegram.ext import ApplicationBuilder, CommandHandler, CallbackQueryHandler, ContextTypes
import asyncio

BOT_NAME = "Help for Support"

SUPPORT_LIST = [
"Lavya_Bhambhu - @Lavyabhambhu1",
" Naveen_Cj - @Naveen_Trading",
"Selvin_Devil - @Skpov5",
" Atif_Muuse - @Atifmuse",
" Kishan_Patel - @LD_GF_kishan_patel",
" Amein_Azzi - @amein_jj",
" Sezan_Smith - @Sezan_10",
"King_Micky - @Kingmyth223",
"Robert_Na - @Ramim103",
"Always_Op - @Always_Op7",
"Idrees Khan - @idreesladla",
"Uttam_Kundu - @MoMAcj",
"Arima_Kishou - @Arima_kishou99",
"Victor_Miles - @VictorOjuks",
"Korea_Pavel - @Koreapav"
]

FAQ = {
"How to use the bot?": "Just choose commands in the menu or type your questions.",
"How to contact support?": "Use the /supports command or contact @m4aka."
}

Help_with_the_bot = {
"info": "If you need any information, you can find it here. More details:",
"/start": "Opens the bot menu.",
"/supports": "Shows members of the support team.",
"/job": "Shows official jobs and employment criteria",
"/command_server": "All server commands",
"/roleplay": "List of all role-playing terms",
"/main_support_monitor": "Followers of supports."
}

# --- Команды ---

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    keyboard = [
        [InlineKeyboardButton("FAQ", callback_data="faq")],
        [InlineKeyboardButton("Navigating the bot", callback_data="navigate")]
    ]
    reply_markup = InlineKeyboardMarkup(keyboard)
    await update.message.reply_text(
        "Hello! I am Support Assistant. How can I help you today?",
        reply_markup=reply_markup
    )

async def supports(update: Update, context: ContextTypes.DEFAULT_TYPE):
    msg = "Here is the list of support members:\n\n" + "\n".join(SUPPORT_LIST)
    await update.message.reply_text(msg)

async def main_support_monitor(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("main support monitor: @m4aka")
async def gps_navigator(update: Update, context: ContextTypes.DEFAULT_TYPE):
    blocks = ["""Server navigator (/gps)
1. Jobs

1.1. Oil Refinery (beginner job)
1.2. Sawmill (beginner job)
1.3. Furniture Factory (beginner job)
1.4. Bus Driver (from level 2)
1.5. Food Delivery (from level 2)
1.6. Mine (from level 3)
1.7. Mechanic Station (from level 3)
1.8. Garbage Truck Driver (from level 4)
1.9. Cash-in-Transit (from level 10)
1.10. Vehicle Hijacker (from level 1)




2. Public Places

2.1. Driving School
2.2. Military Enlistment Office
2.3. Moscow City
2.4. Batyrево Bus Station
2.5. Arzamas Bus Station
2.6. Arzamas Park
2.7. Church
2.8. Pier
2.9. Flight School




3. Car Dealerships

3.1. AutoHouse (Premium Class)
3.2. ArzamasCars (Mid Class)
3.3. AutoYard (Economy Class)
3.4. MotoStyle (Motorcycles)
3.5. Aviation Market
3.6. Car Market
3.7. Arzamas Parking
3.8. Yuzhny Parking
3.9. Runways""",




"""4. Auto Hubs

91. Auto Hub (91)


92. Auto Hub (92)


93. Auto Hub (93)


94. Auto Hub (94)


95. Auto Hub (95)


96. Auto Hub (96)


97. Auto Hub (97)


98. Auto Hub (98)


99. Auto Hub (99)


100. Auto Hub (100)


101. Auto Hub (101)


102. Auto Hub (102)


103. Auto Hub (103)


104. Auto Hub (104)


105. Auto Hub (105)


106. Auto Hub (106)


107. Auto Hub (107)


108. Auto Hub (108)


109. Auto Hub (109)


110. Auto Hub (110)


111. Auto Hub (111)


112. Auto Hub (112)


113. Auto Hub (113)


114. Auto Hub (114)


115. Auto Hub (115)


116. Auto Hub (116)


117. Auto Hub (117)


118. Auto Hub (118)


119. Auto Hub (119)""",






"""5. Government Organizations

5.1. Government
5.2. FSB
5.3. Army
5.4. Arzamas Ministry of Internal Affairs
5.5. Yuzhny Traffic Police (GIBDD)
5.6. Russian Ministry of Emergency Situations (EMERCOM)
5.7. Arzamas Hospital
5.8. Yuzhny Hospital
5.9. Ostankino State TV & Radio Company
5.10. TRK Rhythm TV Channel




6. Criminal Structures

6.1. Tambov Organized Crime Group
6.2. Peaky Blinders
6.3. Izmailovo Organized Crime Group
6.4. Real Guys
6.5. Den
6.6. Black Market
6.7. Business Wars




7. Banks

7.1. Arzamas Bank
7.2. Yuzhny Bank
7.3. Batyrево Bank
7.4. Litvagrad Bank
7.5. Printing House




8. Nearest Locations

8.1. Find nearest 24/7 store
8.2. Find nearest clothing store
8.3. Find nearest accessories store
8.4. Find nearest club
8.5. Find nearest ATM
8.6. Find nearest gas station
8.7. Find nearest snack bar
8.8. Find nearest gun store
8.9. Find nearest gardening store




9. Hotels

9.1. Budget Hotel
9.2. Luxury Hotel
9.3. Mid-range Hotel
9.4. Budget Hotel
9.5. Luxury Hotel""",




"""10. Transport Companies

10.1. TK Garel
10.2. TK Batyrево
10.3. TK Lytkarino




11. Service Stations

11.1. Service Station No.1
11.2. Tire Service
11.3. Styling Center
11.4. Tuning Center




12. Entertainment

12.1. Duels
12.2. Club
12.3. Casino
12.4. Zoo
12.5. Game Center
12.6. Dungeon
12.7. Family Container Battle (Military Base)
12.8. Family Container Battle (Green Zone)
12.9. Container Auction
12.10. Nature Reserve
12.11. Pier (Fishing)




13. Businesses

13.1. Gas Station
13.2. Clothing Store
13.3. Accessories Store
13.4. Gun Store
13.5. 24/7 Stores
13.6. Snack Bars
13.7. Wizard’s Shop
13.8. Electronics Stores
13.9. Central Market
13.10. Pet Shelter
13.11. Fisherman’s Shop




14. Greenhouse Complex

14.1. Garden City Store
14.2. Timber Store
14.3. Glass Store
14.4. Rebar Store
14.5. Wholesale Store Garel
14.6. Wholesale Store Batyrево
14.7. Wholesale Store Lytkarino




15. Farming Complex

15.1. Hay Farm
15.2. Anashan (Farm Products Sale)
15.3. Taiga (Timber Gathering)
15.4. Furniture Factory (Timber Sales)




16. Airline Office

16. Airline Company Office"""
    ]

    for block in blocks:
        await update.message.reply_text(block)
async def server_jobs_and_requirements(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("""
#1 Bus Driver (Level 2)

Requirements:

Character level 2

Category C driver’s license

#2 Food Delivery (Level 2)

Requirements:

Character level 2

#3 Taxi Driver (Level 2)

Requirements:

Character level 2

Category B driver’s license

Medical card

#4 Mine Worker (Level 3)

Requirements:

Character level 3

#5 Mechanic (Level 3)

Requirements:

Character level 3

Category B driver’s license

#6 Garbage Collector (Level 4)

Requirements:

Character level 4

Category C driver’s license

#7 Trucker (Level 5)

Requirements:

Character level 5

Category C driver’s license

Medical card

#8 Firefighter (Level 8)

Requirements:

Character level 8

Category C driver’s license

Medical card

#9 Cash-in-Transit Guard (Level 10)

Requirements:

Character level 10

Category B driver’s license

Medical card

#10 Diver (Level 12)

Requirements:

Character level 12

Medical card

Diving equipment (to work)

#11 Pilot (Level 15)

Requirements:

Character level 15

Aircraft operation license

Medical card
""")

async def command_server(update: Update, context: ContextTypes.DEFAULT_TYPE):
    blocks = [
"""General Commands
/help - server commands
/stats - character statistics
/inv - open inventory
/valute - collect money from auction
/recovery - restore items
/vip - VIP status list
/dreward - daily rewards
/ach - achievements
/donate - donation menu
/topday - top daily depositor
/selldonate - sell donation (recharges)
/sellgold [id] [amount] [price] - sell gold coins
/sellpump [id] [amount] [sum] - sell pumpkins
/sellseno - sell hay to player
/pass [id] - show passport
/med [id] - show medical card
/lic - show licenses
/leaders - list of leaders/deputies online
/warnlog - view warnings
/phonebook - phone book
/number [Nick_Name] - find player's phone number
/history [Nick_Name] - view nickname history
/pay [id] [amount] - transfer money
/anim - animation list
/gps - GPS navigator
/healme - use first aid kit
/domkrat - use jack
/time - check exact time
/adlist - list of lawyers online
/liclist - list of license officers online""",

"""Car / Garage / Business

/car - vehicle menu
/pts [id] - show vehicle registration
/e - start engine
/trank(/t) - open trunk
/company - main company menu
/wedding [id] - marry a player
/divorce - divorce
/kiss [id] - kiss your partner
/minet - oral interaction
/garage - garage information and management
/sellgarage - sell garage to the state
/sellmygarage [id] [amount] - sell garage to another player
/buygarage - buy garage from the state
/promo - enter promo code (to receive reward)
/timeskin - wear temporary skin (promo code)
/showvb - show military ID
/radio [1-2] - select radio frequency
/ad [text] - submit an advertisement
/ratingnews - view media rating
/notify - view notifications
/vacancery - view ongoing job interviews
/mlist - view list of mechanics
/prefix - set your prefix
/mp3 - turn on mp3 player
/jbl - turn on JBL speaker
/music - play music in the car
/cameditgui - hide all interface
/headmove - toggle head movement on/off
/hi - shake hand
/chat - chat settings menu
/style - choose style (communication/walk/fight)
/election - view presidential election results
/flower [id] - give flowers to a player
/dl - view vehicle information
/asc [id] - view player accessories
/livepass - battle pass
/taxlist - list of taxi drivers on the server
/jskill - job skills"""
"""Communication
/call [number] - call a player
/sms [number] [text] - send a message
/n [text] - non-RP communication
/s [text] - shout
/w [text] - whisper
/m [text] - megaphone in vehicle (police)
/r [text] - radio (Government)
/f [text] - radio (Gang)
/d [text] - department chat
/gnews [text] - send a message to government news
/me [text] - first-person action
/do [text] - third-person action
/try [text] - action with 50% success
/todo [text*action] - communication with actions
[text];[text] - message with a new line
/vmute - ignore a player in voice chat
/muteinfo - view chat restriction time
/pc [text] - write in zoo chat""",

"""House

/home - house information
/live [id] [days] [price] - let a player move into your house
/liveout - move out of the house
/sellhome - sell the house to the government
/sellmyhome [id] [price] - sell the house to a player
/hlock - lock/unlock a hotel room
/buyhouse - buy a house from the government
/gmove - move an unfinished greenhouse
/green - interact with personal farm/greenhouse""",

"""Business

/business - business menu
/fuel - gas station monitoring
/sellmybiz [id] [price] - sell business to a player
/fbiz - show financial statistics to a player""",

"""Leaders/Deputies

/lmenu - leader menu
/gnews - government news
/news - news menu
/invite [id] - accept a player
/uninvite [id] [reason] - fire a player
/fwarn [id] [reason] - issue a warning
/unfwarn [id] [reason] - remove a warning
/offmembers - offline players list
/offuninvite [Nick_Name] [reason] - fire an offline player
/setskin [id] - give official uniform
/rang [id] - promote/demote
/l - leader chat (government only)
/fmute [id] [time] [reason] - take radio in organization chat
/fmute [id] [time 0] [reason] - return radio in organization chat
/blacklist - faction blacklist""",

"""Vehicle

/lk(lock) - lock/unlock vehicle
/fill - buy a gas can at a gas station
/fillcar - refuel a vehicle with a can
/gass - refuel water transport
/park - park the vehicle
/rem - repair the vehicle with a repair kit
/domkrat - flip the vehicle using a jack
/sellcar - sell vehicle to the government
/sellmycar [id] [amount] - sell vehicle to a player
/changecar [id] [extra] - swap vehicles with a player""",

"""Family

/fammenu(/fm) - family menu
/famonline - online family members
/fam(/fc) - family radio
/faminvite(/finv) [id] - accept to family
/funinvite(/funv) [id] [reason] - kick from family
/famkick [id] [reason] - remove from family
/famsklad - family warehouse menu
/fammute [id] [time] [reason] - mute family radio
/famcar - family vehicle menu
/fpark - park family vehicle
/fgive [id] [amount] - give warehouse permission
/ftake [id] - revoke warehouse permission
/funloadcar - unload all family vehicles (for leader)
/fgiverank [id] [rank] - change member rank
/ffrank [Nick_Name] [rank] - assign rank to offline player
/fbl [id/Nick_Name] [reason] - add to family blacklist
/funbl [id] - remove from family blacklist
/fcontract - view family contracts""",

"""Hospital

/heal [id] [price] - offer treatment to a player
/out [id] - discharge a patient
/gmedcard [id] - issue medical card
/healaddict [id] [price] - give anti-addiction injection
/changesex [id] [price] - offer gender change surgery
/mhelp - accept dispatcher call""",

"""Army

/military - start training
/endmilitary - end training
/givevb [id] - give military ID
/finery [id] [reason] - give uniform
/unfinery [id] [reason] - remove uniform
/finerylist - list of players with uniform
/warehouse - view organization warehouse
/r - division radio
/rn - OOC division radio""",

"""Traffic Police / Ministry of Internal Affairs

/cuff [id] - cuff a player
/uncuff [id] - uncuff a player
/su [id] - put player on wanted list
/push [id] - push player into vehicle
/clear [id] - remove player from wanted list
/ud [id] - show ID
/take [id] - search and seize licenses
/break - place an object
/ticket [id] [amount] [reason] - issue fine
/pt [id] - start pursuit
/hold [id] - escort player
/wanted - wanted list
/ejectout [id] - eject player from closed vehicle
/arrest [id] - arrest player
/post - go on duty
/warehouse - view organization warehouse""",

"""Government

/givelic [id] - license menu / issue lawyer license
/free [id] [price] - release prisoner
/takeout [id] [5 - 30min] - kick player out of building
/alarm - send alert to police
/demote [id] [reason] - demote player
/cname [id] - approve nickname change
/editsu - edit country's criminal code
/hold(follow) [id] - escort player""",

"""Media (TRK)

/nmenu - news menu
/edit - ad editing menu
/ud - media staff ID
/showads - employee statistics (online)
/efir - broadcast control panel
/addefir - add participant to broadcast""",

"""FSB

/break - place object
/ticket [id] [amount] [reason] - issue fine
/pt [id] - start pursuit
/hold [id] - escort player
/wanted - wanted list
/ejectout [id] - eject player from closed vehicle
/arrest [id] - arrest player
/post - go on duty
/warehouse - view organization warehouse
/passcard - give/revoke office key card
/deal [id] [amount] - propose deal
/demote [id] [reason] - demote player
/tipster get - take spy bug
/tipster set - place bug on player
/tipster del - deactivate bug
/fr - implanted organization radio
/frn - NRP implanted organization radio""",

"""Criminal Structures

/mafiawar - start gang fight for business
/bizlist - list of captured businesses
/mafiawartime (/mwt) - time until next fight
/warelock - open/close warehouse
/makegun - craft weapon from materials
/sellgun - sell weapon
/sellmat [id] [amount] [price] - sell materials
/members - organization online list
/reave - kidnap player
/hold [id] - escort player
/push [id] - push player into vehicle
/rf - speak in kidnap radio
/f - organization radio
/fn - NRP radio""",

"""Emergency Services (MES)

/ram - break door of house/apartment"""]

    for block in blocks:
        await update.message.reply_text(block)

async def roleplay_terms(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text("""RP (RolePlay) - Role-playing where each player must follow your character's role.
DM (Deathmatch) - Killing without a valid reason.
DB (Drive-By) - Killing using a vehicle.
SK (Spawn Kill) - Killing immediately at spawn points.
TK (Team Kill) - Killing members of your own faction.
PG (PowerGame) - Acting like a hero beyond your character's abilities, e.g., being alone against many. Overstating a character's capabilities.
RK (Revenge Kill / Rambo Kill) - Returning to a location where you were killed to take revenge; repeated intentional killing of the same player.

MG (Metagame) - Using real-world information in the in-game chat (OOC in IC).
BX (Bug Exploit Run / Bunny Hop) - Non RP running with jumps.
YK (Criminal Code / UK) - Criminal Code.
AK (Academic Code / AC) - Academic Code.
ZZ (Green Zone) - Public areas like squares, train stations, hospitals; no shooting allowed.
FR (Fast Reload) - Exploit/bug with fast reloading.
FM (Fast Move) - Exploit/bug with fast movement.

FF (Friendly Fire) - Shooting at your teammates/friends without killing, e.g., leaving 10 HP. Shooting in jest.
CK (Character Kill / RP Kill) - Killing according to RP, prohibited on the server.
ORP (Out-of-RolePlay) - Avoiding RP.
PK (Player Kill / Random Kill) - Accidental or environmental death; does not permanently harm the character, considered minor trauma, temporary amnesia, or pain shock.

FRP (Fear RolePlay) - Your character should fear death, as they would in real life.

OOC (Out of Character) - Information or actions unrelated to the RP game.
IC (In Character) - Everything concerning the in-game world; written in normal chat.

AFK (Away From Keyboard) - Away from the keyboard.
Respawn - Player spawn point.
RP NickName - Name in the format: First_Last (e.g., Leonid_Litvinenko, Egor_Plakapenka).
Faction - Organization.
Skills - Weapon proficiency skills.
Level (LVL) - Years in the state/server.""")

# --- Обработка нажатий кнопок ---

async def button(update: Update, context: ContextTypes.DEFAULT_TYPE):
    query = update.callback_query
    await query.answer()
    if query.data == "faq":
        msg = "\n\n".join([f"{q}\n{a}" for q, a in FAQ.items()])
        await query.edit_message_text(msg)
    elif query.data == "navigate":
        msg = "\n".join([f"{cmd} - {desc}" for cmd, desc in Help_with_the_bot.items()])
        await query.edit_message_text(msg)

# --- Запуск бота ---

if __name__ == "__main__":
    app = ApplicationBuilder().token("8207173343:AAEUoqXRR8rWHVIGv-Xza_DRe3-xZCw-baI").build()

    # Регистрируем команды
    app.add_handler(CommandHandler("start", start))
    app. add_handler(CommandHandler("gps", gps_navigator))
    app.add_handler(CommandHandler("supports", supports))
    app.add_handler(CommandHandler("job", server_jobs_and_requirements))
    app.add_handler(CommandHandler("command_server", command_server))
    app.add_handler(CommandHandler("main_support_monitor", main_support_monitor))
    app.add_handler(CommandHandler("roleplay", roleplay_terms))
    app.add_handler(CallbackQueryHandler(button))

    # Устанавливаем команды в меню Telegram
    loop = asyncio.get_event_loop()
    loop.run_until_complete(app.bot.set_my_commands([
        BotCommand("start", "Start the bot"),
        BotCommand("supports", "List all support members"),
        BotCommand("gps", "Gps navigator"),
        BotCommand("job", "job"),
        BotCommand("command_server", "Server work commands"),
        BotCommand("roleplay", "Show roleplay rules"),
        BotCommand("main_support_monitor", "Activate support monitor")
    ]))

    print(f"{BOT_NAME} is running...")
    app.run_polling()
