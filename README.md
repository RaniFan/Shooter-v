# Shooter-v
Главная вещь в данной это дойти до босса и остаться в живых
Вы тут играете тут за отличительного пилота на космическом корабле
И вам предстоит одолеть главного босса этого космоса 
В данном коде и игре самое главное это работа над спрайтами и звуками
![image](https://user-images.githubusercontent.com/128893943/229186043-12d01d7c-fc81-4bad-81b6-d6d60bc2fcde.png)
![image](https://user-images.githubusercontent.com/128893943/229186284-91ab1386-e580-4103-9550-17abaaaabf22.png)
И ещё нам предстоит написать под-класс для передвижение корабля 

      class GameSprite(sprite.Sprite):
        def __init__(self, player_image, player_x, player_y, size_x, size_y, player_speed):
        sprite.Sprite.__init__(self)
        self.image = transform.scale(image.load(player_image), (size_x, size_y))
        self.speed = player_speed
        self.rect = self.image.get_rect()
        self.rect.x = player_x
        self.rect.y = player_y
    def reset(self):
        window.blit(self.image, (self.rect.x, self.rect.y))
      
Вторая часть в данном коде это работа над управлением, тоесть через какие клавиши мы будем перемещаться по космосу

    class Player(GameSprite):
        def update(self):
            global is_busy
            keys = key.get_pressed()
            if keys[K_LEFT] and self.rect.x > 5:
                self.rect.x -= self.speed
            if keys[K_RIGHT] and self.rect.x < win_width - 80:
                self.rect.x += self.speed
        def fire(self):
            bullet = Bullet(img_bullet, self.rect.centerx, self.rect.top, 10, 30, -15)
            bullets.add(bullet)
            
 Не забываем добавить врагов тоесть метриориты чтобы жизнь малиной не казалось 
 
![image](https://user-images.githubusercontent.com/128893943/229189224-ab9a5960-fae0-4866-bb75-871b8432f7eb.png)

Важная часть игры это босс и самое не забываем найти нужный спрайт 
![image](https://user-images.githubusercontent.com/128893943/229194828-0aff0848-65bd-4f29-abca-87e9fbc7a614.png)

