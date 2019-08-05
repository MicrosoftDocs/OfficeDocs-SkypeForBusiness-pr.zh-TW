---
title: AudioStreamDetail 視圖
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: '[AudioStreamDetail] 視圖會儲存資料庫中每個音訊資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。'
ms.openlocfilehash: 16f97fc367b171ceb0ddc5b5c0024bd88c7b5268
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192687"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 視圖
 
[AudioStreamDetail] 視圖會儲存資料庫中每個音訊資料流程的相關資訊。 此視圖已在 Microsoft Lync Server 2013 中推出。
  
|**左欄**|**資料類型**|**詳細資料**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|SessionSeq  <br/> |int  <br/> |從[MediaLine 資料表](medialine-0.md)中參照。  <br/> |
|StreamId  <br/> |int  <br/> |媒體線中的唯一識別碼。  <br/> |
|開始  <br/> |datetime  <br/> |會話的開始時間。  <br/> |
|EndTime  <br/> |datetime  <br/> |會話的結束時間。  <br/> |
|DialogCategory  <br/> |稍微  <br/> |對話方塊類別: 0 是商務用 Skype 伺服器以轉送伺服器腿;1是通向 PSTN 閘道腿的中繼伺服器。  <br/> |
|MediationServerBypassFlag  <br/> |稍微  <br/> |該旗標指出通話是否被略過。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果有的話, 則指示即使繞過旁路 Id, 也不會避開通話。 只定義一個值:  <br/> 0x0001-預設網路介面卡的旁路 ID 為未知。  <br/> |
|CallPriority  <br/> |int  <br/> |通話的優先順序。  <br/> |
|CallerPool  <br/> |Nvarchar (256)  <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |Nvarchar (256)  <br/> |被呼叫方池 FQDN。  <br/> |
|呼叫  <br/> |Nvarchar (450)  <br/> |來電者的 URI。  <br/> |
|方  <br/> |Nvarchar (450)  <br/> |被呼叫者的 URI。  <br/> |
|CallerUserAgent  <br/> |Nvarchar (256)  <br/> |來電者的使用者代理程式字串。  <br/> |
|CallerUserAgentType  <br/> |Smallint  <br/> |來電者的使用者代理程式類型。 如需詳細資訊, 請參閱[UserAgent 資料表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |Nvarchar (64)  <br/> |呼叫者使用者代理程式的類別。 如需詳細資訊, 請參閱[UserAgentDef 資料表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |Nvarchar (256)  <br/> |被呼叫者的使用者代理程式字串。  <br/> |
|CalleeUserAgentType  <br/> |Smallint  <br/> |被呼叫者的使用者代理程式類型。 請參閱[UserAgent 資料表](useragent.md)以取得相關資訊。 <br/> |
|CalleeUserAgentCategory  <br/> |Nvarchar (64)  <br/> |被呼叫者的使用者代理程式類別。 如需資訊, 請參閱[UserAgentDef 資料表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |Nvarchar (256)  <br/> |來電者的端點名稱。  <br/> |
|CalleeEndpoint  <br/> |Nvarchar (256)  <br/> |被呼叫者的端點名稱。  <br/> |
|CallerOS  <br/> |Nvarchar  <br/> |呼叫者終點的作業系統 (OS)。  <br/> |
|CalleeOS  <br/> |Nvarchar  <br/> |被呼叫者的端點的作業系統 (OS)。  <br/> |
|CallerCPUName  <br/> |Nvarchar  <br/> |呼叫者終點的 CPU 名稱。  <br/> |
|CalleeCPUName  <br/> |Nvarchar  <br/> |被呼叫者的端點的 CPU 名稱。  <br/> |
|CallerCPUNumberOfCores  <br/> |Smallint  <br/> |呼叫者終點中的 CPU 核心數。  <br/> |
|CalleeCPUNumberOfCores  <br/> |Smallint  <br/> |被呼叫者的端點中的 CPU 核心數。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者終點的 CPU 處理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被呼叫者的端點的 CPU 處理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |Tinyint  <br/> |指出呼叫者的系統在虛擬化環境中是否正在執行。 如需詳細資訊, 請參閱[端點資料表](endpoint.md)。 <br/> |
|CalleeVirtualizationFlag  <br/> |Tinyint  <br/> |指出被呼叫者的系統是否正在虛擬化環境中執行。 如需詳細資訊, 請參閱[端點資料表](endpoint.md)。 <br/> |
|CorrelationKey  <br/> ||[關聯金鑰]。 從[SessionCorrelation 資料表](sessioncorrelation.md)中參照。  <br/> |
|ConnectivityIce  <br/> |Tinyint  <br/> |媒體路徑 (例如直接或中繼) 的相關資訊。 如需詳細資訊, 請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |針對呼叫者位數標誌中描述的互動式連線建立 (ICE) 程式的相關資訊。 如需詳細資訊, 請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |針對被呼叫者的 bits 標誌中所述的互動式連線建立 (ICE) 程式的相關資訊。 如需詳細資訊, 請參閱體驗品質監視伺服器通訊協定的規格。  <br/> |
|傳輸  <br/> |Tinyint  <br/> |傳輸類型: 0 是 UDP, 1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |來電者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的埠。  <br/> |
|CallerInside  <br/> |稍微  <br/> |指出來電者是否在間隔網路內: 1 表示呼叫者是在商業網路內, 0 代表來電者在網路以外。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |被呼叫者的 IP 位址。 這可能是 IPv4 或 IPv6 位址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫者使用的埠。  <br/> |
|CalleeInside  <br/> |稍微  <br/> |指出被呼叫者是否在間隔網路內: 1 代表被呼叫者是在商業網路內, 0 代表被呼叫者在網路以外。  <br/> |
|CallerUserSite  <br/> |Nvarchar  <br/> |來電者的網站名稱。  <br/> |
|CallerRegion  <br/> |Nvarchar  <br/> |來電者網站之國家/地區的名稱。  <br/> |
|CalleeUserSite  <br/> |Nvarchar  <br/> |被呼叫者的網站名稱。  <br/> |
|CalleeRegion  <br/> |Nvarchar  <br/> |被呼叫者網站之國家/地區的名稱。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |呼叫者所使用之 A/V 邊緣服務的 IP 位址。 如需詳細資訊, 請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫者使用的 A/V 邊緣服務上使用的埠。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |被呼叫者所使用之 A/V 邊緣服務的 IP 位址金鑰。 如需詳細資訊, 請參閱 [ [IPAddress] 資料表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |在被呼叫者所使用的 A/V 邊緣服務上使用的埠。  <br/> |
|CallerCaptureDev  <br/> |Varchar (256)  <br/> |來電者的擷取裝置名稱。  <br/> |
|CallerRenderDev  <br/> |Varchar (256)  <br/> |來電者的轉譯裝置名稱。  <br/> |
|CallerCaptureDevDriver  <br/> |Varchar (256)  <br/> |來電者的捕獲裝置驅動程式名稱。  <br/> |
|CallerRenderDriver  <br/> |Varchar (256)  <br/> |來電者的轉譯裝置驅動程式名稱。  <br/> |
|CalleeCaptureDev  <br/> |Varchar (256)  <br/> |被呼叫者的擷取裝置名稱。  <br/> |
|CalleeRenderDev  <br/> |Varchar (256)  <br/> |被呼叫者的轉譯裝置名稱。  <br/> |
|CalleeCaptureDevDriver  <br/> |Varchar (256)  <br/> |被呼叫者的捕獲裝置驅動程式名稱。  <br/> |
|CalleeRenderDevDriver  <br/> |Varchar (256)  <br/> |被呼叫者的轉譯裝置驅動程式名稱。  <br/> |
|CallerNetworkConnectionType  <br/> |Tinyint  <br/> |來電者的網路連線類型: 0 是 [有線], 1 是 [無線]。  <br/> |
|CallerVPN  <br/> |稍微  <br/> |指出呼叫者是否已經由虛擬專用網路連接: 1 是虛擬私人網路 (VPN), 0 是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |小數 (18, 0)  <br/> |呼叫者端點的網路連結速度, 以 bps 表示。  <br/> |
|CalleeNetworkConnectionType  <br/> |Tinyint  <br/> |被呼叫者的網路連線類型: 0 是 [有線], 1 是 [無線]。  <br/> |
|CalleeVPN  <br/> |稍微  <br/> |指出呼叫者是否已經由虛擬專用網路連接: 1 是虛擬私人網路 (VPN), 0 是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |小數 (18, 0)  <br/> |被呼叫者的端點的網路連結速度, 以 bps 表示。  <br/> |
|ConversationalMOS  <br/> |decimal (3, 2)  <br/> |Narrowband 音訊會話的會話 MOS (根據兩個音訊資料流程)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |在給定各種原則設定 (TURN、API、SDP、原則伺服器等) 的情況下, 套用到指定傳送端資料流程的實際頻寬。 這不會與有效的頻寬混淆, 因為頻寬估計可能會有較低的效率。 這實際上是最大頻寬: 傳送資料流程可能會受到頻寬估計所強加的限制  <br/> |
|JitterInterArrival  <br/> |int  <br/> |從即時控制通訊協定 (RTCP) 統計資料的平均網路抖動。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通話期間網路抖動的最大值。  <br/> |
|PacketLossRate  <br/> |十進位 (5, 4)  <br/> |通話期間的平均資料包遺失率。  <br/> |
|PacketLossRateMax  <br/> |十進位 (5, 4)  <br/> |通話期間觀察到的最大資料包遺失。  <br/> |
|BurstDensity  <br/> |十進位 (9, 4)  <br/> |通話期間猝發損失期間的平均資料包遺失密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |通話期間猝發損失期間的平均資料包遺失時間。  <br/> |
|BurstGapDensity  <br/> |十進位 (9, 4)  <br/> |在突發資料包遺失之間的間隔期間的平均資料包遺失密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |猝發資料包遺失之間的平均持續時間。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音訊資料流程的 [資料包計數]。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音訊資料流程的頻寬估計值。  <br/> |
|DegradationAvg  <br/> |decimal (3, 2)  <br/> |整個通話的網路 MOS 下降。 範圍是0.0 到5.0。 這個指標顯示由於抖動和資料包遺失而減少網路 MOS 的數量。 針對可接受的品質, 它應該小於0.5。  <br/> |
|DegradationMax  <br/> |decimal (3, 2)  <br/> |通話期間網路 MOS 的最大下降。  <br/> |
|DegradationJitterAvg  <br/> |decimal (3, 2)  <br/> |抖動造成的網路 MOS 下降。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal (3, 2)  <br/> |因數據包遺失而造成的網路 MOS 下降。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用於通話的音訊編解碼器, 從[PayloadDescription 資料表](payloaddescription.md)中引用。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音訊資料流程的採樣速率。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |撥號後的類比增益控制呼叫者傳送之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質, 至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |來電者收到之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質, 至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |撥號後的類比增益控制來電者傳送之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質, 它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |撥號後的類比增益控制來電者收到之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質, 它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |來電者的迴響回報損失增強功能。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |呼叫者的喇叭前轉譯每五分鐘的平均問題。 若要獲得較高的品質, 此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |呼叫者麥克風捕獲每五分鐘的平均問題。 若要獲得良好的品質, 這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal (9, 2)  <br/> |本機號碼相對於 CPU 時鐘的麥克風裝置時鐘偏移速度。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal (9, 2)  <br/> |來電者與 CPU 時鐘相關的喇叭裝置時鐘偏移率。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal (9, 2)  <br/> |在呼叫的最後20秒內, 麥克風捕獲串流的時間戳記錯誤 (以毫秒為單位)。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal (9, 2)  <br/> |呼叫者最近20秒內, 來電者的喇叭轉譯資料流程時間戳記錯誤的平均值。  <br/> |
|CallerVsEntryCauses  <br/> |Smallint  <br/> |Voice 開關是一種半雙工模式, 可減少中斷能力。 如需詳細資訊, 請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CallerEchoEventCauses  <br/> |Tinyint  <br/> |呼叫者回顯事件的原因。 如需詳細資訊, 請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal (5, 2)  <br/> |在呼叫者麥克風捕獲串流中檢測到迴響的時間百分比。 如果使用耳機, 該值應該較低。  <br/> |
|CallerEchoPercentSend  <br/> |decimal (5, 2)  <br/> |在來電者的傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該是-30 到-18 的 dBoV。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |從呼叫者音訊的閘道在中繼伺服器上接收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該小於-50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |將中繼伺服器端的自動增益控制 (AGC) 套用至呼叫者的音訊。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |浮  <br/> |呼叫的撥入信號的根平均數 (RMS), 最多為來電者的前30秒。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |代表被呼叫者傳送之音訊的類比後增益控制音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質, 至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |被呼叫者接收之音訊的音訊信號等級。 這個指標的單位是 dBmo。 若要取得可接受的品質, 至少要有 30 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |防類比增益控制被呼叫者傳送之音訊的音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質, 它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |已被呼叫者接收之音訊的反類比增益控制音訊雜訊層級。 這個指標的單位是 dBmo。 針對可接受的品質, 它應該小於 35 dBmo。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |被呼叫者的迴響傳回損失增強功能。 這個指標的單位是 dB。 較低的值代表較少的回音。 A/V 會議伺服器或 IP 電話不會報告此統計值。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |被呼叫者的喇叭前轉譯每五分鐘的平均故障。 若要獲得較高的品質, 此頻率應該小於每五分鐘。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |被呼叫者麥克風捕獲每五分鐘的平均問題。 若要獲得良好的品質, 這應該少於每五分鐘一次。 無法由 A/V 會議伺服器、中繼伺服器或 IP 電話來報告。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal (9, 2)  <br/> |被呼叫者的麥克風裝置時鐘偏移率, 相對於 CPU 時鐘。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal (9, 2)  <br/> |被呼叫者的喇叭裝置時鐘偏移率, 相對於 CPU 時鐘。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal (9, 2)  <br/> |在呼叫的最後20秒內, 麥克風捕獲串流的時間戳記錯誤 (以毫秒為單位)。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal (9, 2)  <br/> |呼叫者最近20秒內, 被呼叫者的喇叭轉譯資料流程時間戳記錯誤的平均值。  <br/> |
|CalleeVsEntryCauses  <br/> |Smallint  <br/> |Voice 開關是一種半雙工模式, 可減少中斷能力。 如需詳細資訊, 請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CalleeEchoEventCauses  <br/> |Tinyint  <br/> |被呼叫者的 echo 事件原因。 如需詳細資訊, 請參閱[MediaLine 資料表](medialine-0.md)。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal (5, 2)  <br/> |在被呼叫者的麥克風捕獲資料流程中檢測到迴響的時間百分比。 如果使用耳機, 該值應該較低。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal (5, 2)  <br/> |在被呼叫者的傳送資料流程中檢測到迴響的時間百分比。 傳送資料流程中的高迴響百分比表示回應洩漏。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |從被呼叫者音訊的閘道在中繼伺服器上接收到的信號等級;這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該是 [-30 至-18] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |從被呼叫者音訊的閘道, 在中繼伺服器上接收到的信號等級。 這只適用于中繼伺服器。 這個度量單位是 dBoV。 若要獲得良好的品質, 可接受的範圍應該小於-50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |將中繼伺服器端的自動增益控制 (AGC) 套用到被呼叫者的音訊。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |浮  <br/> |呼叫的撥入信號的根平均數 (RMS), 最多為撥打電話的前30秒。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal (5, 2)  <br/> |從音訊康復產生的隱藏樣本到典型範例的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal (5, 2)  <br/> |從音訊康復產生的延伸樣本數與典型範例的平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal (5, 2)  <br/> |從音訊修復到典型範例所產生之壓縮樣本的平均比率。  <br/> |
|環路  <br/> |int  <br/> |從 RTCP 統計資料中往返的時間。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音訊資料流程的最大往返行程時間。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal (3, 2)  <br/> |通話的平均 wideband 網路 MOS。 這個指標取決於所使用的資料包遺失、抖動和編解碼器。 範圍是1.0 到5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal (3, 2)  <br/> |通話的最小 wideband 網路 MOS。  <br/> |
|SendListenMOS  <br/> |decimal (3, 2)  <br/> |已傳送音訊的平均預計 wideband, 包括語音等級、雜訊等級及捕捉裝置特徵。  <br/> |
|SendListenMOSMin  <br/> |decimal (3, 2)  <br/> |通話的最小 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |decimal (3, 2)  <br/> |平均預計 wideband 從網路接收之音訊的 MOS 分數, 包括語音電平、雜訊層級、編解碼器、網路條件及捕獲裝置特徵。  <br/> |
|RecvListenMOSMin  <br/> |decimal (3, 2)  <br/> |通話的最小 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |稍微  <br/> |指出是否已使用音訊 FEC 進行通話。  <br/> |
|SenderIsCallerPAI  <br/> |稍微  <br/> |表示 p 斷言識別資訊的方向。1表示資料流程方向從來電者到被叫方;0表示資料流程方向是從被叫方到來電者。  <br/> |
   

