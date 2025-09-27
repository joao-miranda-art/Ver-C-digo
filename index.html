#pgzero
import random

# Função para definir cor da vida
def get_health_color(health, max_health=100):
    if health > max_health * 0.6:
        return "green"
    elif health > max_health * 0.3:
        return "yellow"
    else:
        return "red"


# Configurações do jogo
cell = Actor('border', size=(82,82))
cell1 = Actor('floor', size=(82,82))
cell2 = Actor("crack", size=(82,82))
cell3 = Actor("bones", size=(82,82))
size_w = 9 
size_h = 10 
WIDTH = cell.width * size_w
HEIGHT = cell.height * size_h

win = 0
mode = "game"
colli = 0
game_state = "playing" 

TITLE = "WeCode e Dragões"
FPS = 30

# Mapa
my_map = [
    [0,0,0,0,0,0,0,0,0],
    [0,1,1,1,1,1,1,1,0],
    [0,1,1,2,1,3,1,1,0],
    [0,1,1,1,2,1,1,1,0],
    [0,1,3,2,1,1,3,1,0],
    [0,1,1,1,1,3,1,1,0],
    [0,1,1,3,1,1,2,1,0],
    [0,1,1,1,1,1,1,1,0],
    [0,0,0,0,0,0,0,0,0],
    [-1,-1,-1,-1,-1,-1,-1,-1,-1]
]

# Personagem principal
char = Actor('stand', size=(65,65))
char.health = 100
char.attack = 5
char.top = cell.height
char.left = cell.width

# Inimigos
enemies = []
for i in range(5):
    x = random.randint(1, 7) * cell.width
    y = random.randint(1, 7) * cell.height
    enemy = Actor("enemy", topleft=(x, y), size=(48,48))
    enemy.health = random.randint(10, 20)
    enemy.attack = random.randint(5, 10)
    enemy.bonus = random.randint(0, 2)
    enemies.append(enemy)

# Bônus
hearts = []
swords = []

# Função para reiniciar o jogo
def restart_game():
    global win, mode, colli, game_state, enemies, hearts, swords
    
    win = 0
    mode = "game"
    colli = 0
    game_state = "playing"
    
    char.health = 100
    char.attack = 5
    char.top = cell.height
    char.left = cell.width
    
    hearts[:] = []
    swords[:] = []
    
    enemies[:] = []
    for i in range(5):
        x = random.randint(1, 7) * cell.width
        y = random.randint(1, 7) * cell.height
        enemy = Actor("enemy", topleft=(x, y), size=(48,48))
        enemy.health = random.randint(10, 20)
        enemy.attack = random.randint(5, 10)
        enemy.bonus = random.randint(0, 2)
        enemies.append(enemy)

# Desenhando o mapa
def map_draw():
    for i in range(len(my_map)):
        for j in range(len(my_map[0])):
            if my_map[i][j] == 0:
                cell.left = cell.width*j
                cell.top = cell.height*i
                cell.draw()
            elif my_map[i][j] == 1:
                cell1.left = cell.width*j
                cell1.top = cell.height*i
                cell1.draw()
            elif my_map[i][j] == 2:
                cell2.left = cell.width*j
                cell2.top = cell.height*i
                cell2.draw()  
            elif my_map[i][j] == 3:
                cell3.left = cell.width*j
                cell3.top = cell.height*i
                cell3.draw() 

# Desenho geral
def draw():
    if game_state == 'playing':
        screen.fill("#2f3542")
        map_draw()
        char.draw()
        screen.draw.text("❤️:", center=(100, 775), color='white', fontsize=20)
        screen.draw.text(
            str(char.health),
            center=(150, 775),
            color=get_health_color(char.health),
            fontsize=20
        )
        screen.draw.text("⚔️:", center=(575, 775), color='white', fontsize=20)
        screen.draw.text(str(char.attack), center=(625, 775), color='white', fontsize=20)
        for enemy in enemies:
            enemy.draw()
            screen.draw.text(
                str(enemy.health),
                topleft=(enemy.x + 5, enemy.y - 30),
                color=get_health_color(enemy.health),
                fontsize=18
            )
        for heart in hearts:
            heart.draw()
        for sword in swords:
            sword.draw()
    elif game_state == "victory":
        screen.fill("#1e3a8a") 
        screen.draw.text("🎉 VITÓRIA! 🎉", center=(WIDTH/2, HEIGHT/2 - 80), color='gold', fontsize=46)
        screen.draw.text("Você derrotou todos os inimigos!", center=(WIDTH/2, HEIGHT/2 - 20), color='white', fontsize=24)
        screen.draw.text("Pressione ESPAÇO para jogar novamente", center=(WIDTH/2, HEIGHT/2 + 40), color='lightblue', fontsize=20)
    elif game_state == "defeat":
        screen.fill("#7f1d1d")
        screen.draw.text("💀 DERROTA 💀", center=(WIDTH/2, HEIGHT/2 - 80), color='red', fontsize=46)
        screen.draw.text("Você foi derrotado!", center=(WIDTH/2, HEIGHT/2 - 20), color='white', fontsize=24)
        screen.draw.text("Pressione ESPAÇO para jogar novamente", center=(WIDTH/2, HEIGHT/2 + 40), color='#F08080', fontsize=20) 

# Controles
def on_key_down(key):
    global colli
    
    if game_state in ["victory", "defeat"]:
        if key == keys.SPACE:
            restart_game()
        return
    
    old_x = char.x
    old_y = char.y
    
    if keyboard.right and char.x + cell.width < WIDTH - cell.width:
        char.x += cell.width
    elif keyboard.left and char.x - cell.width > cell.width:
        char.x -= cell.width
    elif keyboard.down and char.y + cell.height < HEIGHT - cell.height*2:
        char.y += cell.height
    elif keyboard.up and char.y - cell.height > cell.height:
        char.y -= cell.height

    # Colisão com inimigos
    enemy_index = char.collidelist(enemies)
    if enemy_index != -1:
        char.x = old_x
        char.y = old_y
        colli = 1
        enemy = enemies[enemy_index]
        enemy.health -= char.attack
        char.health -= enemy.attack
        if enemy.health <= 0:
            if enemy.bonus == 1:
                heart = Actor('heart', size=(32,32))
                heart.pos = enemy.pos
                hearts.append(heart)
            elif enemy.bonus == 2:
                sword = Actor('sword', size=(32,32))
                sword.pos = enemy.pos
                swords.append(sword)
            enemies.pop(enemy_index)

# Lógica de vitória/derrota
def victory():
    global mode, win, game_state
    
    if char.health <= 0:
        game_state = "defeat"
        return
    
    if len(enemies) == 0:
        if mode == "game":
            mode = "level_2"
            win += 1
            char.health = min(char.health + 20, 100)
            for i in range(5):
                x = random.randint(1, 7) * cell.width
                y = random.randint(1, 7) * cell.height
                enemy = Actor("enemy", topleft=(x, y), size=(48,48))
                enemy.health = random.randint(15, 25)
                enemy.attack = random.randint(7, 12)
                enemy.bonus = random.randint(0, 2)
                enemies.append(enemy)
        elif mode == "level_2": 
            game_state = "victory"

# Atualização dos bônus
def update(dt):
    if game_state == "playing":
        victory()
        for i in range(len(hearts)-1, -1, -1):
            if char.colliderect(hearts[i]):
                char.health = min(char.health + 15, 100) 
                hearts.pop(i)
        for i in range(len(swords)-1, -1, -1):
            if char.colliderect(swords[i]):
                char.attack += 3
                swords.pop(i)
