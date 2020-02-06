---
title: QoE 表格清單
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 資料庫架構由下清單格組成。
ms.openlocfilehash: 6c82585195befda13ebb14215e72a59341fac1d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809001"
---
# <a name="list-of-qoe-tables"></a>QoE 表格清單
 
資料庫架構由下清單格組成。 
  
**支援表格**

|**表格**|**說明**|
|:-----|:-----|
|[AppSharingMetricsThreshold 資料表](appsharingmetricsthreshold.md) <br/> |針對應用程式共用所使用的體驗品質指標，儲存最佳和可接受的值。  <br/> |
|[CodecDescription 資料表](codecdescription.md) <br/> |將唯一的編解碼器識別碼對應至其對應的編解碼器。  <br/> |
|[[IPAddress] 表格](ipaddress.md) <br/> |將 IP 位址對應至在體驗資料庫品質的其他地方所使用的唯一 IP 位址識別碼。  <br/> |
|[NetworkConnectionDetail 資料表](networkconnectiondetail.md) <br/> |將網路連線類型對應至在體驗資料庫的 [品質] 資料庫中其他位置使用的網路連接識別碼。  <br/> |
|[PurgeSettings table （QoE）](purgesettings-qoe.md) <br/> |儲存資訊，指定是否要從 QoE 資料庫自動刪除過時的體驗記錄品質。  <br/> |
|[TraceRoute 資料表](traceroute.md) <br/> |儲存通話的傳送資訊。  <br/> |
|[UserAgentDef table （QoE）](useragentdef-qoe.md) <br/> |將使用者代理程式識別碼對應至代理程式的描述性名稱。  <br/> |
|[VideoMetricsThreshold 資料表](videometricsthreshold.md) <br/> |針對與視頻通話搭配使用的經驗統計，儲存最佳和可接受的值。  <br/> |
|[UserAgent 表格](useragent.md) <br/> |儲存會話初始通訊協定（SIP）使用者代理程式（UA）字串以及在音訊與視頻會話中使用的 UA 類型。  <br/> |
|[User 表格](user-0.md) <br/> |儲存在音訊和視頻會話中使用的使用者、會議和電話 Uri。  <br/> |
|[Endpoint 表格](endpoint.md) <br/> |儲存參與音訊與視頻會話之端點的 FQDN 電腦名稱稱。  <br/> |
|[Pool 表格](pool.md) <br/> |儲存指標資料所屬的 pool 的名稱。  <br/> |
|[Device 表格](device.md) <br/> |儲存在音訊/視頻通話中使用的捕獲裝置和轉譯裝置。  <br/> |
|[DeviceDriver 表格](devicedriver.md) <br/> |儲存在音訊/視頻通話中使用的捕獲裝置和轉譯裝置的驅動程式。  <br/> |
|[Conference 表格](conference.md) <br/> |針對其他案例，儲存會議案例或 DialogID 的會議 Uri。  <br/> |
|[SessionCorrelation 表格](sessioncorrelation.md) <br/> |儲存 PSTN 通話的 CorrelationID。  <br/> |
|[PayloadDescription 表格](payloaddescription.md) <br/> |儲存音訊/視頻通話中所用的編解碼器。  <br/> |
|[AppliedBandwidthSource 表格](appliedbandwidthsource.md) <br/> |儲存音訊/視頻通話中使用的頻寬來源。  <br/> |
|[MacAddress 表格](macaddress.md) <br/> |儲存參與音訊與視頻會話的端點的 MAC 位址。  <br/> |
|[Dialog 表格](dialog.md) <br/> |儲存音訊與視頻會話的對話方塊識別碼。  <br/> |
|[地區表格](region.md) <br/> |儲存在 NCS 設定中定義的網路區域。  <br/> |
|[UserSite 表格](usersite.md) <br/> |儲存在 NCS 設定中定義的網路網站。  <br/> |
|[Subnet 表格](subnet.md) <br/> |儲存在 NCS 設定中定義的子網。  <br/> |
|[MonitoredRegionLink 表格](monitoredregionlink.md) <br/> |儲存在 NCS 設定中定義的區域連結。  <br/> |
|[MonitoredUserSiteLink 表格](monitoredusersitelink.md) <br/> |儲存在 NCS 設定中定義的網路網站連結。  <br/> |
|[EndpointSubnet 表格](endpointsubnet.md) <br/> |儲存參與音訊與視頻會話的端點子網。  <br/> |
|[Server 表格](server.md) <br/> |儲存介質所經過的伺服器 FQDN 或 IP 位址。  <br/> |
   
