# React Firebase Authentication Project
- Bu projde Firebase Firestore kullanlarak;
  - Kullanıcı oluşturma,
  - Gücelleme,
  - Giriş ve Çıkış İşlemleri,
  - Database Oluşturma,
  - Database Veri Kadetme,Güncelleme ve Silme,
  - Database güvenlik kuralları oluşturma,
  - Zaman Formatlama,
  İşlemlerini Başarılı Bir Şekilden Gerçekleştirdik.



#Kütüphaneler

- react-router-dom
- firebase
- react-hot-toast
-npm install -D tailwindcss
    npx tailwindcss init
-tailwindui
- @tailwindcss/forms
- npm install @reduxjs/toolkit
- npm install react-redux
- npm install @headlessui/react
- npm install @formkit/auto-animate
- npm i dayjs 

notlar:
- eğer kullanıcı girişi yapılmadan bilgilere erişşimi engellmek istiyorsak firbase de rules kısmında 
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if  request.auth!=null;    //bu kısmı ekliyoruz.
    }
  }
}
- eğer kullanıcı tüm işlemleri yapabilmesini istiyorsak;
    rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /todos/{document=**} {
      allow read, write,update,delete,create: if  request.auth!=null&&request.auth.uid==resource.data.uid;
    }
  }
}
# React-Firebase-Authentication-Project
![Zight Recording 2024-09-30 at 11 44 22 PM](https://github.com/user-attachments/assets/22a0918f-c86e-44cd-9066-9daa49a84742)


