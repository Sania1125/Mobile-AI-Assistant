# AI Assistant for Mobile Management (OOP in Python)

class MobileDevice:
    def __init__(self, owner):
        self.owner = owner
        self.battery = 100
        self.airplane_mode = False
        self.wifi = True
        self.screen_locked = False
        self.alarm_set = False

    def check_battery(self):
        return f"Battery level: {self.battery}%"

    def toggle_airplane_mode(self):
        self.airplane_mode = not self.airplane_mode
        status = "ON" if self.airplane_mode else "OFF"
        return f"Airplane mode is now {status}"

    def toggle_wifi(self):
        self.wifi = not self.wifi
        status = "enabled" if self.wifi else "disabled"
        return f"Wi-Fi is now {status}"

    def lock_screen(self):
        self.screen_locked = True
        return "Screen is now locked."

    def unlock_screen(self):
        self.screen_locked = False
        return "Screen is now unlocked."

    def set_alarm(self):
        self.alarm_set = True
        return "Alarm has been set."

    def get_status(self):
        return f"""
Owner: {self.owner}
Battery: {self.battery}%
Airplane Mode: {'ON' if self.airplane_mode else 'OFF'}
Wi-Fi: {'ON' if self.wifi else 'OFF'}
Screen: {'Locked' if self.screen_locked else 'Unlocked'}
Alarm: {'Set' if self.alarm_set else 'Not Set'}
"""


class AIAssistant:
    def __init__(self, name, device):
        self.name = name
        self.device = device

    def respond(self, command):
        print(f"{self.name} is processing your request...")

        if command == "battery":
            print(self.device.check_battery())
        elif command == "airplane":
            print(self.device.toggle_airplane_mode())
        elif command == "wifi":
            print(self.device.toggle_wifi())
        elif command == "lock":
            print(self.device.lock_screen())
        elif command == "unlock":
            print(self.device.unlock_screen())
        elif command == "alarm":
            print(self.device.set_alarm())
        elif command == "status":
            print(self.device.get_status())
        else:
            print("Sorry, I didn't understand that command.")


# Example usage
if __name__ == "__main__":
    phone = MobileDevice("Sania Irshad")
    assistant = AIAssistant("SmartBot", phone)

    assistant.respond("battery")
    assistant.respond("airplane")
    assistant.respond("wifi")
    assistant.respond("lock")
    assistant.respond("unlock")
    assistant.respond("alarm")
    assistant.respond("status")
