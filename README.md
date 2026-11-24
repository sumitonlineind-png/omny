# Omnicademy: poora setup (shuru se)

Is zip mein:
- index.html : poori website (Firebase config pehle se bhari hui)
- firestore.rules : database ke rules
- storage.rules : file upload ke rules
- firebase.json, .vercelignore : deploy ke liye

## 1. Firebase console (ek baar)
1. **Authentication > Sign-in method > Email/Password** ko Enable karo.
2. **Firestore Database**: agar database nahi hai to Create database dabao. Database ID `(default)` rakho. (Agar pehle se `default` naam ka database hai to wo bhi chalega, site dono check karti hai.)
3. Firestore ke **Rules** tab mein saara purana code hata do. firestore.rules ka poora code paste karo aur **Publish** dabao.
4. (PDF upload chahiye to) **Storage** > Get started. Phir Storage ke Rules mein storage.rules paste karke Publish karo.
5. **Authentication > Settings > Authorized domains** mein apni Vercel site ka domain jodo (https:// ke bina).

## 2. Vercel par deploy
Is folder ko unzip karo. Terminal mein folder ke andar: `npm install -g vercel`, phir `vercel --prod`.
Ya GitHub par daal kar vercel.com/new se Import karo (Framework: Other).

## 3. Pehla admin banao
1. Site par Menu > Student Login / Sign Up se account banao.
2. Menu > Admin Login dabao. Ek box aayega jisme aapki ID hai.
3. Firestore > Start collection > Collection ID `admins` > Document ID: wahi ID > koi ek field (ok = true) > Save.
4. "I added it, check again" dabao. Admin Dashboard khul jayega.

## Agar kuch na chale
Admin Login ke box mein "Result:" wali line padho. Wo batati hai ki database mila ya nahi, rules publish hue ya nahi, ya browser (Brave Shields / ad-blocker) connection rok raha hai. Brave mein sher (lion) icon dabakar is site ke liye Shields off karke dekho.

## Dhyan rakhne wali baatein
- Password Firebase Authentication sambhalta hai, database mein save nahi hota.
- Students ka email aur district sirf admins dekh sakte hain. Doubts par naam aur class dikhti hai.
- Students minors ho sakte hain, school/mentors se permission le lena theek rahega.
- Storage naye projects mein Blaze (pay-as-you-go) plan maang sakta hai.

## AI Tutor (Botpress) jodna
1. Botpress mein bot banao (Studio ya Dashboard se). Webchat > Deploy Settings (ya Studio mein Share > Configure) se Embed code kholo.
2. Embed code mein 2 script tags hote hain. Dono ke `src` link copy karo: pehla `.../inject.js`, doosra `https://files.bpcontent.cloud/...js`.
3. index.html mein `const BOTPRESS={inject:"",config:""};` dhoondo (Ctrl+F: BOTPRESS). Pehle link ko `inject` ke quotes mein, doosre ko `config` ke quotes mein paste karo.
4. Dobara deploy karo. Ask Doubt section mein demo ki jagah "Chat with our AI Tutor" wala card aa jayega.
