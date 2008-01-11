# IRC User Commands
+ register nick         :: /msg NickServ REGISTER password email
+ ID myself             :: /msg NickServ IDENTIFY password
+ ID others             :: /msg NickServ IDENTIFY UserName password
+ NO PM's               :: /umode +g (`/accept nick` whitelists individual nicks)
+ List members in chan  :: /quote names #channel or `/names #channel`

----

# OP commands
+ register IRC channel  :: /cs REGISTER #Channel
+ access chanop list    :: /msg chanserv access #ubuntu-women list
+ all flags             :: +AFORfiorstv
+ temporary Op          :: /op UserName
+ perm Op               :: /cs FLAGS #Channel UserName AOP
+ invite channel        :: /msg chanserv invite #ubuntu-women 
+ Op                    :: /msg chanserv op #ubuntu-women svaksha
+ temp Voice            :: /mode #Channel +v UserName
+ auto Voice            :: /cs FLAGS #Channel UserName +VA
+ ban                   :: /mode #Channel +b [nick!user@host]
+ unban                 :: /mode #Channel -b [nick!user@host]
+ ban immunity          :: /mode #Channel +e [nick!user@host]
+ view ban list         :: /mode #Channel +b
+ SOP                   :: /cs FLAGS #Channel UserName SOP
+ moderate channel      :: /mode #Channel +m
+ Change channel topic  :: /msg chanserv topic #ubuntu-women <add-foo-bar-topic-here>
+ set topic             :: /cs topic #Channel topic-message
+ lock topic            :: /cs set TOPICLOCK
+ cycle                 :: /hop
+ Add Nick to Group     :: 1. login as original account.
                           2. /ns identify newnick originalpassword
                           {OR}
                           1. logout of any accounts /ns logout
                           2. /nick newnick
                           3. /ns identify originalnick originalpassword
                           4. /ns group originalpassword
                           
---- 

# IRSSI
+ Jump windows in irssi) :: /ws NUMBER

----

