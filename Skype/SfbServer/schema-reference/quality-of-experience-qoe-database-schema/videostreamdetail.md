---
title: VideoStreamDetail 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: '[VideoStreamDetail] 視圖會儲存資料庫中每個影片資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 3fb598feec3b4dca87086504c620109a99bce7d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804143"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 視圖
 
[VideoStreamDetail] 視圖會儲存資料庫中每個影片資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**說明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|StreamId  <br/> |int  <br/> |媒體線中的唯一識別碼。  <br/> |
|開始  <br/> |datetime  <br/> |會話的開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |會話的結束時間。  <br/> |
|CallPriority  <br/> |int  <br/> |通話的優先順序。  <br/> |
|CallerPool  <br/> |Nvarchar （256）  <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar （256）  <br/> |被呼叫方池 FQDN。  <br/> |
|呼叫  <br/> |Nvarchar （450）  <br/> |來電者的 URI。  <br/> |
|方  <br/> |Nvarchar （450）  <br/> |被呼叫者的 URI。  <br/> |
|CallerUserAgent  <br/> |Nvarchar （256）  <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |呼叫者的使用者代理程式類型。 如需詳細資訊，請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar （64）  <br/> |呼叫者的使用者代理類別。 如需詳細資訊，請參閱[UserAgentDef 資料表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar （256）  <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |被呼叫者的使用者代理程式類型。 請參閱[UserAgent 資料表](useragent.md)以取得相關資訊。 <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar （64）  <br/> |被呼叫者的使用者代理程式類別。 如需資訊，請參閱[UserAgentDef 資料表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |Nvarchar （256）  <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar （256）  <br/> |被呼叫者的端點名稱。  <br/> |
|CallerOS  <br/> |Nvarchar  <br/> |呼叫者終點的作業系統（OS）。  <br/> |
|CalleeOS  <br/> |Nvarchar  <br/> |被呼叫者的端點的作業系統（OS）。  <br/> |
|CallerCPUName  <br/> |Nvarchar  <br/> |呼叫者終點的 CPU 名稱。  <br/> |
|CalleeCPUName  <br/> |Nvarchar  <br/> |被呼叫者的端點的 CPU 名稱。  <br/> |
|CallerCPUNumberOfCores  <br/> |Smallint  <br/> |呼叫者終點的 CPU 核心數。  <br/> |
|CalleeCPUNumberOfCores  <br/> |Smallint  <br/> |被呼叫者的端點的 CPU 核心數。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者終點的 CPU 處理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被呼叫者的端點的 CPU 處理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |Tinyint  <br/> |指出呼叫者的系統在虛擬化環境中是否正在執行。 如需詳細資訊，請參閱[端點資料表](endpoint.md)。 <br/> |
|CalleeVirtualizationFlag  <br/> |Tinyint  <br/> |指出被呼叫者的系統是否正在虛擬化環境中執行。 如需詳細資訊，請參閱[端點資料表](endpoint.md)。 <br/> |
|ConnectivityIce  <br/> |Tinyint  <br/> |媒體路徑（例如直接或中繼）的相關資訊。 如需詳細資訊，請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |針對呼叫者位數標誌中描述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |針對被呼叫者的 bits 標誌中所述的互動式連線建立（ICE）程式的相關資訊。 如需詳細資訊，請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|傳輸  <br/> |int  <br/> |傳輸類型：0是 UDP，1是 TCP。  <br/> |
|CallerIPAddr  <br/> |var （50）  <br/> |來電者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的埠。  <br/> |
|CallerInside  <br/> |稍微  <br/> |指出來電者是否在組織網路內。 1表示呼叫者是在商業網路內，0代表呼叫者在網路以外。  <br/> |
|CalleeIPAddr  <br/> |var （50）  <br/> |被呼叫者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫者使用的埠。  <br/> |
|CalleeInside  <br/> |稍微  <br/> |指出來電者是否在組織網路內。1代表被叫方是在商業網路內，0代表被叫方在網路以外。  <br/> |
|CallerUserSite  <br/> |Nvarchar  <br/> |來電者的網站名稱。  <br/> |
|CallerRegion  <br/> |Nvarchar  <br/> |來電者網站之國家/地區的名稱。  <br/> |
|CalleeUserSite  <br/> |Nvarchar  <br/> |被呼叫者的網站名稱。  <br/> |
|CalleeRegion  <br/> |Nvarchar  <br/> |被呼叫者網站之國家/地區的名稱。  <br/> |
|CallerRelayIPAddr  <br/> |var （50）  <br/> |呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫者使用的 A/V 邊緣服務上的埠。  <br/> |
|CalleeRelayIPAddr  <br/> |var （50）  <br/> |被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。 如需詳細資訊，請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被呼叫者使用的 A/V 邊緣服務上的埠。  <br/> |
|CallerCaptureDev  <br/> |Varchar （256）  <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar （256）  <br/> |來電者的轉譯裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar （256）  <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDevDriver  <br/> |Varchar （256）  <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeCaptureDev  <br/> |Varchar （256）  <br/> |被呼叫者的擷取裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar （256）  <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleCaptureDevDriver  <br/> |Varchar （256）  <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar （256）  <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CallerNetworkConnectionType  <br/> |Tinyint  <br/> |來電者的網路連線類型：0是 [有線]，1是 [無線]。  <br/> |
|CallerVPN  <br/> |稍微  <br/> |指出呼叫者是否已經由虛擬專用網路連接。 1是虛擬私人網路（VPN），0是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |小數（18，）  <br/> |呼叫者端點的網路連結速度，以 bps 表示。  <br/> |
|CalleeNetworkConnectionType  <br/> |Tinyint  <br/> |被呼叫者的網路連線類型：0是 [有線]，1是 [無線]。  <br/> |
|CalleeVPN  <br/> |稍微  <br/> |指出被呼叫者是否已經由虛擬私人網路絡進行連線。 1是虛擬私人網路（VPN），0是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |小數（18，0）  <br/> |被呼叫者的端點的網路連結速度（bps）。  <br/> |
|ConversationalMOS  <br/> |decimal （3，2）  <br/> |Narrowband 音訊會話的會話 MOS （根據兩個音訊資料流程）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |在給定各種原則設定（TURN、API、SDP、原則伺服器等）的情況下，套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆，因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬：傳送資料流程可能會受到頻寬估計所施加的限制。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |從即時控制通訊協定（RTCP）統計資料的平均網路抖動。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話期間網路抖動的最大值。  <br/> |
|環路  <br/> |int  <br/> |從 RTCP 統計資料中往返的時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音訊資料流程的最大往返行程時間。  <br/> |
|PacketLossRate  <br/> |十進位（5，4）  <br/> |通話期間的平均資料包遺失率。  <br/> |
|PacketLossRateMax  <br/> |十進位（5，4）  <br/> |通話期間觀察到的最大資料包遺失。  <br/> |
|PacketUtilization  <br/> |int  <br/> |影片串流的資料包計數（即時傳輸通訊協定、RTP）。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音訊資料流程的頻寬估計值。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用於通話的音訊編解碼器，從[PayloadDescription 資料表](payloaddescription.md)中引用。  <br/> |
|VideoResolution  <br/> |char （9）  <br/> |以圖元為單位的影片解析度，以圖元為單位的寬度乘以圖元高度。 報告為字串。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |影片串流的平均位元速率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |十進位（9，4）  <br/> |收到的視頻畫面播放速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |十進位（9，4）  <br/> |已傳送的視頻畫面播放速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |影片會話期間的最大視頻位元速率。  <br/> |
|VideoPacketLossRate  <br/> |十進位（9，4）  <br/> |視頻資料包遺失的頻率。  <br/> |
|VideoFrameLossRate  <br/> |decimal （9.4）  <br/> |遺失的視頻畫面總百分比。  <br/> |
|VideoFEC  <br/> |稍微  <br/> |不使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |為影片所分配的平均頻寬量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal （9.4）  <br/> |遺失的視頻畫面總百分比。  <br/> |
|SenderIsCallerPAI  <br/> |稍微  <br/> |P 斷言身分識別資訊的資料流程方向。 1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。  <br/> |
   

