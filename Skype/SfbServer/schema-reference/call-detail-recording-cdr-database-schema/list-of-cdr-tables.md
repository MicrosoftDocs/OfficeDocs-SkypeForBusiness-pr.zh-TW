---
title: 商務用 Skype Server 2015 中的 CDR 資料表清單
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
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: '[通話詳細資料錄製（CDR）] 資料庫架構由下清單格組成。'
ms.openlocfilehash: a35636333366bbfd55d4337fadfec68af681db6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815131"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 中的 CDR 資料表清單
 
[通話詳細資料錄製（CDR）] 資料庫架構由下清單格組成。 
  
## <a name="static-tables"></a>靜態資料表

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 CallPriorities 表格](callpriorities.md) <br/> |儲存可能的通話優先順序清單，例如緊急、緊急、正常、非緊急及其他。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格](conferencejointimethresholds.md) <br/> |儲存 [會議加入時間摘要] 報告所使用的分類界限。  <br/> |
|[商務用 Skype Server 2015 中的 DeRegisterType 表格](deregistertype.md) <br/> |儲存可能的使用者取消註冊原因清單，例如「用戶端啟動」、「註冊已過期」、「用戶端損毀」等等。  <br/> |
|[MediaList 表格](medialist.md) <br/> |儲存可在資料庫中產生專案的媒體類型清單（例如，IM、音訊、影片和檔案傳輸）。  <br/> |
|[PurgeSettings 資料表](purgesettings.md) <br/> |儲存資訊，指定是否要從 CDR 資料庫自動刪除過時的呼叫詳細資料記錄（以及時間）。  <br/> |
|[Roles 表格](roles.md) <br/> |儲存可能的會議角色清單（例如，出席者與簡報者）。  <br/> |
|[SIPResponseMetaData 資料表](sipresponsemetadata.md) <br/> |儲存 SIP 回應代碼清單，以及每個代碼的分類與定義。  <br/> |
   
## <a name="supporting-tables"></a>支援表格

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md) <br/> |儲存與在此資料庫中捕獲之資訊之通話所涉及之每個用戶端的用戶端（用戶端類型和版本號碼）。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md) <br/> |儲存在會議相關通話中使用的 ConferenceURIs 清單。  <br/> |
|[商務用 Skype Server 2015 中的主控表格](contenttypes.md) <br/> |儲存在對等通話和電話會議中使用的會話初始通訊協定（SIP）內容類型清單。  <br/> |
|[商務用 Skype Server 2015 中的 [裝置] 表格](devices.md) <br/> |儲存裝置清單，包括其製造商、硬體版本及 MAC 位址。  <br/> |
|[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) <br/> |儲存資料庫中每個會話之對話方塊識別碼的相關資訊。  <br/> |
|[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md) <br/> |儲存用於外部呼叫的邊緣伺服器清單。  <br/> |
|[商務用 Skype Server 2015 中的 [閘道] 表格](gateways.md) <br/> |儲存用於語音透過網際網路通訊協定（VoIP）通話的閘道清單。  <br/> |
|[商務用 Skype Server 2015 中的 HardwareVersions 表格](hardwareversions.md) <br/> |儲存裝置的硬體版本清單（電話）。  <br/> |
|[商務用 Skype Server 2015 中的 [製造商] 表格](manufacturers.md) <br/> |儲存裝置的製造商清單（電話）。  <br/> |
|[商務用 Skype Server 2015 中的 Mcus 表格](mcus.md) <br/> |儲存各種 A/V 會議伺服器及其 Uri 的相關資訊。  <br/> |
|[MediationServers 表格](mediationservers.md) <br/> |儲存用於 VoIP 通話的中繼伺服器清單。  <br/> |
|[Phones 表格](phones.md) <br/> |儲存已歸檔或通話詳細資料之 VoIP 通話中所用的所有電話號碼。  <br/> |
|[Pools 表格](pools.md) <br/> |儲存要捕獲 IM 訊息的 [池] 的名稱。  <br/> |
|[Servers 表格](servers.md) <br/> |儲存通話中所涉及的伺服器名稱。  <br/> |
|[Tenants 表格](tenants.md) <br/> |儲存目前部署所支援的租使用者。 企業使用者、同盟使用者、公用 IM 連線使用者和匿名使用者都有一些組建內部的租使用者。  <br/> |
|[UserAgentDef 資料表](useragentdef.md) <br/> |將使用者代理程式識別碼對應至代理程式的描述性名稱。  <br/> |
|[Users 表格](users.md) <br/> |儲存參與此資料庫中記錄或封存之會話之使用者的使用者 Uri。  <br/> |
|[UserStatistics 資料表](userstatistics.md) <br/> |儲存個別使用者使用系統的相關資訊。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>適用于會議 CDR 記錄的表格

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 [會議] 表格](conferences.md) <br/> |儲存已封存或記錄其詳細資料之所有會議的相關資訊，包括 ConferenceURI、開始和結束時間。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格](conferencesessiondetails-0.md) <br/> |儲存每個 SIP 會議會話的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個會話的診斷 ID。  <br/> |
|[商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格](focusjoinsandleaves.md) <br/> |儲存會議加入和離開的相關資訊，包括使用者的角色與用戶端版本。  <br/> |
|[商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格](mcujoinsandleaves.md) <br/> |儲存參與會議與使用者加入並離開時間的 A/V 會議伺服器資訊。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 會議中的訊息表格

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 ConferenceMessageCount 表格](conferencemessagecount.md) <br/> |針對每個 IM 會議，儲存每位使用者所傳送的訊息數目。  <br/> |
|[商務用 Skype Server 2015 中的 IMReportSummary 表格](imreportsummary.md) <br/> |提供組織中的立即訊息會話的整體報告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>點對點工作階段的資料表