**指標資料表格**

|**表格**|**說明**|
|:-----|:-----|
|[AppSharingStream 資料表](appsharingstream.md) <br/> |儲存用於應用程式共用之網路資料流程的體驗品質統計資料。 用於應用程式共用之網路資料流程的體驗品質統計資料。  <br/> |
|[Session 表格](session.md) <br/> |儲存音訊或音訊/視頻會話的整體資訊。 會話是在兩個端點之間定義為音訊或視頻 SIP 對話方塊。  <br/> |
|[MediaLine 表格](medialine-0.md) <br/> |儲存會話中每個媒體線的相關資訊。 媒體線是一個或多個音訊與視頻資料流程的集合。 通常，單一媒體線會有兩個數據流，也就是音訊或視頻。  <br/> |
|[AudioStream 表格](audiostream.md) <br/> |針對媒體行中的每個音訊資料流程儲存音訊媒體質量度量單位。  <br/> |
|[AudioSignal 表格](audiosignal.md) <br/> |在媒體行中儲存音訊媒體質量度量單位。 這包括聲音回聲取消（AEC）和自動增益控制（AGC）度量單位。  <br/> |
|[VideoStream 表格](videostream.md) <br/> |針對媒體線中的每個音訊資料流程儲存視頻媒體質量度量單位。  <br/> |
|[AudioClientEvent 表格](audioclientevent.md) <br/> |儲存從用戶端事件收集的音訊媒體質量指標。  <br/> |
|[VideoClientEvent 表格](videoclientevent.md) <br/> |儲存從用戶端事件收集的視頻媒體質量指標。  <br/> |
|**DiagnosticData 資料表** <br/> |儲存僅供內部使用的診斷資料。  <br/> |
   
**摘要資料表格**

|**表格**|**說明**|
|:-----|:-----|
|**ServerSummary 資料表** <br/> |儲存伺服器的摘要資料，這些資料只適用于體驗品質（QoE）報告。  <br/> |
|**UserSummary 資料表** <br/> |儲存使用者的摘要資料，這些資料只用于 QoE 報告。  <br/> |
|**CallTypeSummary 資料表** <br/> |儲存通話類型摘要資料時，這些資料只用于 QoE 報告。  <br/> |
   
**供監視伺服器內部使用的表格**

|**表格**|**說明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |僅供內部使用。  <br/> |
|**DbConfigInt** <br/> |僅供內部使用。  <br/> |
|**前端表格** <br/> |僅供內部使用。  <br/> |
|**工作表** <br/> |僅供內部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |僅供內部使用。  <br/> |
|**DbErrorMessage** <br/> |僅供內部使用。  <br/> |
|**MetricsThreshold** <br/> |僅供內部使用。  <br/> |
|**DaylightSavingYears** <br/> |僅供內部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |僅供內部使用。  <br/> |
|**時區** <br/> |僅供內部使用。  <br/> |
|**CallSummary 資料表** <br/> |僅供內部使用。  <br/> |
|**DeviceCallSumary 資料表** <br/> |僅供內部使用。  <br/> |
|**租使用者資料表** <br/> |僅供內部使用。  <br/> |
|**VideoCallSummaryTable** <br/> |僅供內部使用。  <br/> |
|**ASCallSummaryTable** <br/> |僅供內部使用。  <br/> |
   

