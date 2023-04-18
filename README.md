# JAMGYU
pip install pygame

import pygame
import random

# 게임의 색깔을 정의합니다.
BLACK = (0, 0, 0)
WHITE = (255, 255, 255)
GREEN = (0, 255, 0)
RED = (255, 0, 0)

# 화면의 크기를 정의합니다.
WIDTH = 800
HEIGHT = 600

# 뱀의 크기를 정의합니다.
BLOCK_SIZE = 10

# Pygame을 초기화합니다.
pygame.init()

# 화면을 설정합니다.
screen = pygame.display.set_mode((WIDTH, HEIGHT))

# 게임의 타이틀을 설정합니다.
pygame.display.set_caption("Snake Game")

# 게임의 FPS(Frame Per Second)를 설정합니다.
clock = pygame.time.Clock()
FPS = 20

# 글꼴을 설정합니다.
font = pygame.font.SysFont(None, 25)

# 점수를 출력하는 함수입니다.
def draw_score(score):
    text = font.render("Score: "+str(score), True, WHITE)
    screen.blit(text, [0, 0])

# 뱀을 그리는 함수입니다.
def draw_snake(snake_list):
    for x,y in snake_list:
        pygame.draw.rect(screen, GREEN, [x, y, BLOCK_SIZE, BLOCK_SIZE])

# 게임을 실행하는 함수입니다.
def gameLoop():
    game_over = False
    game_close = False

    # 뱀의 초기 위치와 길이를 설정합니다.
    x1 = WIDTH / 2
    y1 = HEIGHT / 2
    snake_List = []
    Length_of_snake = 1

    # 먹이의 초기 위치를 설정합니다.
    foodx = round(random.randrange(0, WIDTH - BLOCK_SIZE) / 10.0) * 10.0
    foody = round(random.randrange(0, HEIGHT - BLOCK_SIZE) / 10.0) * 10.0

    # 게임 루프
    while not game_over:

        # 게임이 종료될 경우
        while game_close == True:
            screen.fill(BLACK)
            message("You Lost! Press Q-Quit or C-Play Again", RED)
            draw_score(Length_of_snake - 1)
            pygame.display.update()

            # 키보드 입력 이벤트 처리
            for event in pygame.event.get():
                if event.type == pygame.KEYDOWN:
                    if event

git push 
