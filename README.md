import os
import discord
from discord.ext import commands
import random



intents = discord.Intents.default()
intents.message_content = True

bot = commands.Bot(command_prefix='!', intents=intents)

@bot.event
async def on_ready():
    print(f'We have logged in as {bot.user}')



@bot.command()
async def hello(ctx):
    await ctx.send("Приветствую тебя")
    await ctx.send("Что ты хотечешь узнать от меня?")
    

@bot.event
async def on_message(message):
    if message.content.startswith('Привет ботяра'):
        channel = message.channel
        await channel.send("Привет")
        await channel.send("Что ты хочешь узнать?")

    if message.content.startswith('Хочу узнать как очистить воздух в доме'):
        channel = message.channel
        await channel.send("В ванной и туалете дополнительно поставьте вытяжной вентилятор")
