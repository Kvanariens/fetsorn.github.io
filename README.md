# vlg_line

https://t.me/



sort_by_state(devices_state)
print("Р’РєР»СЋС‡РµРЅС‹:", [d["name"] for d in on_devices])
print("Р’С‹РєР»СЋС‡РµРЅС‹:", [d["name"] for d in off_devices])

# РџСЂРёРјРµСЂ СЂР°СЃРїРёСЃР°РЅРёСЏ РґР»СЏ Р°РІС‚РѕРјР°С‚РёС‡РµСЃРєРѕРіРѕ РІРєР»СЋС‡РµРЅРёСЏ/РІС‹РєР»СЋС‡РµРЅРёСЏ СѓСЃС‚СЂРѕР№СЃС‚РІ

import schedule
import time

def turn_on(device):
    print(f"Р’РєР»СЋС‡РµРЅРёРµ: {device}")

def turn_off(device):
    print(f"Р’С‹РєР»СЋС‡РµРЅРёРµ: {device}")

# РџСЂРёРјРµСЂ СЂР°СЃРїРёСЃР°РЅРёСЏ
schedule.every().day.at("07:00").do(turn_on, "Light")
schedule.every().day.at("07:05").do(turn_on, "Thermostat")
schedule.every().day.at("22:00").do(turn_off, "Light")
schedule.every().day.at("23:00").do(turn_off, "Thermostat")

# Р—Р°РїСѓСЃРє СЂР°СЃРїРёСЃР°РЅРёСЏ
print("\nРђРІС‚РѕРјР°С‚РёС‡РµСЃРєРѕРµ СѓРїСЂР°РІР»РµРЅРёРµ СѓСЃС‚СЂРѕР№СЃС‚РІР°РјРё РїРѕ СЂР°СЃРїРёСЃР°РЅРёСЋ:")
# РџСЂРѕРїСѓСЃС‚РёС‚СЊ РІС‹РїРѕР»РЅРµРЅРёРµ РІ С‚РµРєСѓС‰РµРј РїСЂРёРјРµСЂРµ РґР»СЏ РїСЂРѕСЃС‚РѕС‚С‹
# while True:
#     schedule.run_pending()
#     time.sleep(1)

# РЈР»СѓС‡С€РµРЅРёРµ Р±РµР·РѕРїР°СЃРЅРѕСЃС‚Рё СЃРёСЃС‚РµРјС‹

def enhance_security(devices):
    for device in devices:
        if device['category'] == 'Security':
            device['protection'] = 'high'
        else:
            device['protection'] = 'medium'
    return devices

# РџСЂРёРјРµСЂ СѓСЃС‚СЂРѕР№СЃС‚РІ
devices_security = [
    {"name": "Door Lock", "category": "Security"},
    {"name": "Light", "category": "Comfort"},
    {"name": "Camera", "category": "Security"}
]

# РЈР»СѓС‡С€РµРЅРёРµ Р±РµР·РѕРїР°СЃРЅРѕСЃС‚Рё
print("\nРЈР»СѓС‡С€РµРЅРёРµ Р±РµР·РѕРїР°СЃРЅРѕСЃС‚Рё:")
secure_devices = enhance_security(devices_security)
for device in secure_devices:
    print(f"{device['name']} - Protection Level: {device['protection']}")
