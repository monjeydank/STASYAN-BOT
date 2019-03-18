# STASYAN-BOT
# My own discord bot for training my skills.
import discord
from discord.ext.commands import Bot
from discord.ext import commands
import asyncio

from discord.ext import commands


des = 'Стасян'
prefix = (".","")

bot = commands.Bot(command_prefix=prefix, description=des)


@bot.event
async def on_message(message):

    if message.content.upper().startswith('Я ХОЧУ УМЕРЕТЬ'):
        userID = message.author.id
        await bot.send_message(message.channel, "Ну пиздец! <@%s> Я тоже, братан" % (userID))

    if message.content.upper().startswith('ПРИВЕТ'):
        userID = message.author.id
        await bot.send_message(message.channel, "Здарова-здарова, <@%s>" % (userID))

    if message.content.upper().startswith('ПЛАЧУ'):
        userID = message.author.id
        await bot.send_message(message.channel, "Да ладно тебе, всё обязательно наладится, <@%s>" % (userID))

    if message.content.upper().startswith('ПОКА'):
        userID = message.author.id
        await bot.send_message(message.channel, "Давай, <@%s> Не кашляй, друг!" % (userID))

    if message.content.upper().startswith('ЛЮБЛЮ ТЕБЯ'):
        userID = message.author.id
        await bot.send_message(message.channel, "И я тебя, сладенький <@%s>" % (userID))

    if message.content.upper().startswith('КАК ТЫ?'):
        await bot.send_message(message.channel, "Да, потихонечку.")

    if message.content.upper().startswith('ТЕБЕ НРАВИТСЯ КАК ПОДСТРИГСЯ ГЛОБА?'):
        await bot.send_message(message.channel, "Абсолютно нет ")



    if message.content.upper().startswith('СКАЖИ'):
        if message.author.id == "395293677687406612":
            args = message.content.split(" ")
            await bot.send_message(message.channel, "%s" % (" ".join (args[1:])))
        else:
            await bot.send_message(message.channel, "А не пойти бы тебе нахуй?")

    if message.content.upper().startswith('ИНФА'):
        embed = discord.Embed(title = "Стасян", description = "Привет, меня зовут Стасян. Меня запрограммировали ради изучения создания ботов.в дискорде. Я умею реагировать на команды.", colour = discord.Colour.magenta())
        embed.set_author(name='Мой батя - madaMada#2782')
        embed.add_field(name='Дата создания: ', value='16.03,19', inline=False)
        embed.add_field(name='Было выпито энергетиков: ', value='9', inline=True)
        embed.add_field(name='Букер: ', value='бэнгер', inline=True)
        await bot.send_message(message.channel, embed=embed)

    if message.content.upper().startswith('ХЕЛП'):
        embed = discord.Embed(colour = discord.Colour.magenta())
        embed.set_author(name='Список команд (писать без префикса)')
        embed.add_field(name='привет', value='Здоровается с тобой', inline=False)
        embed.add_field(name='я хочу умереть', value='Морально поддерживает', inline=False)
        embed.add_field(name='скажи', value='Пишет то, что вы сказали после команды', inline=False)
        embed.add_field(name='пока', value='Прощается с тобой', inline=False)
        await bot.send_message(message.channel, embed=embed)

   @bot.event
   async def on_ready():
   await bot.change_presence(game=discord.Game(name='ящик'))

bot.run('NTU2MTIzNTY3MDIwOTY1OTE4.D26qIw.au9zREaQKewpWuoxxVWrgzeIi04')
