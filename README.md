- 👋 Hi, I’m @Tanundon
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Tanundon/Tanundon is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import random

class Character:
    def __init__(self, name, hp, attack):
        self.name = name
        self.hp = hp
        self.attack = attack

    def take_damage(self, damage):
        self.hp -= damage

    def attack_enemy(self, enemy):
        damage = random.randint(0, self.attack)
        enemy.take_damage(damage)
        print(f"{self.name} โจมตี {enemy.name} โดยใช้พลังโจมตี {damage}")
        print(f"{enemy.name} มีเลือดเหลือ {enemy.hp}\n")

player = Character("ผู้เล่น", 100, 20)
enemy = Character("ศัตรู", 80, 15)

while player.hp > 0 and enemy.hp > 0:
    player.attack_enemy(enemy)
    if enemy.hp <= 0:
        print("คุณชนะ!")
        break
    
    enemy.attack_enemy(player)
    if player.hp <= 0:
        print("คุณแพ้!")
        break
