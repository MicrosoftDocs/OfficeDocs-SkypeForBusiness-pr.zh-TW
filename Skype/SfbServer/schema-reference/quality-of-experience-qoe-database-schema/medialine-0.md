---
title: MediaLine 表格
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: 每個記錄代表一個媒體線。 （一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個視頻媒體線，但如果是使用會議裝置或使用了圖庫視圖，該會話可能包含兩個視頻媒體線。
ms.openlocfilehash: 0c189a79a9d87e76ec48be1acb7b4062876b5b16
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808811"
---
# <a name="medialine-table"></a>MediaLine 表格
 
每個記錄代表一個媒體線。 （一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片（A/V）會話通常包含一個音訊媒體線和一個視頻媒體線，但如果是使用會議裝置或使用了圖庫視圖，該會話可能包含兩個視頻媒體線。
  
|**左欄**|**資料類型**|**索引鍵/索引**|**詳細資料**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |首選  <br/> |從[會話資料表](session.md)中參照。  <br/> |
|**SessionSeq** <br/> |int  <br/> |首選  <br/> |從[會話資料表](session.md)中參照。  <br/> |
|**MediaLineLabel** <br/> |Tinyint  <br/> |首選  <br/> |0為主要音訊，1為主要影片，2為全景影片，3為應用程式/桌面共用（VbSS）。 這個標籤在單一會話中必須是唯一的。  <br/> |
|**ConnectivityIce** <br/> |Tinyint  <br/> | <br/> |此欄存在，但在 Microsoft Lync Server 2013 中未使用。 在 CallerConnectivityICE 和 CalleeConnectivityICE 欄中，會捕獲針對媒體線使用之連線性的相關資訊。  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |有關在 bits 標誌中描述的互動式連接建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱*體驗監視伺服器通訊協定規格的品質*（可供下載）。 <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |與 CallerIceWarningFlags 相同，但在被呼叫方端的那一側。 如需詳細資訊，請參閱*體驗監視伺服器通訊協定規格的品質*（可供下載）。 <br/> |
|**安全性** <br/> |Tinyint  <br/> | <br/> |使用中的安全性設定檔。 0為 [無]，1為 SRTP，2為 V1。  <br/> |
|**傳輸** <br/> |Tinyint  <br/> | <br/> |0是 UDP，1是 TCP。  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |外  <br/> |來電者的 IP 位址。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | 呼叫者使用的埠。 <br/> |
|**CallerSubnet** <br/> |int  <br/> | 外 <br/> |來電者的子網。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CallerInside** <br/> |稍微  <br/> | <br/> |1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |外  <br/> |來電者的 mac 位址，從[MacAddress 資料表](macaddress.md)中引用。  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |外  <br/> |呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |呼叫者在 A/V 邊緣服務上使用的埠。  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |外  <br/> |呼叫者使用的擷取裝置。 從[裝置資料表](device.md)中參照。  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |外  <br/> |由呼叫者使用的轉譯裝置。 從[裝置資料表](device.md)中參照。  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |外  <br/> |呼叫者的捕獲裝置驅動程式（從[DeviceDriver 資料表](devicedriver.md)中引用）。  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |外  <br/> |呼叫者轉譯裝置的驅動程式，從[DeviceDriver 資料表](devicedriver.md)參考。  <br/> |
|**CallerNetworkConnectionType** <br/> |Tinyint  <br/> |外  <br/> |指出呼叫者連線到網路的方式。 值是從[NetworkConnectionDetail 資料表](networkconnectiondetail.md)中取得。 對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。  <br/> |
|**CallerBssid** <br/> |int  <br/> |外  <br/> |呼叫者的 BSSID （如果使用無線）。 從[MacAddress 資料表](macaddress.md)中引用。  <br/> |
|**CallerVPN** <br/> |稍微  <br/> ||來電者的連結。 1是虛擬私人網路（VPN），0是非 VPN。  <br/> |
|**CallerLinkSpeed** <br/> |小數（18，0）  <br/> ||呼叫者終點的網路連結速度（以 bps 為來）。  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |外  <br/> |呼叫接收器的 IP 位址。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CalleePort** <br/> |稍微  <br/> ||呼叫接收器使用的埠。  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |外  <br/> |被呼叫者的子網。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CalleeInside** <br/> |稍微  <br/> | <br/> |1代表呼叫接收器在商業網路內，0代表呼叫接收器在網路以外。  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |外  <br/> |被呼叫者的 Mac 位址。 從[MacAddress 資料表](macaddress.md)中參照。  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |外  <br/> |呼叫接收器所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |由呼叫接收器在 A/V 邊緣服務上使用的埠。  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |外  <br/> |捕獲呼叫接收器使用的裝置。 從[裝置資料表](device.md)中參照。  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |外  <br/> |呼叫接收器所使用的轉譯裝置。 從[裝置資料表](device.md)中參照。  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |外  <br/> |呼叫接收器的擷取裝置的驅動程式。 從[DeviceDriver 資料表](devicedriver.md)中引用。  <br/> |
|**CalleeRenderDevDriver** <br/> |Varchar （256）  <br/> |外  <br/> |呼叫接收器的轉譯裝置的驅動程式。 從[DeviceDriver 資料表](devicedriver.md)中引用。  <br/> |
|**CalleeNetworkConnectionType** <br/> |Tinyint  <br/> |外  <br/> |表示被呼叫者連線到網路的方式。 值是從[NetworkConnectionDetail 資料表](networkconnectiondetail.md)中取得。 對於 WiFi 連線，一般的值為0（適用于有線連接，1）;如果是乙太網路連線，則為3。  <br/> |
|**CalleeBssid** <br/> |int  <br/> |外  <br/> |被呼叫者的 BSSID （如果使用無線）。 從[MacAddress 資料表](macaddress.md)中引用。  <br/> |
|**CalleeVPN** <br/> |稍微  <br/> | <br/> |呼叫接收器的連結;1是虛擬私人網路（VPN），0是非 VPN。  <br/> |
|**CalleeLinkSpeed** <br/> |小數（18，0）  <br/> | <br/> |呼叫接收器終點的網路連結速度，以 bps 為限。  <br/> |
|**ConversationalMOS** <br/> |decimal （3，2）  <br/> | <br/> |Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||這是在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。  <br/> |
|**AppliedBandwidthSourceKey** <br/> |Smallint  <br/> ||這是強加頻寬上限的來源。 它描述頻寬限制的來源： [原則伺服器]、[轉換伺服器]、[模態] 等等。 從[AppliedBandwidthSource 資料表](appliedbandwidthsource.md)中參照。  <br/> |
|**呼叫** <br/> |稍微  <br/> | <br/> |指出來自來電者的統計資料是否已收到;1為 [是]，null 值為 [否]。  <br/> |
|**方** <br/> |稍微  <br/> | <br/> |指出是否已收到來自呼叫接收器的指標;1為 [是]，null 值為 [否]。  <br/> |
|**MidCallReport** <br/> |稍微  <br/> ||指出報告是針對會話的一部分或完整的會話。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**ClassifiedPoorCall** <br/> |稍微  <br/> ||指出通話是分類為不佳通話（值為1）或良好通話（0）。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CalleeConnectivityICE** <br/> |Tinyint  <br/> ||指示呼叫者是否使用 ICE 通訊協定（網際網路連線建立）連線至網路。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |撥打電話之使用者的反身 IP 位址。 在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |撥打電話之使用者所採用的 WiFi 驅動程式的裝置描述。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |撥打電話之使用者所採用的 WiFi 驅動程式版本號碼。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |外  <br/> |接收通話之使用者的反身 IP 位址。 在使用 NAT （網路位址轉譯）的組織中，反身 IP 位址是 proxy 伺服器的 IP 位址。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |外  <br/> |接收通話之使用者所使用之 WiFi 驅動程式的裝置描述。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |外  <br/> |接收通話之使用者所使用的 WiFi 驅動程式版本號碼。  <br/> 此欄是在 Microsoft Lync Server 2013 中推出。  <br/> |
   

