# hbc4
hunter
$ pip تثبيت line-bot-sdk
من  قارورة  استيراد  قارورة ، طلب ، إحباط

من  linebot  استيراد (
     LineBotApi ، WebhookHandler
)
من  linebot . استيراد استثناءات  (
     InvalidSignatureError
)
من  linebot . استيراد النماذج  (
     MessageEvent ، TextMessage ، TextSendMessage ،
)

التطبيق  =  قارورة ( __name__ )

line_bot_api  =  LineBotApi ( 'YOUR_CHANNEL_ACCESS_TOKEN' )
 معالج  =  WebhookHandler ( 'YOUR_CHANNEL_SECRET' )


@ التطبيق . route ( "/ callback" ، الأساليب = [ 'POST' ]) 
def  callback ():
     # get X-Line-Signature قيمة رأس 
    التوقيع  =  طلب . رؤوس [ "X-Line-Signature" ]

    # الحصول على نص طلب كنص 
    الجسم  =  طلب . get_data ( as_text = صحيح )
     التطبيق . مسجل . معلومات ( "طلب الهيئة:"  +  الجسم )

    # مقبض هيئة webhook 
    حاول :
         معالج . مقبض ( الجسم ، توقيع )
     باستثناء  InvalidSignatureError :
         طباعة ( "التوقيع غير صالح الرجاء التحقق من وصول قناتك رمز سر / قناة." )
         إحباط ( 400 )

    إرجاع  "موافق"


@ معالج . أضف ( MessageEvent ، message = TextMessage ) 
def  handle_message ( event ):
     line_bot_api . reply_message (
         event . reply_token ،
         TextSendMessage ( text = event . message . text ))


إذا  __name__  ==  "__main__" :
     التطبيق . تشغيل ()
