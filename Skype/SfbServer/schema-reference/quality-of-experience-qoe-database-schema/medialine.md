---
title: MediaLine view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: 媒體行檢視會儲存資料庫中每一媒體行的相關資訊。 一個音訊工作階段通常會包含一個音訊媒體行。 一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: fa527c31c1011fdcad38d21534e9ec1c1a4ec96e4a704dd79722313e73a39056
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296920"
---
# <a name="medialine-view"></a>MediaLine view
 
媒體行檢視會儲存資料庫中每一媒體行的相關資訊。 一個音訊工作階段通常會包含一個音訊媒體行。 一個音訊和視訊 (A/V) 工作階段通常包含一個音訊媒體行和一個視訊媒體行；不過，如果使用會議裝置或使用圖庫檢視，則工作階段可能包含兩個媒體行。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**細節**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|安全性  <br/> |Tinyint  <br/> |使用中的安全性設定檔。0 是無 (NONE)，1 是 SRTP，2 是 V1。  <br/> |
|傳輸  <br/> |Tinyint  <br/> |傳輸類型。0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |發話者的 IP 位址，可以是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |發話者使用的連接埠。  <br/> |
|CallerInside  <br/> |位  <br/> |指出發話者是否在組織網路內。1 代表發話者在企業網路內。0 代表發話者在網路外。  <br/> |
|CallerMacAddress  <br/> |Varchar (256)   <br/> |發話者使用之網路介面的 MAC 位址。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |發話者在 A/V Edge Service 上使用的連接埠。  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)   <br/> |由 A/V Edge service 報告之來電者的 IP 位址。 例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CallerIPAddr。  <br/> |
|CallerCaptureDev  <br/> |Varchar (256)   <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar (256)   <br/> |來電者的呈現裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar (256)   <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDevDriver  <br/> |Varchar (256)   <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |Varchar (256  <br/> |來電者的 Wifi 驅動程式描述。  <br/> |
|CallerWifiDriverVersion  <br/> |Varchar (256)   <br/> |來電者的 Wifi 驅動程式版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |Varchar (256)   <br/> |呼叫者網路連線的詳細資料。 如需詳細資訊，請參閱 [NetworkConnectionDetail 表格](networkconnectiondetail.md) 。 <br/> |
|CallerBssid  <br/> |Varchar (256)   <br/> |發話者 WiFi 連線所使用的基本服務組識別碼。  <br/> |
|CallerVPN  <br/> |位  <br/> |指出發話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |受話者使用的連接埠。  <br/> |
|CalleeInside  <br/> |位  <br/> |指出受話者是否在企業網路內。1 代表受話者在企業網路內，0 代表受話者在網路外。  <br/> |
|CalleeMacAddress  <br/> |Varchar (256)   <br/> |受話者使用之網路介面的 MAC 位址。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |受話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |受話者在 A/V Edge Service 上使用的連接埠。  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)   <br/> |受話者的 IP 位址，由 A/V Edge service 所報告。 例如，如果用戶端位在 NAT 後面，此位址可能會不同於 CalleeIPAddr。  <br/> |
|CalleeCaptureDev  <br/> |var (50)   <br/> |被呼叫者的捕獲裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleeCaptureDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |Varchar (256)   <br/> |被呼叫者的 Wifi 驅動程式描述。  <br/> |
|CalleeWifiDriverVersion  <br/> |Varchar (256  <br/> |被呼叫者的 Wifi 驅動程式版本。  <br/> |
|CalleeNetworkConnectionDetail  <br/> |Varchar (256)   <br/> |被呼叫者網路連線的詳細資料。 如需詳細資訊，請參閱 [NetworkConnectionDetail 表格](networkconnectiondetail.md) 。 <br/> |
|CalleeBssid  <br/> |Varchar (256)   <br/> |被呼叫者的 WiFi 連線所使用的基本服務設定識別碼。  <br/> |
|CalleeVPN  <br/> |位  <br/> |指出受話者是否透過虛擬私人網路來連線。1 是虛擬私人網路 (VPN)，0 是非 VPN。  <br/> |
|ConversationalMOS  <br/> |十進位 (3，2)   <br/> |音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |這是在指定各種原則設定 (TURN、API、SDP、Policy Server 等等) 的情況下，套用至指定傳送端資料流的實際頻寬。不要將這個與有效頻寬混淆，因為根據頻寬預估值，會有較低的有效頻寬。基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。  <br/> |
|AppliedBandwidthSource  <br/> |Varchar (256)   <br/> |所採用的頻寬容量來源。 它說明頻寬限制來自 (，例如「原則伺服器」、「輪流伺服器」或「模態」 ) 。  <br/> |
|Caller  <br/> |位  <br/> |指出是否收到發話者的計量；1 為是，0 為否。  <br/> |
|方  <br/> |位  <br/> |指出是否收到受話者的計量；1 為是，0 為否。  <br/> |
|MidCallReport  <br/> |位  <br/> |指出此報告適用於部分通話或完整通話。  <br/> |
|ClassifiedPoorCall  <br/> |位  <br/> |指出通話分類為通話不良 (1) 或通話良好 (0)。  <br/> |
|CallerConnectivityICE  <br/> |Tinyint  <br/> |指出發話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。  <br/> |
|CalleeConnectivityICE  <br/> |Tinyint  <br/> |指出受話者是否使用 ICE 通訊協定 (網際網路連線建立) 連線至網路。  <br/> |
   

