# MQTT

IP is used for connection: portal.centrometal.hr (136.243.62.164, old address was 176.9.123.173) and port 1883
Connection username and client id is the same `4EED90D0` and password `BTRG98xV`
On wifi connections it will subscribe to: cm.srv.cmpelet.4EED90D0

Subscribe on topic `cm.srv.cmpelet.4EED90D0`

First start a sync requested:
- P: `{"_sync":"id","_token":"...","clMsgId":0,"_sign":"..."}`
- S: `{"_sync_ACK":"ok","clMsgId":4,"_token":"...","srvMsgId":4,"_sign":"..."}`

Web interface asks refresh:
- S: `{"REFRESH":0,"srvMsgId":25,"_sign":"..."}`
- P: `{"B_Tk1":65.3,"B_Tptv1":65,"B_Tak1":61,"B_Tak2":27,"B_Tdpl1":-8,"B_Tva1":17,"B_Tpov1":-55.0,"B_Ths1":61,"B_fan":0,"B_FotV":32767,"B_puzOn":0.0,"B_puzOff":0.0,"clMsgId":15744333,"_sign":"..."}`
- P: `{"B_STATE":"OFF","B_KONF":12,"B_CMD":0,"B_INST":"PST","B_KONF_STR":"A.7.2","B_Pk":0,"B_Pptv":0,"B_Prec":0,"B_Vptv":0,"B_Pdkg1":0,"B_Pdkg2":0,"B_Mpc":0,"clMsgId":15744334,"_sign":"..."}`
- P: `{"B_Mpo":0,"B_Zc":0,"B_Pbyp":0,"B_bim":0,"B_pres":0,"B_zlj":0,"B_SUP_TYPE":2,"B_VER":"v1.26h","B_sng":"20kW (P3)","B_WifiVER":"v1.15","B_fireS":0,"B_start":0,"clMsgId":15744335,"_sign":"..."}`
- P: `{"B_zahPk":1,"B_zahPtv":1,"B_zahK1":1,"B_zahK2":0,"B_puz":0,"B_gri":0,"B_cm2k":0,"C1B_Tpol1":32.9,"C1B_Tpol":33.2,"C1B_Tsob1":-55.0,"C1B_Tsob":21.0,"C1B_kor":-7.0,"clMsgId":15744336,"_sign":"..."}`
- P: `{"C1B_dayNight":0,"C1B_misO":0,"C1B_misC":0,"C1B_P":1,"C1B_CircType":1,"C1B_onOff":1,"C1B_recSrc":100,"C1B_recType":0,"C1B_korType":0,"C2B_Tpol1":30.0,"clMsgId":15744337,"_sign":"..."}`
- P: `{"C2B_Tpol":33.2,"C2B_Tsob1":-55.0,"C2B_Tsob":21.0,"C2B_kor":-7.0,"C2B_dayNight":0,"C2B_misO":0,"C2B_misC":1,"C2B_P":0,"C2B_CircType":1,"C2B_onOff":0,"C2B_recSrc":100,"clMsgId":15744338,"_sign":"..."}`
- P: `{"B_uklMon":1,"B_freezMon":1,"B_vanjMon":1,"B_netMon":1,"B_kasMon":1,"B_freezEn":0,"B_Add":"802","B_dirKrug":"0","B_uklKot":0,"B_uklPtv":0,"B_uklRec":0,"clMsgId":15744345,"_sign":"..."}`

Schedule request:
- S: `{"PRD 330":"VAL","PRD 327":"ALV","srvMsgId":311164,"_sign":"..."}`
- P: `{"PVAL_330_0":0,"PVAL_327_0":1440,"PVAL_327_1":1440,"PVAL_327_2":1440,"PVAL_327_3":1440,"PVAL_327_4":1440,"PVAL_327_5":1440,"PVAL_327_6":1440,"PVAL_327_7":1440,"clMsgId":15744339,"_sign":"..."}`
- P: `{"PVAL_327_8":1440,"PVAL_327_9":1440,"PVAL_327_10":1440,"PVAL_327_11":1440,"PVAL_327_12":1440,"PVAL_327_13":1440,"PVAL_327_14":1440,"PVAL_327_15":1440,"clMsgId":15744340,"_sign":"..."}`
- P: `{"PVAL_327_16":1440,"PVAL_327_17":1440,"PVAL_327_18":1440,"PVAL_327_19":1440,"PVAL_327_20":1440,"PVAL_327_21":1440,"PVAL_327_22":1440,"PVAL_327_23":1440,"clMsgId":15744341,"_sign":"..."}`
- P: `{"PVAL_327_24":1440,"PVAL_327_25":1440,"PVAL_327_26":1440,"PVAL_327_27":1440,"PVAL_327_28":1440,"PVAL_327_29":1440,"PVAL_327_30":1440,"PVAL_327_31":1440,"clMsgId":15744342,"_sign":"..."}`
- P: `{"PVAL_327_32":1440,"PVAL_327_33":1440,"PVAL_327_34":1440,"PVAL_327_35":1440,"PVAL_327_36":1440,"PVAL_327_37":1440,"PVAL_327_38":1440,"PVAL_327_39":1440,"clMsgId":15744343,"_sign":"..."}`
- P: `{"PVAL_327_40":1440,"PVAL_327_41":1440,"C2B_recType":0,"C2B_korType":0,"B_Time":"68A0E5AC","B_misP":0.0,"B_BRAND":"Centrometal","B_PRODNAME":"Cm Pelet-set","clMsgId":15744344,"_sign":"..."}`

