---
title: MediaLine 表格
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每筆記錄代表一個媒體行。  (一個音訊會話通常會包含一個音訊媒體線。 一個音訊和影片 (A/V) 會話通常會包含一個音訊媒體線和一個影片媒體線，但如果使用會議裝置或使用畫廊 View，則會話可能會包含兩個影片媒體線。
ms.openlocfilehash: bb4efba0477193232991732c821aaaa547a19583f8899156a1f92cca119c6b3a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321635"
---
# <a name="medialine-table"></a>MediaLine 表格
 
每筆記錄代表一個媒體行。  (一個音訊會話通常會包含一個音訊媒體線。 一個音訊和影片 (A/V) 會話通常會包含一個音訊媒體線和一個影片媒體線，但如果使用會議裝置或使用畫廊 View，則會話可能會包含兩個影片媒體線。
  
|**欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主要  <br/> |從 [Session 資料表](session.md)參考。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主要  <br/> |從 [Session 資料表](session.md)參考。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |主要  <br/> |0是主要音訊、1是主要影片，2是全景影片，3是應用程式/桌面共用，16是以影片為基礎的螢幕共用 (VbSS) 。 此標籤在單一會話中必須是唯一的。  <br/> |
|**ConnectivityIce** <br/> |Tinyint  <br/> | <br/> |此欄存在，但未用於 Microsoft Lync Server 2013。 CallerConnectivityICE 和 CalleeConnectivityICE 欄中已捕獲用於媒體線之連線的相關資訊。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |有關互動式連線建立 (冰) 程式的資訊，請參閱 bits 旗中所述的處理常式。 如需詳細資訊，請參閱可供下載的  *經驗品質監控伺服器通訊協定規格*  。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |與 CallerIceWarningFlags 相同，但在被呼叫者的一端。 如需詳細資訊，請參閱可供下載的  *經驗品質監控伺服器通訊協定規格*  。 <br/> |
|**安全性** <br/> |Tinyint  <br/> | <br/> |使用中的安全性設定檔。 0 是無 (NONE)，1 是 SRTP，2 是 V1。  <br/> |
|**傳輸** <br/> |Tinyint  <br/> | <br/> |0 是 UDP，1 是 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Foreign  <br/> |來電者的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 發話者使用的連接埠。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | Foreign <br/> |來電者的子網。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CallerInside** <br/> |位  <br/> | <br/> |1表示來電者位於商業網路內，0表示來電者位於網路外。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Foreign  <br/> |來電者的 mac 位址，參考來源為 [MacAddress table](macaddress.md)。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |呼叫者在 A/V Edge service 上使用的埠。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Foreign  <br/> |呼叫者使用的捕獲裝置。 從 [裝置資料表](device.md)中參照。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Foreign  <br/> |由來電者使用的呈現裝置。 從 [裝置資料表](device.md)中參照。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫者的捕獲裝置的驅動程式，參考來源為 [DeviceDriver 表格](devicedriver.md)。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫者的轉譯裝置的驅動程式，參考來源為 [DeviceDriver 表格](devicedriver.md)。  <br/> |
|**CallerNetworkConnectionType** <br/> |Tinyint  <br/> |Foreign  <br/> |會指出來電者連線到網路的方式。 值是從 [NetworkConnectionDetail 表格](networkconnectiondetail.md)取得。 一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |Foreign  <br/> |使用無線時的來電者 BSSID。 從 [MacAddress 資料表](macaddress.md)中參照。  <br/> |
|**CallerVPN** <br/> |位  <br/> ||來電者的連結。 1 是虛擬私人網路 (VPN)，0 是非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |十進位 (18，0)   <br/> ||來電者端點的網路連結速度（bps）。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Foreign  <br/> |通話接收器的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CalleePort** <br/> |位  <br/> ||呼叫接收器使用的埠。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Foreign  <br/> |被呼叫者的子網。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CalleeInside** <br/> |位  <br/> | <br/> |1表示呼叫接收器位於商業網路內，0表示通話接收器位於網路外。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Foreign  <br/> |被呼叫者的 Mac 位址。 從 [MacAddress 表格](macaddress.md)中參照。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器所使用之 A/V Edge service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |呼叫接收器在 A/V Edge Service 上使用的埠。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外國  <br/> |用於呼叫接收器的捕獲裝置。 從 [裝置資料表](device.md)中參照。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Foreign  <br/> |會呈現呼叫接收器所使用的裝置。 從 [裝置資料表](device.md)中參照。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器的捕獲裝置的驅動程式。 從 [DeviceDriver 資料表](devicedriver.md)中參照。  <br/> |
|**CalleeRenderDevDriver** <br/> |Varchar (256)   <br/> |Foreign  <br/> |呼叫接收器的呈現裝置的驅動程式。 從 [DeviceDriver 資料表](devicedriver.md)中參照。  <br/> |
|**CalleeNetworkConnectionType** <br/> |Tinyint  <br/> |Foreign  <br/> |會指出被呼叫者連線到網路的方式。 值是從 [NetworkConnectionDetail 表格](networkconnectiondetail.md)取得。 一般值為0表示 WiFi 連線的有線連接 ' 1;在乙太網路連線時使用3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Foreign  <br/> |使用無線時，被呼叫者的 BSSID。 從 [MacAddress 資料表](macaddress.md)中參照。  <br/> |
|**CalleeVPN** <br/> |位  <br/> | <br/> |通話接收器的連結;1是虛擬私人網路 (VPN) ，0是非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |十進位 (18，0)   <br/> | <br/> |通話接收器端點的網路連結速度（bps）。  <br/> |
|**ConversationalMOS** <br/> |十進位 (3，2)   <br/> | <br/> |音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||這是套用至指定之傳送端資料流程的實際頻寬，指定各種原則設定 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |Smallint  <br/> ||這是所採用的頻寬容量來源。 它說明頻寬限制來自 ( "Policy Server"、"輪流伺服器"、"模態" 等) 。 從 [AppliedBandwidthSource 表格](appliedbandwidthsource.md)中參照。  <br/> |
|**Caller** <br/> |位  <br/> | <br/> |會指出是否已收到來自來電者的計量值;1為 [是]，null 值為 [否]。  <br/> |
|**方** <br/> |位  <br/> | <br/> |會指出是否已收到來自呼叫接收器的計量值;1為 [是]，null 值為 [否]。  <br/> |
|**MidCallReport** <br/> |位  <br/> ||會指出報表是針對會話的一部分，還是完整的會話。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**ClassifiedPoorCall** <br/> |位  <br/> ||會指出呼叫是否分類為 (1) 或良好通話 (0) 的通話是否不良。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CalleeConnectivityICE** <br/> |Tinyint  <br/> ||指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |撥打電話之使用者的反身 IP 位址。 在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |撥打通話之使用者所使用之 WiFi 驅動程式的裝置描述。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |撥打通話之使用者所使用 WiFi 驅動程式的版本號碼。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Foreign  <br/> |接收通話之使用者的反身 IP 位址。 在使用 NAT (網路位址轉譯) 的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Foreign  <br/> |接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Foreign  <br/> |接收通話之使用者所使用 WiFi 驅動程式的版本號碼。  <br/> 此欄是在 Microsoft Lync Server 2013 中引進。  <br/> |
   

