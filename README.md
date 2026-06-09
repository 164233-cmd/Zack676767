# Zack676767
import random

def play_game():
    print("=========================================")
    print("🎮 ยินดีต้อนรับสู่เกมทายตัวเลขอัจฉริยะ! 🎮")
    print("=========================================")
    print("ระบบได้สุ่มตัวเลขระว่าง 1 ถึง 100 ไว้เรียบร้อยแล้ว")
    
    # สุ่มตัวเลข 1 ถึง 100
    secret_number = random.randint(1, 100)
    attempts = 0
    max_attempts = 10
    
    print(f"คุณมีโอกาสทายทั้งหมด {max_attempts} ครั้ง มาเริ่มกันเลย!\n")
    
    while attempts < max_attempts:
        try:
            # รับค่าจากผู้เล่น
            guess = int(input(f"🔮 ครั้งที่ {attempts + 1} - ลองทายตัวเลขมาซิ: "))
        except ValueError:
            print("❌ กรุณากรอกเฉพาะตัวเลขจำนวนเต็มเท่านั้นนะจ๊ะ!")
            continue
            
        attempts += 1
        
        # ตรวจสอบเงื่อนไข
        if guess < secret_number:
            print("💡 น้อยเกินไป! ลองตัวเลขที่มากกว่านี้หน่อย")
        elif guess > secret_number:
            print("💡 มากเกินไป! ลองตัวเลขที่น้อยกว่านี้หน่อย")
        else:
            print(f"\n🎉 ยินดีด้วย!! คุณทายถูกแล้ว! ตัวเลขนั้นก็คือ {secret_number} นั่นเอง")
            print(f"🏆 คุณใช้เวลาทายไปทั้งหมด {attempts} ครั้ง")
            break
        
        # บอกจำนวนครั้งที่เหลือ
        remaining = max_attempts - attempts
        if remaining > 0:
            print(f"⏱️ เหลือโอกาสอีก {remaining} ครั้ง\n")
        else:
            print(f"\n😭 เสียใจด้วยนะ คุณหมดโอกาสแล้ว! ตัวเลขที่ถูกต้องจริงๆ คือ {secret_number}")

if __name__ == "__main__":
    play_game()
