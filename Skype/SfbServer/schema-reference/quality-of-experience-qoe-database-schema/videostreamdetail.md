---
title: VideoStreamDetail view
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail View 儲存資料庫中每個影片資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 0e34791bd3081497c4c8501dbd01d2e9d39503f1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393535"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail view
 
VideoStreamDetail View 儲存資料庫中每個影片資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**描述**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|MediaLineLabel  <br/> |Tinyint  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|StreamId  <br/> |int  <br/> |媒體行中的唯一識別碼。  <br/> |
|StartTime  <br/> |datetime  <br/> |會話的開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |工作階段結束時間。  <br/> |
|CallPriority  <br/> |int  <br/> |通話的優先順序。  <br/> |
|CallerPool  <br/> |Nvarchar (256)   <br/> |發話者集區 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar (256)   <br/> |受話者集區 FQDN。  <br/> |
|Caller  <br/> |Nvarchar (450)   <br/> |來電者的 URI。  <br/> |
|方  <br/> |Nvarchar (450)   <br/> |被呼叫者的 URI。  <br/> |
|CallerUserAgent  <br/> |Nvarchar (256)   <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |來電者使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar (64)   <br/> |呼叫者的使用者代理類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar (256)   <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |被呼叫者之使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar (64)   <br/> |被呼叫者之使用者代理程式的類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |Nvarchar (256)   <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar (256)   <br/> |被呼叫者的端點名稱。  <br/> |
|CallerOS  <br/> |Nvarchar (128)   <br/> |呼叫者端點的作業系統 (OS) 。  <br/> |
|CalleeOS  <br/> |Nvarchar (128)   <br/> |受話者端點的作業系統 (OS) 。  <br/> |
|CallerCPUName  <br/> |Nvarchar (128)   <br/> |來電者端點的 CPU 名稱。  <br/> |
|CalleeCPUName  <br/> |Nvarchar (128)   <br/> |受話者端點的 CPU 名稱。  <br/> |
|CallerCPUNumberOfCores  <br/> |Smallint  <br/> |來電者端點的 CPU 核心數目。  <br/> |
|CalleeCPUNumberOfCores  <br/> |Smallint  <br/> |受話者端點的 CPU 核心數目。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |來電者端點的 CPU 處理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |受話者端點的 CPU 處理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |Tinyint  <br/> |會指出來電者的系統是否在虛擬化環境中執行。 如需詳細資訊，請參閱 [端點表格](endpoint.md) 。 <br/> |
|CalleeVirtualizationFlag  <br/> |Tinyint  <br/> |會指出受話者的系統是否正在虛擬環境中執行。 如需詳細資訊，請參閱 [端點表格](endpoint.md) 。 <br/> |
|ConnectivityIce  <br/> |Tinyint  <br/> |媒體路徑的相關資訊，例如 direct 或中繼。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|傳輸  <br/> |int  <br/> |傳輸類型：0是 UDP，1是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |發話者使用的連接埠。  <br/> |
|CallerInside  <br/> |位  <br/> |會指出來電者是否在組織網路內。 1表示來電者位於商業網路內，0表示來電者位於網路外。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |受話者使用的連接埠。  <br/> |
|CalleeInside  <br/> |位  <br/> |會指出來電者是否在組織網路內。1表示受話者位於商業網路內，0表示受話者位於網路外。  <br/> |
|CallerUserSite  <br/> |Nvarchar (128)   <br/> |來電者網站的名稱。  <br/> |
|CallerRegion  <br/> |Nvarchar (128)   <br/> |來電者網站的國家/地區名稱。  <br/> |
|CalleeUserSite  <br/> |Nvarchar (128)   <br/> |被呼叫者之網站的名稱。  <br/> |
|CalleeRegion  <br/> |Nvarchar (128)   <br/> |被呼叫者網站的國家/地區名稱。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫者所使用 A/V Edge service 上的埠。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被呼叫者所使用 A/V Edge service 上的埠。  <br/> |
|CallerCaptureDev  <br/> |Varchar (256)   <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar (256)   <br/> |來電者的呈現裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar (256)   <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDevDriver  <br/> |Varchar (256)   <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeCaptureDev  <br/> |Varchar (256)   <br/> |被呼叫者的捕獲裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleCaptureDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CallerNetworkConnectionType  <br/> |Tinyint  <br/> |來電者的網路連線類型：0是有線的，1是無線。  <br/> |
|CallerVPN  <br/> |位  <br/> |會指出呼叫者是否透過虛擬專用網路連接。 1 是虛擬私人網路 (VPN)，0 是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |十進位 (18，)   <br/> |呼叫者端點的網路連結速度（bps）。  <br/> |
|CalleeNetworkConnectionType  <br/> |Tinyint  <br/> |被呼叫者的網路連線類型：0是有線的，1是無線。  <br/> |
|CalleeVPN  <br/> |位  <br/> |會指出是否已透過虛擬專用網路連接被呼叫者。 1 是虛擬私人網路 (VPN)，0 是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |十進位 (18，0)   <br/> |受話者端點的網路連結速度 (以 bps) 為單位）。  <br/> |
|ConversationalMOS  <br/> |十進位 (3，2)   <br/> |音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 基本上，除了頻寬預估值規定的限制以外，這是傳送端資料流所能取得的最大頻寬。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話期間的最大網路抖動。  <br/> |
|往返  <br/> |int  <br/> |從 RTCP 統計資料來回的時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音訊資料流程的最大來回時間。  <br/> |
|PacketLossRate  <br/> |十進位 (5，4)   <br/> |通話期間的平均封包遺失率。  <br/> |
|PacketLossRateMax  <br/> |十進位 (5，4)   <br/> |通話期間觀察到的封包遺失上限。  <br/> |
|PacketUtilization  <br/> |int  <br/> |影片的封包計數 (即時傳輸通訊協定，RTP) 。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音訊資料流程的頻寬估計值。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用於通話的音訊編解碼器，從 [PayloadDescription 表格](payloaddescription.md)中參照。  <br/> |
|VideoResolution  <br/> |char (9)   <br/> |影片解析度（圖元寬度乘以圖元高度）。 報告為字串。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |視頻資料流程的平均位元速率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |十進位 (9，4)   <br/> |收到的影片的畫面速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |十進位 (9，4)   <br/> |傳送影片的畫面速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |影片中的最大視頻位元速率。  <br/> |
|VideoPacketLossRate  <br/> |十進位 (9，4)   <br/> |視頻封包遺失的速率。  <br/> |
|VideoFrameLossRate  <br/> |十進位 (9.4)   <br/> |丟失之總影片框的百分比。  <br/> |
|VideoFEC  <br/> |位  <br/> |不會使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |為影片所分配的平均頻寬量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |十進位 (9.4)   <br/> |已遺失之總影片框的百分比。  <br/> |
|SenderIsCallerPAI  <br/> |位  <br/> |P-宣稱身分識別資訊的資料流程方向。 1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。  <br/> |
   

