# RS Makeup Studio WhatsApp AI Bot — Starter

Yeh Node.js starter app WhatsApp Cloud API webhook aur Gemini API ko jodta hai.

## Is starter mein kya hai?
- Meta webhook verification (`GET /webhook`)
- Incoming WhatsApp text messages receive karna (`POST /webhook`)
- Gemini se Hindi/Hinglish reply generate karna
- Studio address aur human handover ke simple replies
- Health endpoint: `/health`

## Abhi kya included NAHI hai?
- Yeh code khud se deploy nahi hua hai.
- Yeh daily scheduled broadcasts nahi bhejta.
- Booking details ko database/sheet mein save nahi karta.
- Final appointment calendar mein reserve/confirm nahi karta.
- WhatsApp API access, approved phone number setup, webhook URL aur API keys tumhe configure karni hongi.

## Zaroori accounts
1. Meta for Developers: https://developers.facebook.com/
2. WhatsApp Business Platform: https://whatsappbusiness.com/developers/developer-hub/
3. Google AI Studio API key: https://aistudio.google.com/apikey
4. Hosting account, for example Render: https://render.com/

## Setup summary
1. ZIP ko extract karo.
2. Folder ko GitHub repository mein upload karo. `.env` ya real API keys upload mat karna.
3. Render par New > Web Service se repository connect karo.
4. Build command: `npm install`
5. Start command: `npm start`
6. Render Environment Variables mein `.env.example` ke variables ko real values ke saath set karo.
7. Deploy ke baad `https://YOUR-SERVICE.onrender.com/health` open karo. JSON `{"ok":true,...}` aana chahiye.
8. Meta Developer app mein WhatsApp product/webhooks configure karo:
   - Callback URL: `https://YOUR-SERVICE.onrender.com/webhook`
   - Verify token: wahi value jo `WHATSAPP_VERIFY_TOKEN` mein set ki hai
   - Webhook field `messages` subscribe karo.
9. Meta dashboard se test message bhejo. Pehle test number se verify karo; phir production number migration/coexistence instructions carefully follow karo.

## Important
- `GRAPH_API_VERSION` ko Meta dashboard/documentation mein currently supported Graph API version ke mutabik update karo.
- WhatsApp Cloud API ka billing/message-template rules apply ho sakte hain.
- Render free web services idle hone par sleep karti hain; webhook reply mein delay ho sakta hai. Production customer service ke liye free hosting reliable guarantee nahi hai.
- Existing WhatsApp Business number ko API se connect karne se pehle Meta ke current number coexistence/migration rules check karo. Bina samjhe number migrate mat karna.
- Google Gemini free tier ki limits aur data-use terms check karo. Customer ke private/sensitive details prompt mein mat daalo.
- Daily promotional messages ke liye opt-in aur WhatsApp rules follow karo. Unsolicited bulk messages mat bhejo.
