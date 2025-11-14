# วิธีติดตั้ง Ruby และ Ruby on Rails บน WSL Ubuntu (64-bit)

## 1. ดาวน์โหลดและติดตั้ง WSL Ubuntu
- ไปที่ลิงก์ดาวน์โหลด: https://ubuntu.com/desktop/wsl
- เลือก Ubuntu 64-bit
- ติดตั้งผ่าน Microsoft Store หรือทำตามขั้นตอนในหน้าเว็บ
- เปิด Ubuntu ครั้งแรกเพื่อตั้งค่า Username/Password

## 2. อัปเดตแพ็กเกจ
sudo apt update && sudo apt upgrade -y

## 3. ติดตั้ง Dependencies สำหรับ Ruby / Rails
sudo apt install -y build-essential libssl-dev libreadline-dev zlib1g-dev libsqlite3-dev nodejs yarn git

## 4. ติดตั้ง rbenv และ ruby-build
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc
echo 'eval "$(rbenv init -)"' >> ~/.bashrc
source ~/.bashrc

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build

## 5. ติดตั้ง Ruby (ตัวอย่าง Ruby 3.2.2)
rbenv install 3.2.2
rbenv global 3.2.2
ruby -v

## 6. ติดตั้ง Rails
gem install rails
rbenv rehash
rails -v

## 7. ติดตั้ง SQLite (ถ้ายังไม่ได้ติดตั้ง)
sudo apt install -y sqlite3 libsqlite3-dev

## 8. สร้างโปรเจกต์ Rails ใหม่
rails new test_app
cd test_app
bin/rails server

## 9. เปิดใช้งานในเบราว์เซอร์
http://localhost:3000

## เสร็จสิ้น 🎉
คุณพร้อมใช้งาน Ruby on Rails บน WSL Ubuntu แล้ว!
