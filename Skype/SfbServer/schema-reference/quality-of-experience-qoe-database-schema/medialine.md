---
title: MediaLine 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: '[MediaLine] 視圖會儲存資料庫中每個媒體線的相關資訊。 一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片 (A/V) 會話通常包含一個音訊媒體線和一個影片媒體線;不過, 如果使用會議裝置或使用圖庫視圖, 該會話可能會包含兩個視頻媒體線。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 03b86aa6e954c61a40a28e1d2c2a0194b581849e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192663"
---
# <a name="medialine-view"></a>MediaLine 視圖
 
[MediaLine] 視圖會儲存資料庫中每個媒體線的相關資訊。 一個音訊會話通常包含一個音訊媒體線。 一個音訊與影片 (A/V) 會話通常包含一個音訊媒體線和一個影片媒體線;不過, 如果使用會議裝置或使用圖庫視圖, 該會話可能會包含兩個視頻媒體線。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |針對呼叫者位數標誌中描述的互動式連線建立 (ICE) 程式的相關資訊。 如需詳細資訊, 請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |針對被呼叫者的 bits 標誌中所述的互動式連線建立 (ICE) 程式的相關資訊。 如需詳細資訊, 請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|安全性  <br/> |Tinyint  <br/> |安全設定檔正在使用中。 0為 [無], 1 為 SRTP, 2 為 V1。  <br/> |
|傳輸  <br/> |Tinyint  <br/> |傳輸類型。 0是 UDP, 1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的埠。  <br/> |
|CallerInside  <br/> |稍微  <br/> |指出來電者是否在組織網路內。 1表示呼叫者是在商業網路內。 0代表呼叫者在網路以外。  <br/> |
|CallerMacAddress  <br/> |Varchar (256)  <br/> |呼叫者使用之網路介面的 MAC 位址。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊, 請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |呼叫者使用的 A/V 邊緣服務上使用的埠。  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |由 A/V 邊緣服務報告的呼叫者 IP 位址。 此位址可能會與 CallerIPAddr (例如, 如果用戶端位於 NAT 之後) 不同。  <br/> |
|CallerCaptureDev  <br/> |Varchar (256)  <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar (256)  <br/> |來電者的轉譯裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar (256)  <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDevDriver  <br/> |Varchar (256)  <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |Varchar (256  <br/> |呼叫者的 Wifi 驅動程式描述。  <br/> |
|CallerWifiDriverVersion  <br/> |Varchar (256)  <br/> |呼叫者的 Wifi 驅動程式版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |Varchar (256)  <br/> |呼叫者網路連線的詳細資料。 如需詳細資訊, 請參閱[NetworkConnectionDetail 資料表](networkconnectiondetail.md)。 <br/> |
|CallerBssid  <br/> |Varchar (256)  <br/> |呼叫者 WiFi 連線所使用的基本服務組識別元。  <br/> |
|CallerVPN  <br/> |稍微  <br/> |指出呼叫者是否已經由虛擬專用網路連接。 1是虛擬私人網路 (VPN), 0 是非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫者使用的埠。  <br/> |
|CalleeInside  <br/> |稍微  <br/> |指出被呼叫者是否在商業網路內。 1代表被呼叫者是在商業網路內, 0 代表被呼叫者在網路以外。  <br/> |
|CalleeMacAddress  <br/> |Varchar (256)  <br/> |被呼叫者使用的網路介面 MAC 位址。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |被呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊, 請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |在被呼叫者所使用的 A/V 邊緣服務上使用的埠。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |被呼叫者的 IP 位址, 由 A/V 邊緣服務所報告。 此位址可能會與 CalleeIPAddr (例如, 如果用戶端位於 NAT 之後) 不同。  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |被呼叫者的擷取裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar (256)  <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleeCaptureDevDriver  <br/> |Varchar (256)  <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar (256)  <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |Varchar (256)  <br/> |被呼叫者的 Wifi 驅動程式描述。  <br/> |
|CalleeWifiDriverVersion  <br/> |Varchar (256  <br/> |被呼叫者的 Wifi 驅動程式版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |Varchar (256)  <br/> |被呼叫者網路連線的詳細資料。 如需詳細資訊, 請參閱[NetworkConnectionDetail 資料表](networkconnectiondetail.md)。 <br/> |
|CalleeBssid  <br/> |Varchar (256)  <br/> |被呼叫者的 WiFi 連線所使用的基本服務組識別元。  <br/> |
|CalleeVPN  <br/> |稍微  <br/> |指出被呼叫者是否已經由虛擬私人網路絡進行連線。 1是虛擬私人網路 (VPN), 0 是非 VPN。  <br/> |
|ConversationalMOS  <br/> |decimal (3, 2)  <br/> |Narrowband 音訊會話的會話 MOS (根據兩個音訊資料流程)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |這是在給定各種原則設定 (TURN、API、SDP、原則伺服器等) 的情況下, 套用到指定傳送端資料流程的實際頻寬。 您應該不要將它與有效的頻寬混淆, 因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬: 傳送資料流程可能會受到頻寬估計所施加的限制。  <br/> |
|AppliedBandwidthSource  <br/> |Varchar (256)  <br/> |強加頻寬上限的來源。 它描述頻寬限制的來源 (例如, 「原則伺服器」、「轉換伺服器」或「模態」)。  <br/> |
|呼叫  <br/> |稍微  <br/> |指出來自來電者的統計資料是否已收到;1為 [是], 0 為 [否]。  <br/> |
|方  <br/> |稍微  <br/> |指出是否已收到來自呼叫接收器的指標;1為 [是], 0 為 [否]。  <br/> |
|MidCallReport  <br/> |稍微  <br/> |指出報告是用於通話的一部分還是完全通話。  <br/> |
|ClassifiedPoorCall  <br/> |稍微  <br/> |指出通話是分類為不佳通話 (1), 或作為良好通話 (0)。  <br/> |
|CallerConnectivityICE  <br/> |Tinyint  <br/> |指示呼叫者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。  <br/> |
|CalleeConnectivityICE  <br/> |Tinyint  <br/> |指示使用者是否使用 ICE 通訊協定 (網際網路連線建立) 與網路連線。  <br/> |
   

