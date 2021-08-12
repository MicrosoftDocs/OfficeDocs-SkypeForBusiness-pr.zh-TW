---
title: AudioStreamDetail view
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail View 儲存資料庫中每個音訊資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
ms.openlocfilehash: 88300d4117a26dd033897d955ae82fb99f7d7b4878cb484caf4bae1fad3f965d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309182"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail view
 
AudioStreamDetail View 儲存資料庫中每個音訊資料流程的資訊。 此視圖已引進于 Microsoft Lync Server 2013。
  
|**欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從 [MediaLine 表格](medialine-0.md)中參照。  <br/> |
|StreamId  <br/> |int  <br/> |媒體行中的唯一識別碼。  <br/> |
|StartTime  <br/> |datetime  <br/> |會話的開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |工作階段結束時間。  <br/> |
|DialogCategory  <br/> |位  <br/> |對話方塊類別：0是指轉送伺服器腿的商務用 Skype Server;1是轉送伺服器到 PSTN 閘道腿。  <br/> |
|MediationServerBypassFlag  <br/> |位  <br/> |指示是否略過呼叫的旗標。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果有的話，則表示即使旁路 IDs 相符也不會略過通話的原因。 只定義了一個值：  <br/> 0x0001-預設網路介面卡的未知旁路識別碼。  <br/> |
|CallPriority  <br/> |int  <br/> |通話的優先順序。  <br/> |
|CallerPool  <br/> |Nvarchar (256)   <br/> |發話者集區 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar (256)   <br/> |受話者集區 FQDN。  <br/> |
|Caller  <br/> |Nvarchar (450)   <br/> |來電者的 URI。  <br/> |
|方  <br/> |Nvarchar (450)   <br/> |被呼叫者的 URI。  <br/> |
|CallerUserAgent  <br/> |Nvarchar (256)   <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |來電者使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar (64)   <br/> |來電者使用者代理程式的類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar (256)   <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |被呼叫者之使用者代理程式的類型。 如需詳細資訊，請參閱 [UserAgent 表格](useragent.md) 。 <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar (64)   <br/> |被呼叫者之使用者代理程式的類別。 如需詳細資訊，請參閱 [UserAgentDef 表格 (QoE) ](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |Nvarchar (256)   <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar (256)   <br/> |被呼叫者的端點名稱。  <br/> |
|CallerOS  <br/> |Nvarchar (128)   <br/> |呼叫者端點的作業系統 (OS) 。  <br/> |
|CalleeOS  <br/> |Nvarchar (128)   <br/> |受話者端點的作業系統 (OS) 。  <br/> |
|CallerCPUName  <br/> |Nvarchar (128)   <br/> |來電者端點的 CPU 名稱。  <br/> |
|CalleeCPUName  <br/> |Nvarchar (128)   <br/> |受話者端點的 CPU 名稱。  <br/> |
|CallerCPUNumberOfCores  <br/> |Smallint  <br/> |來電者端點中的 CPU 核心數目。  <br/> |
|CalleeCPUNumberOfCores  <br/> |Smallint  <br/> |受話者端點中的 CPU 核心數目。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |來電者端點的 CPU 處理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |受話者端點的 CPU 處理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |Tinyint  <br/> |會指出來電者的系統是否在虛擬化環境中執行。 如需詳細資訊，請參閱 [端點表格](endpoint.md) 。 <br/> |
|CalleeVirtualizationFlag  <br/> |Tinyint  <br/> |會指出受話者的系統是否正在虛擬環境中執行。 如需詳細資訊，請參閱 [端點表格](endpoint.md) 。 <br/> |
|CorrelationKey  <br/> ||相關機碼。 從 [SessionCorrelation 表格](sessioncorrelation.md)中參照。  <br/> |
|ConnectivityIce  <br/> |Tinyint  <br/> |媒體路徑的相關資訊，例如 direct 或中繼。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |發話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |受話者位元旗標中描述之互動式連線建立 (ICE) 程序的相關資訊。如需詳細資訊，請參閱＜經驗品質監控伺服器通訊協定規格＞。  <br/> |
|傳輸  <br/> |Tinyint  <br/> |傳輸類型：0是 UDP，1是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |來電者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |發話者使用的連接埠。  <br/> |
|CallerInside  <br/> |位  <br/> |會指出來電者是否在間隔網路內：1表示來電者位於商業網路內，0表示來電者位於網路外。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被呼叫者的 IP 位址。 這可以是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |受話者使用的連接埠。  <br/> |
|CalleeInside  <br/> |位  <br/> |會指出受話者是否在間隔網路內：1表示受話者位於商業網路內，0表示受話者位於網路外。  <br/> |
|CallerUserSite  <br/> |Nvarchar (128)   <br/> |來電者網站的名稱。  <br/> |
|CallerRegion  <br/> |Nvarchar (128)   <br/> |來電者網站的國家/地區名稱。  <br/> |
|CalleeUserSite  <br/> |Nvarchar (128)   <br/> |被呼叫者之網站的名稱。  <br/> |
|CalleeRegion  <br/> |Nvarchar (128)   <br/> |被呼叫者網站的國家/地區名稱。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |發話者使用之 A/V Edge Service 的 IP 位址。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |發話者在 A/V Edge Service 上使用的連接埠。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |被呼叫者所使用之 A/V Edge service 的 IP 位址金鑰。 如需詳細資訊，請參閱 [IPAddress 表格](ipaddress.md) 。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |受話者在 A/V Edge Service 上使用的連接埠。  <br/> |
|CallerCaptureDev  <br/> |Varchar (256)   <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar (256)   <br/> |來電者的呈現裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar (256)   <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDriver  <br/> |Varchar (256)   <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeCaptureDev  <br/> |Varchar (256)   <br/> |被呼叫者的捕獲裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleeCaptureDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar (256)   <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CallerNetworkConnectionType  <br/> |Tinyint  <br/> |來電者的網路連線類型：0是有線的，1是無線。  <br/> |
|CallerVPN  <br/> |位  <br/> |會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |十進位 (18，0)   <br/> |呼叫者端點的網路連結速度（bps）。  <br/> |
|CalleeNetworkConnectionType  <br/> |Tinyint  <br/> |被呼叫者的網路連線類型：0是有線的，1是無線。  <br/> |
|CalleeVPN  <br/> |位  <br/> |會指出呼叫者是否是透過虛擬私人網路絡（1是虛擬私人網路） (VPN) ，0是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |十進位 (18，0)   <br/> |被呼叫者端點的網路連結速度（bps）。  <br/> |
|ConversationalMOS  <br/> |十進位 (3，2)   <br/> |音訊工作階段的窄頻交談方式 MOS (兩種音訊資料流皆為依據)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |針對指定之傳送端資料流程套用至指定之傳送端資料流程的實際頻寬，可 (轉換、API、SDP、原則伺服器等等) 。 這並不會混淆有效的頻寬，因為頻寬估算可能會有較低的有效頻寬。 這基本上是傳送資料流程可以採用限制頻寬估計所強加限制的最大頻寬  <br/> |
|JitterInterArrival  <br/> |int  <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話期間的最大網路抖動。  <br/> |
|PacketLossRate  <br/> |十進位 (5，4)   <br/> |通話期間的平均封包遺失率。  <br/> |
|PacketLossRateMax  <br/> |十進位 (5，4)   <br/> |通話期間觀察到的封包遺失上限。  <br/> |
|BurstDensity  <br/> |十進位 (9，4)   <br/> |通話期間的猝量遺失期間的封包遺失平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |通話期間的猝量遺失期間的封包遺失平均持續時間。  <br/> |
|BurstGapDensity  <br/> |十進位 (9，4)   <br/> |封包遺失失敗之間的平均封包遺失密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |封包遺失的平均持續時間。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音訊資料流程的封包計數。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音訊資料流程的頻寬估計值。  <br/> |
|DegradationAvg  <br/> |十進位 (3，2)   <br/> |整個通話的網路 MOS 降低。 範圍是0.0 到5.0。 此度量顯示由於抖動和封包遺失，網路 MOS 減少的數量。 可接受的品質應小於0.5。  <br/> |
|DegradationMax  <br/> |十進位 (3，2)   <br/> |通話期間的最大網路 MOS 降級。  <br/> |
|DegradationJitterAvg  <br/> |十進位 (3，2)   <br/> |抖動導致的網路 MOS 降低。  <br/> |
|DegradationPacketLossAvg  <br/> |十進位 (3，2)   <br/> |封包遺失導致的網路 MOS 降低。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用於通話的音訊編解碼器，從 [PayloadDescription 表格](payloaddescription.md)中參照。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音訊資料流程的取樣速率。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |來電者所傳送之音訊的後續類比增益控制音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |來電者接收之音訊的音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |來電者所傳送之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |來電者接收之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |呼叫來電者的回顯回復功能增強功能。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |呼叫者的喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |來電者的擴音器 capture 每五分鐘的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|CallerTimestampDriftRateMic  <br/> |十進位 (9，2)   <br/> |來電者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |十進位 (9，2)   <br/> |來電者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|CallerTimestampErrorMicMs  <br/> |十進位 (9，2)   <br/> |通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |十進位 (9，2)   <br/> |呼叫者的最後20秒內，平均來電者的發言人轉譯資料流程時間戳記錯誤（毫秒）。  <br/> |
|CallerVsEntryCauses  <br/> |Smallint  <br/> |語音開關是一種具有低中斷能力的半雙工模式。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CallerEchoEventCauses  <br/> |Tinyint  <br/> |來電者的 echo 事件原因。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CallerEchoPercentMicIn  <br/> |十進位 (5，2)   <br/> |在來電者的麥克風捕獲資料流程中偵測到迴響的時間百分比。 如果使用的是耳機，則值應該很低。  <br/> |
|CallerEchoPercentSend  <br/> |十進位 (5，2)   <br/> |在來電者的傳送資料流程中偵測到迴響的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |從來電者音訊的閘道，在轉送伺服器上接收信號等級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為-30 到-18 dBoV。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |從來電者的音訊的閘道處接收轉送伺服器上的信號等級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |在套用至來電者音訊的轉送伺服器端 (AGC) 自動取得控制權。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |對來電者傳入的信號的根平均方 (RMS) ，最多可達前30秒的呼叫。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |代表被呼叫者所傳送之音訊的後續類比增益控制音訊信號等級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |被呼叫者所接收之音訊的音訊信號層級。 此度量單位的單位是 dBmo。 若要取得可接受的品質，至少要有 30 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |受話者所傳送之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |受話者接收之音訊的後續類比增益控制音訊雜訊層級。 此度量單位的單位是 dBmo。 針對可接受的品質，它應小於 35 dBmo。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |被呼叫者的回顯傳回遺失增強功能。 此度量單位的單位為 dB。 較低的值表示較少的回聲。 A/V 的會議服務器或 IP 電話不會報告此度量。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |被呼叫者的喇叭轉譯每五分鐘的平均故障。 為了獲得良好的品質，應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |受話者麥克風捕獲每五分鐘的平均故障。 若為良好的品質，這應小於每五分鐘一次。 不會 A/V 會議伺服器、轉送伺服器或 IP 電話上報告。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |十進位 (9，2)   <br/> |受話者的麥克風裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |十進位 (9，2)   <br/> |受話者的揚聲器裝置時鐘相對於 CPU 時鐘的相對頻率。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |十進位 (9，2)   <br/> |通話的最後20秒內的平均麥克風捕獲資料流程時間戳記錯誤（毫秒）。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |十進位 (9，2)   <br/> |通話的最後20秒內，被呼叫者的發言人轉譯資料流程時間戳記錯誤（毫秒）。  <br/> |
|CalleeVsEntryCauses  <br/> |Smallint  <br/> |語音開關是一種具有低中斷能力的半雙工模式。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CalleeEchoEventCauses  <br/> |Tinyint  <br/> |被呼叫者的 echo 事件原因。 如需詳細資訊，請參閱 [MediaLine 表格](medialine-0.md) 。 <br/> |
|CalleeEchoPercentMicIn  <br/> |十進位 (5，2)   <br/> |被呼叫者的麥克風捕獲資料流程中偵測到迴響的時間百分比。 如果使用的是耳機，則值應該很低。  <br/> |
|CalleeEchoPercentSend  <br/> |十進位 (5，2)   <br/> |在被呼叫者的已傳送資料流程中偵測到迴響的時間百分比。 傳送資料流程中的高回音百分比會傳回回聲洩漏。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |從受話者的音訊的閘道從轉送伺服器接收信號層級;這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應為 [-30 到-18] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |從所呼叫者音訊的閘道，在轉送伺服器上收到的信號等級。 這只適用于轉送伺服器。 此度量單位為 dBoV。 為了獲得良好的品質，可接受的範圍應小於-50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |在套用至受話者音訊的轉送伺服器端 (AGC) 自動取得控制權。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |從來電者傳入的信號的根平均平方 (RMS) ，最多可達前30秒的呼叫。  <br/> |
|RatioConcealedSamplesAvg  <br/> |十進位 (5，2)   <br/> |音訊修復所產生之隱藏樣本與一般範例的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |十進位 (5，2)   <br/> |音訊修復所產生之延伸樣本的平均比率為典型範例。  <br/> |
|RatioCompressedSamplesAvg  <br/> |十進位 (5，2)   <br/> |音訊修復所產生之壓縮樣本與一般範例的平均比率。  <br/> |
|往返  <br/> |int  <br/> |從 RTCP 統計資料來回的時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音訊資料流程的最大來回時間。  <br/> |
|OverallAvgNetworkMOS  <br/> |十進位 (3，2)   <br/> |通話的平均寬頻網路 MOS。 此度量取決於所用的封包遺失、抖動和編解碼器。 範圍是1.0 到5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |十進位 (3，2)   <br/> |通話的最小寬頻網路 MOS。  <br/> |
|SendListenMOS  <br/> |十進位 (3，2)   <br/> |已傳送之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級和捕獲裝置特性。  <br/> |
|SendListenMOSMin  <br/> |十進位 (3，2)   <br/> |通話的最小 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |十進位 (3，2)   <br/> |從網路接收之音訊的平均預測寬頻傾聽 MOS 分數，包括語音層級、雜訊層級、編解碼器、網路狀況和捕獲裝置特性。  <br/> |
|RecvListenMOSMin  <br/> |十進位 (3，2)   <br/> |通話的最小 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |位  <br/> |會指出是否使用音訊 FEC 進行通話。  <br/> |
|SenderIsCallerPAI  <br/> |位  <br/> |表示 p 宣稱識別資訊的方向;1表示資料流程是從來電者流向被呼叫者;0表示資料流程方向從被叫方傳送給來電者。  <br/> |
   

