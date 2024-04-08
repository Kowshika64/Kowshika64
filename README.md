import random
characters ="ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"
captcha =""
for i in range(5):
    captcha += random.choice(characters)

    print("Generated Captcha:",captcha
