---
title: 商務用 Skype Server 2015 的 CDR 表格清單
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 詳細通話記錄 (CDR) 資料庫結構描述包含下列表格。
ms.openlocfilehash: 1e8c76080089005977154c3e23d924a4b98dc6b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746659"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>商務用 Skype Server 2015 的 CDR 表格清單
 
詳細通話記錄 (CDR) 資料庫結構描述包含下列表格。 
  
## <a name="static-tables"></a>靜態表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 CallPriorities 表格](callpriorities.md) <br/> |儲存通話可能優先順序的清單 (如「緊急」、「急」、「一般」、「非緊急」等)。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceJoinTimeThresholds 表格](conferencejointimethresholds.md) <br/> |儲存會議加入時間摘要報告所使用的分類範圍。  <br/> |
|[商務用 Skype Server 2015 中的 DeRegisterType 表格](deregistertype.md) <br/> |儲存使用者取消註冊可能原因的清單 (如「由用戶端起始」、「註冊到期」或「用戶端損毀」等)。  <br/> |
|[MediaList 表格](medialist.md) <br/> |儲存各種媒體類型清單，這些類型會產生資料庫中的項目 (例如 IM、音訊、視訊以及檔案傳輸)。  <br/> |
|[PurgeSettings 表格](purgesettings.md) <br/> |儲存指定是否要從 CDR 資料庫自動刪除過時詳細通話記錄及何時刪除的資訊。  <br/> |
|[Roles 表格](roles.md) <br/> |儲存會議可能角色清單 (例如出席者和簡報者)。  <br/> |
|[SIPResponseMetaData 表格](sipresponsemetadata.md) <br/> |儲存 SIP 回應碼及這些回應碼的分類和定義清單。  <br/> |
   
## <a name="supporting-tables"></a>支援的表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 ClientVersions 表格](clientversions.md) <br/> |儲存通話方之每個用戶端的用戶端 (用戶端類型與版本號碼) 以及此資料庫中擷取的資訊。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceUris 表格](conferenceuris.md) <br/> |儲存會議相關通話中所使用的 ConferenceURI 清單。  <br/> |
|[商務用 Skype Server 2015 中的 ContentTypes 表格](contenttypes.md) <br/> |儲存工作階段初始通訊協定 (SIP) 內容類型清單，這些類型是用於對等式通話和電話會議。  <br/> |
|[商務用 Skype Server 2015 的裝置表格](devices.md) <br/> |儲存裝置清單 (包括，製造商、硬體版本以及 MAC 位址)。  <br/> |
|[商務用 Skype Server 2015 中的對話方塊表格](dialogs.md) <br/> |儲存資料庫中每個工作階段的對話方塊 ID 相關資訊。  <br/> |
|[商務用 Skype Server 2015 中的 EdgeServers 表格](edgeservers.md) <br/> |儲存用於撥打外線的 Edge Server 清單。  <br/> |
|[商務用 Skype Server 2015 的閘道表格](gateways.md) <br/> |儲存用於 Voice over Internet Protocol (VoIP) 通話的閘道清單。  <br/> |
|[商務用 Skype Server 2015 中的 HardwareVersions 表格](hardwareversions.md) <br/> |儲存裝置 (電話機) 硬體版本清單。  <br/> |
|[商務用 Skype Server 2015 中的製造商表格](manufacturers.md) <br/> |儲存裝置 (電話機) 製造商清單。  <br/> |
|[商務用 Skype Server 2015 中的 Mcus 表格](mcus.md) <br/> |儲存各種 A/V 會議伺服器及其 URI 的資訊。  <br/> |
|[MediationServers 表格](mediationservers.md) <br/> |儲存用於 VoIP 通話的中繼伺服器清單。  <br/> |
|[電話表格](phones.md) <br/> |儲存用於已封存或其通話詳細資料已記錄之 VoIP 通話中的所有電話號碼。  <br/> |
|[Pool 表格](pools.md) <br/> |儲存擷取 IM 訊息的集區名稱。  <br/> |
|[Servers 表格](servers.md) <br/> |儲存通話方的伺服器名稱。  <br/> |
|[承租人表格](tenants.md) <br/> |儲存目前部署支援的租用戶；包括企業使用者、同盟使用者、公共 IM 連線使用者以及匿名使用者的部分內建租用戶。  <br/> |
|[UserAgentDef 表格](useragentdef.md) <br/> |地圖使用者代理程式的識別碼命名為代理程式的描述性名稱。  <br/> |
|[Users 表格](users.md) <br/> |儲存資料庫中所記錄或封存的工作階段之使用者的使用者 URI。  <br/> |
|[UserStatistics 表格](userstatistics.md) <br/> |儲存個別使用者對系統使用狀況的相關資訊。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>會議 CDR 記錄特有表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的會議表格](conferences.md) <br/> |儲存已封存或其詳細資料已記錄之所有會議的資訊，包括 ConferenceURI，以及開始時間和結束時間。  <br/> |
|[商務用 Skype Server 2015 中的 ConferenceSessionDetails 表格](conferencesessiondetails-0.md) <br/> |儲存每個 SIP 型會議工作階段的相關資訊，包括每個工作階段的開始時間和結束時間、使用者識別碼、回應碼以及診斷 ID。  <br/> |
|[商務用 Skype Server 2015 中的 FocusJoinsAndLeaves 表格](focusjoinsandleaves.md) <br/> |儲存會議加入和葉子的資訊，包括使用者的角色和用戶端版本。  <br/> |
|[商務用 Skype Server 2015 中的 McuJoinsAndLeaves 表格](mcujoinsandleaves.md) <br/> |儲存參與會議的 A/V 會議伺服器以及使用者加入或離開時間之資訊。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 會議中的訊息表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的 ConferenceMessageCount 表格](conferencemessagecount.md) <br/> |針對每個 IM 會議，儲存每個使用者所傳送的訊息數目。  <br/> |
|[商務用 Skype Server 2015 中的 IMReportSummary 表格](imreportsummary.md) <br/> |提供組織內所保留之立即訊息工作階段的整體報告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>對等工作階段表格

