@bot.message_handler(commands=['start'])
def start(message):
  markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
  button1 = types.KeyboardButton('Зарегестрироваться')
  markup.add(button1)
  bot.send_message(message.chat.id, "👋 Привет, {0.first_name}!\nВы попали к персональному помощнику по управлению Добро.Центром\n\nДля начала нужно зарегестрироваться 👇🏻".format(message.from_user), reply_markup=markup)

@bot.message_handler(content_types=['text'])
def registtion(message):
  if(message.text == 'Зарегестрироваться'):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    button1 = types.KeyboardButton('Я ознакомился')
    markup.add(button1)
    bot.send_message(message.chat.id, "Преждем чем приступить к регистрации предлагаем Вам ознакомится с публичной политикой обработки персональных данных Ассоциации волонтерских центров".format(message.from_user), reply_markup=markup)
  elif(message.text == 'Я ознакомился'):
    markup = types.ReplyKeyboardMarkup(resize_keyboard=True)
    button1 = types.KeyboardButton('Стандарт')
    button2 = types.KeyboardButton('Мастер')
    markup.add(button1, button2)
    bot.send_message(message.chat.id, "Какой у Вас пакет франшизы?".format(message.from_user), reply_markup=markup)
