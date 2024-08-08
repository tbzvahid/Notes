### Clear ASA 5520 Configuration
rommon #0> <b>configreg 0x41 </b></br>
rommon #1> <b>boot </b></br>
ciscoasa> <b>en </b></br>
Password: only Press Enter </br>
ciscoasa# <b>conf t </b></br>
ciscoasa(config)# <b>config-register 0x01 </b></br>
ciscoasa(config)# <b>copy running-config startup-config </b></br>
ciscoasa(config)# <b>reload </b></br>