|**Table**|**描述**|
|:-----|:-----|
|[SessionDetails 表格](sessiondetails.md) <br/> |儲存每個對等工作階段的資訊，包括每個使用者的開始時間和結束時間、使用者識別碼、回應碼以及訊息計數。  <br/> |
|[商務用 Skype Server 2015 中的 FileTransfers 表格](filetransfers-0.md) <br/> |儲存檔案傳輸工作階段的資訊，包括檔案名稱和結果 (接受、拒絕或取消)。  <br/> |
|[媒體表格](media.md) <br/> |儲存與對等工作階段相關之不同媒體類型的資訊。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 通話詳細資訊的表格

|**Table**|**描述**|
|:-----|:-----|
|[VoipDetails 表格](voipdetails-0.md) <br/> |會針對每次雙方 VoIP/PSTN 通話，儲存通話的相關資訊，例如 VoIP 電話的電話 ID、所用閘道，以及哪一方中斷連線。 指的是通話開始/結束時間和回應碼的 [SessionDetails 表格](sessiondetails.md) 。 <br/> |
   
> [!NOTE]
> 如果通話任一方是 VoIP 使用者或者有中繼伺服器參與通話，此表格中會建立一筆記錄。 在 [SessionDetails 表格](sessiondetails.md)中，會捕獲不涉及公用交換電話網路 (PSTN) 電話的 VoIP/VoIP 通話相關資訊。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 通話稽核表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 的位置表格](locations.md) <br/> |會針對每個緊急電話，如增強型 9-1-1 (E9-1-1) 通話，儲存通話的位置資訊。 指的是通話開始/結束時間和回應碼的 [SessionDetails 表格](sessiondetails.md) 。 <br/> |
   
> [!NOTE]
> 此表格僅包含針對 E9-1-1 通話的位置二進位大型物件。請參考 SessionDetails 表格以取得通話的其他詳細資訊。 
  
## <a name="tables-for-troubleshooting"></a>疑難排解表格

|**Table**|**描述**|
|:-----|:-----|
|[商務用 Skype Server 2015 中的應用程式表格](application.md) <br/> |儲存與路由及連線相關的商務用 Skype Server 2015 內各種程式的資訊。  <br/> |
|[商務用 Skype Server 2015 中的 CallType 表格](calltype.md) <br/> |儲存通話類型的相關資訊，例如「音訊」、「立即訊息」、「音訊和影片」和「應用程式共用」。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorCategory 表格](errorcategory.md) <br/> |儲存每個商務用 Skype Server 2015 診斷分類的易記名稱。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorDef 表格](errordef.md) <br/> |儲存錯誤類型與其定義的相關資訊。  <br/> |
|[商務用 Skype Server 2015 中的 ErrorReport 表格](errorreport.md) <br/> |儲存所發生錯誤的相關資訊。  <br/> |
|[ProgressReport 表格](progressreport.md) <br/> |儲存與商務用 Skype Server 2015 處理常式相關之各個步驟的進度報告相關資訊。  <br/> |
   
下列清單中的表格是由商務用 Skype Server 2015 內部使用。 本文件不提供其詳細資料。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 內部使用的表格

|**Table**|**描述**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |僅限內部使用。  <br/> |
|**DbConfigInt** <br/> |僅限內部使用。  <br/> |
|**DbErrorMessage** <br/> |僅限內部使用。  <br/> |
|**FrontEnd 表格** <br/> |僅限內部使用。  <br/> |
|**MSMQProcessing 表格** <br/> |僅限內部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |僅限內部使用。  <br/> |
|**Syndicators 表格** <br/> |僅限內部使用。  <br/> |
|**SyndicatorsTenantMap 表格** <br/> |僅限內部使用。  <br/> |
|**Task 表格** <br/> |僅限內部使用。  <br/> |
|**UserStatistics** <br/> |僅限內部使用。  <br/> |
|**UsageSummary_UQ** <br/> |僅限內部使用。  <br/> |
|**UsageSummary** <br/> |僅限內部使用。  <br/> |
|**DaylightSavingYears** <br/> |僅限內部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |僅限內部使用。  <br/> |
|**TimeZones** <br/> |僅限內部使用。  <br/> |
|**FailureSummary_UQ** <br/> |僅限內部使用。  <br/> |
|**FailureSummary** <br/> |僅限內部使用。  <br/> |
|**ServerSummary** <br/> |僅限內部使用。  <br/> |
|**MsDiagMetaData** <br/> |僅限內部使用。  <br/> |
   

