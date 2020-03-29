# Juan-Novaes
Criador de I.# coding: iso-8859-1 -*-
import aiml
import os

os.chdir('C:/Python24/curso/projetoAIML') # diretório que contém os arquivos da AIML standard
ai = aiml.Kernel() # inicialização
ai.learn('std-startup.xml') # lê o arquivo principal da AIML e faz referências aos outros
ai.respond('load aiml b') # faz com que os outros arquivos da AIML sejam carregados

while (1==1):
frase = raw_input('Fale algo ao bot em english:')
print "Resposta do bot: %s" % ai.respond(frase)
# coding: iso-8859-1 -*-
import aiml
import os

os.chdir('C:/Python24/curso/projetoAIML') # diretório que contém os arquivos da AIML standard
ai = aiml.Kernel() # inicialização
ai.learn('std-startup.xml') # lê o arquivo principal da AIML e faz referências aos outros
ai.respond('load aiml b') # faz com que os outros arquivos da AIML sejam carregados

while (1==1):
frase = raw_input('Fale algo ao bot em english:')
print "Resposta do bot: %s" % ai.respond(frase)
# coding: iso-8859-1 -*-
import aiml
import os
import pyTTS
import time

tts = pyTTS.Create() # cria o motor de fala.
tts.Volume = 90 # Ajusta o Volume.

os.chdir('C:/Python24/curso/projetoAIML') # muda para o diretório que contém os arquivos da AIML

standard
ai = aiml.Kernel() # inicialização
ai.learn('std-startup.xml') # abre o arquivo principal da AIML (que faz referências aos outros)
ai.respond('load aiml b') # faz com que os outros arquivos da AIML sejam carregados

while (1==1):
frase = raw_input('Fale algo ao bot em english:')
print "Resposta do bot: %s" % tts.Speak(ai.respond(frase))
<aiml>
<category>
<pattern>oi</pattern>
<template>Ola, tudo bem?</template>
</category>


<category>
<pattern>qual o seu nome?</pattern>
<template>
<random>
<li>Sou chamado de chatterbot</li>
<li>Me chamo chatterbot</li>
<li>Chatterbot</li>
<li>pode me chamar de chatterbot</li>
</random>
</template>
</category>


</aiml># coding: iso-8859-1 -*-
# Projeto: bot-AIMerLin
# Por: Kratos - 2007

import aiml # Carrega a Inteligência Artificial de conversação do bot
import os, sys # Para entrada e saída de dados e fechar o programa
import random # Para Sortear itens na lista
import win32com.client # Controla API do Win32 (COM)

ag = win32com.client.Dispatch("Agent.Control.2") # Declara o objecto a ser controlado (Agent's)
ag.connected = True # Conecta com o objeto

# lista de Animação do MS Agent, no caso, o Sr. Merlin.
playList =["Acknowledge","Alert","Announce","Blink","Confused","Congratulate","Congratulate_2", "Greet","Decline","DoMagic1","DoMagic2","DontRecognize","GestureDown","GestureLeft",
"GestureRigh","GestureUp","GetAttention","GetAttentionContinued","GetAttentionReturn","Greet",
"Hearing_1","Hearing_2","Hearing_3","Hide","Idle1_1","Idle1_2","Idle1_3","Idle1_4","Idle2_1",
"Idle2_2","Idle3_1","Idle3_2","LookDown","LookDownBlink","LookDownReturn","LookLeft","LookLeftBli
nk", "LookLeftReturn","LookRight","LookRightBlink","LookRightReturn","LookUp","LookUpBlink","LookUpRet
urn", "Pleased","Process","Processing","Read","ReadContinued","Reading","ReadReturn","RestPose",
"Sad","Search","StartListening","StopListening","Suggest","Surprised","Think","Uncertain",
"Uncertain","Wave","Write"]

os.chdir('C:\Python24\Curso\Meus Programas\Projetos\BotPython') # AIML standard.
ai = aiml.Kernel() # Inicialização no bot.
ai.learn('std-startup.xml') # Abre o arquivo principal da AIML (que faz referências aos outros).
ai.respond('load aiml b') # Carrega arquivos da AIML (Inteligência Artificial).

ag.Characters.Load("Merlin") # Carrega o Merlin como agent, existem inúmeros outros.
ag.Characters("Merlin").Show() # Mostra o agent.
ag.Characters("Merlin").TTSModeID = "{8AA08CA1-A1AE-11D3-9BC5-00A0C967A2D1}" # Português BR

ag.Characters("Merlin").Play(playList[7]) # Executa uma animação da lista
ag.Characters("Merlin").Speak(u"Olá, meu criador, Kratos, ainda está me ensinando a falar em português!") # Fala
ag.Characters("Merlin").Play(playList[0]) # Executa a animação da Lista.
ag.Characters("Merlin").Speak(u"Meu nome é Mérlin, qual é o seu nome?") # Fala a frase.
ag.Characters("Merlin").Speak(u"Só lembrando que a partir de agora, falarei em inglês, com sutaque Português")
ag.Characters("Merlin").Speak(u"Pois, precisam carregar meus dados AIML com informações em Português")


about = """ >>> Agente AIML Speak <<<

Digite '-q' ou nada, para sair.
Digite '-h' para minimizar.
Digite '-s' para maximizar.
Total de Animações: %s .\n""" %(len(playList))
print about

# Inicia a conversa com o bot, você pergunta, e ele responde!
while (1==1):	
try:
	youSpeak = raw_input(u"Fale algo ao bot em english: ")
	if youSpeak == "-q":
		sys.exit()
	if youSpeak == "-h":
		ag.Characters("Merlin").Hide()
	if youSpeak == "-s":
		ag.Characters("Merlin").Show()
	botSpeak = ai.respond(youSpeak)
	ag.Characters("Merlin").Speak(botSpeak)
	print
except:
	ag.connected = False
	sys.exit()		
raw_input(">>") # Serve para manter o Agent activo