|**表格**|**說明**|
|:-----|:-----|
|[SessionDetails 表格](sessiondetails.md) <br/> |儲存每個點對點工作階段的相關資訊，包括開始和結束時間、使用者識別碼、回應代碼，以及每個使用者的郵件數目。  <br/> |
|[商務用 Skype Server 2015 中的 FileTransfers 表格](filetransfers-0.md) <br/> |儲存檔案傳輸會話的相關資訊，包括檔案名與結果（接受、拒絕或取消）。  <br/> |
|[媒體資料表格](media.md) <br/> |儲存點對點工作階段中所涉及之不同媒體類型的相關資訊。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 通話詳細資料的表格

|**表格**|**說明**|
|:-----|:-----|
|[VoipDetails 表格](voipdetails-0.md) <br/> |針對每個雙方的 VoIP/PSTN 通話，儲存有關通話的資訊，例如 VoIP 電話的電話 ID、使用的閘道，以及哪個方已中斷連線。 參照[SessionDetails 資料表](sessiondetails.md)取得通話的開始/結束時間及回應碼。 <br/> |
   
> [!NOTE]
> 如果通話中有一方是 VoIP 使用者，或者如果是在通話中參與轉送伺服器，則會在此資料表中建立記錄。 有關 VoIP/VoIP 通話的資訊，不涉及在[SessionDetails 資料表](sessiondetails.md)中捕獲公用交換電話網絡（PSTN）電話。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1-1 通話審核的資料表

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 [位置] 表格](locations.md) <br/> |針對每個緊急通話（例如增強型9-1-1 （E9-1-1）通話），儲存通話的位置資訊。 參照[SessionDetails 資料表](sessiondetails.md)取得通話的開始/結束時間及回應碼。 <br/> |
   
> [!NOTE]
> 此表格僅包含 E9-1-1 通話的位置 blob。 參照 SessionDetails 資料表，取得有關通話的其他詳細資訊。 
  
## <a name="tables-for-troubleshooting"></a>疑難排解表格

|**表格**|**說明**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 [應用程式] 表格](application.md) <br/> |儲存在路由和連線中所涉及之商務用 Skype Server 2015 的各種處理常式資訊。  <br/> |
|[商務用 Skype Server 2015 中的 CallType 表格](calltype.md) <br/> |儲存有關通話類型的資訊，例如「音訊」、「立即訊息」、「音訊及視頻」和「應用程式共用」。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorCategory 表格](errorcategory.md) <br/> |儲存每個商務用 Skype Server 2015 診斷分類的易記名稱。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorDef 表格](errordef.md) <br/> |儲存錯誤類型和其定義的相關資訊。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorReport 表格](errorreport.md) <br/> |儲存所發生錯誤的相關資訊。  <br/> |
|[ProgressReport 表格](progressreport.md) <br/> |儲存有關商務用 Skype Server 2015 程式中所涉及之各個步驟的進度報告資訊。  <br/> |
   
下列清單中的表格是由商務用 Skype Server 2015 在內部使用。 本檔未說明其詳細資料。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 供內部使用的表格

|**表格**|**說明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |僅供內部使用。  <br/> |
|**DbConfigInt** <br/> |僅供內部使用。  <br/> |
|**DbErrorMessage** <br/> |僅供內部使用。  <br/> |
|**前端表格** <br/> |僅供內部使用。  <br/> |
|**MSMQProcessing 資料表** <br/> |僅供內部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |僅供內部使用。  <br/> |
|**Syndicators 資料表** <br/> |僅供內部使用。  <br/> |
|**SyndicatorsTenantMap 資料表** <br/> |僅供內部使用。  <br/> |
|**工作表** <br/> |僅供內部使用。  <br/> |
|**UserStatistics** <br/> |僅供內部使用。  <br/> |
|**UsageSummary_UQ** <br/> |僅供內部使用。  <br/> |
|**UsageSummary** <br/> |僅供內部使用。  <br/> |
|**DaylightSavingYears** <br/> |僅供內部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |僅供內部使用。  <br/> |
|**時區** <br/> |僅供內部使用。  <br/> |
|**FailureSummary_UQ** <br/> |僅供內部使用。  <br/> |
|**FailureSummary** <br/> |僅供內部使用。  <br/> |
|**ServerSummary** <br/> |僅供內部使用。  <br/> |
|**MsDiagMetaData** <br/> |僅供內部使用。  <br/> |
   

