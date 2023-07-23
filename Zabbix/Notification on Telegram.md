## Recieve Zabbix notification on Telegram

a- Create a Bots , ID and Channel on Telegram
 1- Go to @botFather
 2- type /newbot
 3- enter the name ELXBOT
 4- Choose Username for your bot ELXBOT_bot (you have to add a bot at the end )
 5- HTTP API created
 6- Go to ELXBOT
 7- type /start
 8- Create a New Channel name it ELXChannel
 9- go to ELXBOT and add this bot to ELXChannel (Post Messages right has to enable when adding )
 10- Go to IDBot and add this bot to ELXChannel 
 11-Go to ELXChannel and type /getgroupid
b-Configure Telegram Media Type
1- browse the following address https://git.zabbix.com/projects/ZBX/repos/zabbix/browse/templates/media/telegram/media_telegram.yaml?at=refs%2Fheads%2Frelease%2F6.4
2- choose you Zabbix version
3- Copy the content of media_telegram.yaml then create a file and name it media_telegram.yaml paste into this file.
4- go to Zabbix - Alert - Media Type choose Import, from Import File, browse to select media_telegram.yaml then only check Update existing at last click on Import.
5- Click on MediaType tab and fill out fields as the following
 1-ParseMode = MarkdownV2
 2-Token = HTTP API
 3- Check Proccess Tag
6-to save Configuration click on Update
7- on the same page in front of telegram click on Test , in the pop-up windows fill out the fields as the following
 1-To = Channel ID
 2-Token = HTTP API
8- Click on Test, and you will see Media Type test Successful. If you configured everything correctly.
c- Create a User, a User Group, a User Role
 1-Create a User Role 
   1- name it ROUSR only check Dashboard and from Monitoring Problemes and Latest Data Click on Update to Save.
 2- Create a User and assign User Role and User Group
  1-In User tab fill out as the following
    1- Username = ELXCRMUSR
    2- Password = set password
    3- Time Zone = Choose correct Time Zone
  2-In Media tab click on Add and as the below
    1- Type = Telegram
    2- Send to = Channel ID
    Click on Add then Update
 3- Create a User Group and do the following
   1- in User Group tab
    1-Group name = ELXCRM
    2-Users = ELXCRMUSR
   2-In Host permissions tab
    1-Select Host group then Read and also check Include subgroups click on Add
   3-In Problem tag filter
    1- Select Host group and check Include subgroups Click on Add at last click on Update
 
 
