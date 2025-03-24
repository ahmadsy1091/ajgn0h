#import telebot

# إنشاء كائن البوت باستخدام التوكن الخاص بك
bot = telebot.TeleBot("8010269803:AAHnYwn-j_CauU33V-40Glk-Pb90iq4_3jY")

# تعريف دالة للرد على أوامر /start و /help
@bot.message_handler(commands=['start', 'help'])
def send_welcome(message):
    bot.reply_to(message, "اهلااااا وسهلا")

# تعريف دالة للرد على جميع الرسائل
@bot.message_handler(func=lambda message: True)
def echo_all(message):
    bot.reply_to(message, message.text)

# بدء استقبال الرسائل بشكل مستمر
bot.infinity_polling()
