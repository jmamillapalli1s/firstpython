import random, sys, json
import pygame
from pygame.locals import *
with open('result.json') as f:
    data = json.load(f)
user = {
    "name": "",
    "score": 0
}
white = (255, 255, 255)
black = (0, 0, 0)
def scoreboard():
    pygame.init()
    Pan2 = Pane()
    Pan2.addRect()
    Pan2.addText()
    f1 = Pan2.button("Quit", (480, 300))
    f2 = Pan2.button("Start", (380, 300))
    while True:
        for event in pygame.event.get():
            if event.type == pygame.QUIT:
                pygame.quit()
                sys.exit()
            if(event.type == pygame.KEYDOWN):
                if event.key == pygame.K_ESCAPE:
                    pygame.quit()
                key_to_start = event.key == pygame.K_s or event.key == pygame.K_RIGHT or event.key == pygame.K_UP
            if event.type == pygame.MOUSEBUTTONDOWN:
                if f1.collidepoint(pygame.mouse.get_pos()):
                    pygame.quit()
                    sys.exit()
                elif f2.collidepoint(pygame.mouse.get_pos()):
                    run()
            pygame.display.update()