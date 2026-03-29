mport serial
import pygame
import random
import time

# Initialize
pygame.init()
pygame.mixer.init()

# Connect to Arduino (COM5)
ser = serial.Serial('COM5', 9600)
time.sleep(2)  # allow Arduino to reset

# List of your sound file paths
sounds = [
    r"C:\Users\Dhruv\Desktop\projjject\Fahhh- sound effect (HD) - HighQualitySFX (128k).mp3",

]

while True:
    data = ser.readline().decode().strip()
    print(data)  # for debugging

    if data == "TOUCH":
        pygame.mixer.music.stop()
        sound = random.choice(sounds)  # pick random sound
        pygame.mixer.music.load(sound)
        pygame.mixer.music.play()
