---
title: QoE 表格清單
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 資料庫結構描述由下列表格所組成。
ms.openlocfilehash: 1d6d60d06dcb6cbfdde6a4fdbbd2746d00aa8531
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601268"
---
# <a name="list-of-qoe-tables"></a>QoE 表格清單
 
資料庫結構描述由下列表格所組成。 
  
**支援的表格**

|**表格**|**描述**|
|:-----|:-----|
|[AppSharingMetricsThreshold 表格](appsharingmetricsthreshold.md) <br/> |針對用於應用程式共用的經驗品質計量，儲存最佳且可接受的值。  <br/> |
|[CodecDescription 表格](codecdescription.md) <br/> |將唯一轉碼器識別碼對應至其相對應的轉碼器。  <br/> |
|[IPAddress 表格](ipaddress.md) <br/> |將 IP 位址對應至用在經驗品質資料庫其他地方的唯一 IP 位址識別碼。  <br/> |
|[NetworkConnectionDetail 表格](networkconnectiondetail.md) <br/> |將網路連線類型對應至用在經驗品質資料庫其他地方的網路連線識別碼。  <br/> |
|[PurgeSettings table (QoE) ](purgesettings-qoe.md) <br/> |儲存指定是否 (何時) 要從 QoE 資料庫中自動刪除過期經驗品質記錄的資訊。  <br/> |
|[TraceRoute 表格](traceroute.md) <br/> |儲存通話的路由資訊。  <br/> |
|[UserAgentDef table (QoE) ](useragentdef-qoe.md) <br/> |地圖使用者代理程式的識別碼命名為代理程式的描述性名稱。  <br/> |
|[VideoMetricsThreshold 表格](videometricsthreshold.md) <br/> |針對用於視訊通話的經驗品質計量，儲存最佳且可接受的值。  <br/> |
|[UserAgent 表格](useragent.md) <br/> |儲存音訊和視訊工作階段中所用的工作階段初始通訊協定 (SIP) 使用者代理程式 (UA) 字串與 UA 類型。  <br/> |
|[使用者表格](user-0.md) <br/> |儲存音訊和視訊工作階段中所用的使用者、會議以及電話 URI。  <br/> |
|[Endpoint 表](endpoint.md) <br/> |儲存參與音訊和視訊工作階段之端點的 FQDN 電腦名稱。  <br/> |
|[Pool 表格](pool.md) <br/> |儲存計量資料所屬之集區的名稱。  <br/> |
|[裝置表格](device.md) <br/> |儲存音訊/視訊通話中所用的擷取裝置和轉換裝置。  <br/> |
|[DeviceDriver 表格](devicedriver.md) <br/> |儲存音訊/視訊通話中所用的擷取裝置和轉換裝置驅動程式。  <br/> |
|[會議表格](conference.md) <br/> |儲存會議案例的會議 URI 或是其他案例的 DialogID。  <br/> |
|[SessionCorrelation 表格](sessioncorrelation.md) <br/> |儲存 PSTN 通話的 CorrelationID。  <br/> |
|[PayloadDescription 表格](payloaddescription.md) <br/> |儲存音訊/視訊通話中所用的轉碼器。  <br/> |
|[AppliedBandwidthSource 表格](appliedbandwidthsource.md) <br/> |儲存音訊/視訊通話中所用的頻寬來源。  <br/> |
|[MacAddress 表格](macaddress.md) <br/> |儲存參與音訊和視訊工作階段之端點的 MAC 位址。  <br/> |
|[Dialog 表格](dialog.md) <br/> |儲存音訊和視訊工作階段的對話方塊 ID。  <br/> |
|[地區表格](region.md) <br/> |儲存 NCS 設定中所定義的網路地區。  <br/> |
|[UserSite 表格](usersite.md) <br/> |儲存 NCS 設定中所定義的網站。  <br/> |
|[Subnet 表格](subnet.md) <br/> |儲存 NCS 設定中所定義的子網路。  <br/> |
|[MonitoredRegionLink 表格](monitoredregionlink.md) <br/> |儲存 NCS 設定中所定義的區域連結。  <br/> |
|[MonitoredUserSiteLink 表格](monitoredusersitelink.md) <br/> |儲存 NCS 設定中所定義的網站連結。  <br/> |
|[EndpointSubnet 表格](endpointsubnet.md) <br/> |儲存參與音訊和視訊工作階段之端點的子網路。  <br/> |
|[伺服器表格](server.md) <br/> |儲存媒體通過之伺服器的 FQDN 或 IP 位址。  <br/> |
   
