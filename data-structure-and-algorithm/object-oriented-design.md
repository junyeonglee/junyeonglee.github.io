# Object-Oriented Design

## Singleton Class

All modules are singleton, by definition.

```python
## Restaurant.py
country = "singapore"

## sample1.py
import Restaurant
print(Restaurant.country)  # singapore
Restaurant.country = "malaysia"

## sample2.py
import Restaurant
print(Restaurant.country) # malaysia
```

## Factory Method

```python
class CardGame:
    @staticmethod
    def create_card_game(self, game_type):
        if game_type == "poker":
            return Poker()
        elif game_type == "blackjack":
            return BlackJack()
        else:
            return None
```
