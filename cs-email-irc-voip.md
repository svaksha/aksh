+ [EMail](#email)
+ [IRC](#irc)
+ [Mailing List](#mailing-list)
+ [Mobile](#mobile)
+ [VOIP](#voip)

----

# [EMail](https://en.wikipedia.org/wiki/Comparison_of_webmail_providers)
+ https://en.wikipedia.org/wiki/Bitmessage
+ [MJML](https://github.com/mjmlio/mjml) :: A framework that makes responsive-email easy.
+ Building an Email Server on Ubuntu Linux, Part-3 ::https://www.linux.com/learn/sysadmin/building-email-server-ubuntu-linux-part-3

----


# IRC 

## IRSSI User Commands
+ Jump windows (in irssi) :: /ws NUMBER
+ register nick         :: /msg NickServ REGISTER password email
+ ID myself             :: /msg NickServ IDENTIFY password
                        :: /msg nickserv set accountname NICK 

### [GHOST](https://toxin.jottit.com/freenode_nickserv_commands#ns09)
GHOST Reclaims use of a nickname.
+ GHOST                 :: /msg NickServ GHOST NICK password
+ RELEASE (freenode, cl):: /msg NickServ RELEASE NICK password
  REGAIN (moznet)       :: /msg NickServ REGAIN NICK password
  RECLAIM (OFTC)        :: /msg NickServ RECLAIM NICK password

### commands 
+ ID others             :: /msg NickServ IDENTIFY NICK password
+ NO PM's               :: /umode +g (`/accept nick` whitelists individual nicks)
+ List members in chan  :: /quote names #channel or `/names #channel`
+ search                :: /msg alis help list  (format /msg alis list #india*)
+ User Info             :: /msg nickserv info NICK ALL, (OR) /msg nickserv info NICK
                           /msg socinfo factoids search #women * 
                           /query socinfo on #women

## ChanOP commands
+ register IRC channel  :: /cs REGISTER #Channel

### [Access](https://toxin.jottit.com/freenode_nickserv_commands#ns18)
+ access chanop list    :: /msg chanserv access #ubuntu-women list {/msg ChanServ ACCESS LIST #CHANNEL}
                        :: /msg NickServ ACCESS LIST
                           /msg NickServ ACCESS ADD jack@host.example.com
                           /msg NickServ ACCESS ADD user@10.0.0.8
                           /msg NickServ ACCESS ADD jilles@192.168.1.0/24
                           /msg NickServ ACCESS DEL *someone@*.area.old.example.net 
+ all flags             :: +AFORfiorstv
+ temporary Op          :: /op NICK
+ perm Op               :: /cs FLAGS #Channel NICK AOP
+ invite channel        :: /msg chanserv invite #ubuntu-women 
+ Op                    :: /msg chanserv op #ubuntu-women svaksha
+ temp Voice            :: /mode #Channel +v NICK
+ auto Voice            :: /cs FLAGS #Channel NICK +VA
+ remove trolls (temp)  :: /remove #channel nick :reason      
+ ban                   :: /mode #Channel +b [nick!user@host]
+ unban                 :: /mode #Channel -b [nick!user@host]
+ ban immunity          :: /mode #Channel +e [nick!user@host]
+ view ban list         :: /mode #Channel +b
+ SOP                   :: /cs FLAGS #Channel NICK SOP
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

# [Mailing List](https://en.wikipedia.org/wiki/Category:Free_mailing_list_software)

## [Discourse](https://en.wikipedia.org/wiki/Discourse_%28software%29)

----

# Mobile
+ https://en.wikipedia.org/wiki/List_of_open-source_mobile_phones

----

# VOIP
+ https://en.wikipedia.org/wiki/Comparison_of_VoIP_software 

+ https://en.wikipedia.org/wiki/List_of_free_and_open-source_Android_applications
+ https://en.wikipedia.org/wiki/Signal_%28software%29

----