**計量資料表格**

|**表格**|**描述**|
|:-----|:-----|
|[AppSharingStream 表格](appsharingstream.md) <br/> |儲存用於應用程式共用之網路串流的經驗品質計量。用於應用程式共用之網路串流的經驗品質計量。  <br/> |
|[Session 表格](session.md) <br/> |儲存音訊或音訊/視訊工作階段的整體資訊。工作階段定義為兩個端點之間的音訊或視訊 SIP 對話。  <br/> |
|[MediaLine 表格](medialine-0.md) <br/> |儲存工作階段中每個媒體行的相關資訊。媒體行為一或多個音訊及視訊資料流的集合。一般來說，單一媒體行會有兩個音訊或視訊資料流。  <br/> |
|[AudioStream 表格](audiostream.md) <br/> |儲存媒體行中每個音訊資料流的音訊媒體品質計量。  <br/> |
|[AudioSignal 表格](audiosignal.md) <br/> |儲存媒體行中音訊媒體品質計量。這包括柔和式迴音效果取消 (AEC) 以及自動增益控制 (AGC) 計量。  <br/> |
|[VideoStream 表格](videostream.md) <br/> |儲存媒體行中每個音訊資料流的視訊媒體品質計量。  <br/> |
|[AudioClientEvent 表格](audioclientevent.md) <br/> |儲存從用戶端事件收集到的音訊媒體品質計量。  <br/> |
|[VideoClientEvent 表格](videoclientevent.md) <br/> |儲存從用戶端事件收集到的視訊媒體品質計量。  <br/> |
|**DiagnosticData 表格** <br/> |儲存僅限內部使用的診斷資料。  <br/> |
   
**摘要資料表格**

|**表格**|**描述**|
|:-----|:-----|
|**ServerSummary 表格** <br/> |儲存伺服器的摘要資料，這些資料僅用於經驗品質 (QoE) 報告。  <br/> |
|**UserSummary 表格** <br/> |儲存使用者的摘要資料，這些資料僅用於經驗品質 (QoE) 報告。  <br/> |
|**CallTypeSummary 表格** <br/> |儲存通話類型的摘要資料，這些資料僅用於經驗品質 (QoE) 報告。  <br/> |
   
**監控伺服器所用的內部使用表格**

|**表格**|**描述**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |僅限內部使用。  <br/> |
|**DbConfigInt** <br/> |僅限內部使用。  <br/> |
|**FrontEnd 表格** <br/> |僅限內部使用。  <br/> |
|**Task 表格** <br/> |僅限內部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |僅限內部使用。  <br/> |
|**DbErrorMessage** <br/> |僅限內部使用。  <br/> |
|**MetricsThreshold** <br/> |僅限內部使用。  <br/> |
|**DaylightSavingYears** <br/> |僅限內部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |僅限內部使用。  <br/> |
|**TimeZones** <br/> |僅限內部使用。  <br/> |
|**CallSummary 表格** <br/> |僅限內部使用。  <br/> |
|**DeviceCallSumary 表格** <br/> |僅限內部使用。  <br/> |
|**Tenant 表格** <br/> |僅限內部使用。  <br/> |
|**VideoCallSummaryTable** <br/> |僅限內部使用。  <br/> |
|**ASCallSummaryTable** <br/> |僅限內部使用。  <br/> |
   