Web interface asks rstat:
- S: `{"RSTAT":"ALL","srvMsgId":81254,"_sign":"..."}`
- P: `{"CNT_0":126072,"CNT_1":0,"CNT_2":0,"CNT_3":9218,"CNT_4":125831,"CNT_5":16061,"CNT_6":4596,"CNT_7":28051,"CNT_8":275691,"CNT_9":0,"CNT_10":0,"CNT_11":0,"clMsgId":1116365,"_sign":"..."}`
- P: `{"CNT_12":0,"CNT_13":0,"CNT_14":0,"CNT_15":0,"clMsgId":1116366,"_sign":"..."}`

### Observed parameters and values

**Only checked cmpelet type and values**

- B_Add Additional features
- B_AddConf Accessories
- B_bim
- B_BRAND Brand: Centrometal
- B_cm2k CM2K Status
- B_CMD Command active: 0
- B_cmsr100 Pellet Tank Level
- B_CP CentroPlus
- B_dirKrug
- B_fan Heater Fan State: 1160, 3000, 0, 2500, 1200, 2300, 1230, 1630, 2380, 1380, 1280, 2200, 1560, 1080, 1290, 1170, 900, 1150, 1240, 1430, 1400, 1550, 2100, 1900, 2350, 2450, 1350, 2680, 1600, 1700, 1950, 1500, 2400, 1850, 1450, 1800, 2070, 1660, 1190, 1610, 1860, 1210, 2270, 1440, 1180, 1270, 1140, 1410, 1455, 1460, 1000, 1580, 1070, 1488, 2330, 2130, 1953, 950
- B_fanO
- B_fireS
- B_FotV Fire Sensor
- B_freezEn Freeze Guard
- B_freezMon Freeze Monitor
- B_gri Heater State: 1, 0
- B_INST Installation: PST
- B_kasMon
- B_KONF Setup: 56, 33, 2, 1, 3, 26, 18, 30, 9, 27
- B_KONF_STR Setup: E.1.2, C.2.1, A.0.1, A.0.0, A.0.2, C.0.0, B.1.0, C.1.1, A.2.2, C.0.1
- B_korNum Accessories Value
- B_ldOnOff
- B_misP Mixing Valve
- B_Mpc
- B_Mpo
- B_netMon Remote Start Enabled
- B_Oxy1 Lambda Sensor
- B_Pbyp
- B_Pdkg1
- B_Pdkg2
- B_Pk Boiler Pump
- B_Pptv
- B_Prec
- B_pres
- B_PREUZ
- B_PRODNAME Product name: Cm Pelet-set
- B_puz Pellet Transporter
- B_puzOff
- B_puzOn: 0, 5, 1, 4, 6, 2, 7, 11, 9, 14, 3.5
- B_razP
- B_signal
- B_SMD
- B_sng Nominal power: 20kW (P3), 25kW (P4), 35kW (P6), 70kW (P5), 50kW (P6)
- B_start
- B_STATE Boiler state: OFF, PP3, S7-2, A5, S7-3, PP4, A0, A7-3, A2, PP1, A6, S7-1, A3, P, A4, M-1, PP2, M-2, A1, PP5, P4, P3, P2-2, P1-3, P2-5, P6, P4-2, P2-3, M-3, P2, A7-1, A7-2
- B_SUP_TYPE: 2
- B_Tak1 Buffer Tank Up
- B_Tak2 Buffer Tank Down
- B_Tdpl1 Flue Gas
- B_Ths1 Hydraulic Crossover Temperature
- B_Time Clock
- B_Tk1 Boiler Temperature
- B_Tpov1 Mixer Temperature
- B_Tptv1 Domestic Hot Water
- B_Tva1 Outdoor Temperature
- B_uklKot Boiler Operational: 0, 2, 1
- B_uklMon
- B_uklPtv
- B_uklRec
- B_vanjMon
- B_VER Firmware version: v1.26f, v1.23g, v1.26h, v1.26g, V1.26g
- B_Vptv
- B_WifiVER Wifi Box version: v1.15 or v1.10
- B_zahK1
- B_zahK2
- B_zahPk
- B_zahPtv
- B_Zc
- B_zlj Operation Mode: 1, 0, 2
- CNT_0 Burner Work
- CNT_1 Working DHW only
- CNT_2 Freeze protection
- CNT_3 Number of Burner Start
- CNT_4 Fan Working Time
- CNT_5 Electric Heater Working Time
- CNT_6 Number of Electric Heater Start
- CNT_7 Vacuum Turbine Working Time
- CNT_8 Boiler pump
- CNT_9
- CNT_10
- CNT_11
- CNT_12
- CNT_13
- CNT_14
- CNT_15
