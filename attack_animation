from enum import Enum
import arcade


class AttaqueType(Enum):
    NOT_STARTED = 0
    ROCK = 1
    PAPER = 2
    SCISSOR = 3


class AttackAnimation(arcade.Sprite):
    ATTACK_SCALE = 0.50
    ANIMATION_SPEED = 5.0

    def __init__(self, attack_type):
        super().__init__()
        self.an_update_time = 1.0 / AttackAnimation.ANIMATION_SPEED
        self.time_since_last_swap = 0.0
        self.atack_typ = attack_type
        if self.atack_typ == AttaqueType.ROCK:
            self.texture = [
                arcade.load_texture("assets/srock.png"),
                arcade.load_texture("assets/srock-attack.png"),
            ]
        elif self.atack_typ == AttaqueType.PAPER:
            self.texture = [
                arcade.load_texture("assets/spaper.png"),
                arcade.load_texture("assets/spaper-attack.png"),
            ]
        else:
            self.texture = [
                arcade.load_texture("assets/scissors.png"),
                arcade.load_texture("assets/scissors-close.png"),
            ]

        self.scale = self.ATTACK_SCALE
        self.current_texxt_lol = 0
        self.set_texture(self.current_texxt_lol)

    def on_update(self, delta_time: float = 1 / 60):
        # Update the animation.
        self.time_since_last_swap += delta_time
        if self.time_since_last_swap > self.an_update_time:
            self.current_texxt_lol += 1
            if self.current_texxt_lol < len(self.texture):
                self.set_texture(self.current_texxt_lol)
            else:
                self.current_texxt_lol = 0
                self.set_texture(self.current_texxt_lol)
            self.time_since_last_swap = 0.0
