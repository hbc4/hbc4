# hbc4
hunter
line_bot_api . narrowcast (
     الرسائل = TextSendMessage ( النص = "مرحبا أيها العالم!" )،
     المستلم = AudienceRecipient ( group_id = 5614991017776 )،
     مرشح = تصفية ( الديموغرافية = AgeFilter ( GTE = "age_35" ، لتر = "age_40" ))،
     الحد = الحد ( الحد الأقصى = 600 )
)الملف الشخصي  =  line_bot_api . get_profile ( user_id )

print ( profile . display_name )
 print ( profile . user_id )
 print ( profile . picture_url )
 print ( profile . status_message )
الملف الشخصي  =  line_bot_api . get_group_member_profile ( group_id ، user_id )

print ( profile . display_name )
 print ( profile . user_id )
 print ( profile . picture_url )

الملف الشخصي  =  line_bot_api . get_room_member_profile ( room_id ، user_id )

print ( profile . display_name )
 print ( profile . user_id )
 print ( profile . picture_url )

message_content  =  line_bot_api . get_message_content ( message_id )

مع  فتح ( FILE_PATH ، 'البنك الدولي' ) كما  فد :
     لل  قطعة  في  MESSAGE_CONTENT . iter_content ():
         fd . اكتب ( مقطع )
