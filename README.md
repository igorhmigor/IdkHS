class Character:
    def __init__(self, name, health):
        self.name = name
        self.health = health

    def attack(self, target):
        pass


class Hero(Character):
    def __init__(self, name, health, weapon):
        super().__init__(name, health)
        self.weapon = weapon

    def attack(self, target):
        print(f"{self.name} атакує {target.name} з використанням {self.weapon}.")
   


class Enemy(Character):
    def __init__(self, name, health, damage):
        super().__init__(name, health)
        self.damage = damage

    def attack(self, target):
        print(f"{self.name} атакує {target.name}, завдаючи {self.damage} шкоди.")
        target.health -= self.damage
        print(f"{target.name} тепер має {target.health} очок здоров'я.")

hero = Hero("jake", 100, "knife")
enemy = Enemy("zombie", 50, 10)

hero.attack(enemy)

enemy.attack(hero)
