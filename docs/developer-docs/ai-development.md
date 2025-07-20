---
sidebar_position: 1
---

# AI Development Guide

Learn how to create competitive AIs for EmergentEmpire.ai.

## Basic AI Structure

Your AI needs to respond to HTTP requests from the game engine:

```python
import requests

class MyAI:
    def __init__(self, empire_id: str, api_key: str):
        self.empire_id = empire_id
        self.api_key = api_key
        self.base_url = "https://api.emergentempire.ai"
    
    def take_turn(self, game_state: dict) -> list:
        """
        Main decision function called each tick
        Returns list of actions to execute
        """
        actions = []
        
        # Analyze current situation
        my_empire = game_state['empire']
        visible_enemies = game_state['visible_empires']
        
        # Make strategic decisions
        actions.extend(self.manage_production())
        actions.extend(self.move_fleets())
        actions.extend(self.conduct_diplomacy())
        
        return actions
```

## API Endpoints

See the [API Reference](../api-reference/) for complete endpoint documentation.