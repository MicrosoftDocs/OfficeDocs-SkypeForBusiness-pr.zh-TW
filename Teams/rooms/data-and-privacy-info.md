---
title: 資料與隱私權資訊
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 04/07/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 資料與隱私權資訊
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 0aea2402705eb817c7f075cf003245c0ad3258fd
ms.sourcegitcommit: b70f01d7eae2e3e6f7495c685518a2037aaece31
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/11/2022
ms.locfileid: "64757095"
---
# <a name="approach"></a>方法

使用受管理服務的客戶以其最有價值的資產— 資料來信任 Microsoft。 他們信任其隱私權會受到保護，而且只會以符合其期望的方式使用。

技術會遵循隱私權程式，以確保符合客戶在收集和使用有效執行服務的資料時所承諾的遵守。

## <a name="data-collection"></a>資料獲取

技術所收集的資料僅限於監控已註冊會議室中所識別之健康情況、根本原因及減輕問題所需的資訊。

技術將會監視裝置、收集遙測資料，並允許 Microsoft 以系統管理員身分遠端存取和管理裝置。

收集的遙測資料是專為會議室帳戶而非個別使用者。 個別使用者的附隨性參照可能會在使用裝置期間出現在活動記錄檔中。

### <a name="who-can-access-your-data"></a>神秘可以存取您的資料

技術服務會採取強烈措施，協助保護客戶資料，避免未經授權的人員不當存取或使用資料。 這包括限制 Microsoft 人員和轉包商的存取權。

### <a name="zero-standing-access-data-storage"></a>零常用存取資料儲存體

「技術」可透過零獨立存取原則，降低與具有許可權存取權之帳戶相關聯的風險，也就是組織內外惡意行為者所帶來的風險。 這可讓服務在沒有任何使用者預設可用許可權的情況下運作。 結合「時間僅限時間」和「Just-Enough-Access」原則，為預設安全且符合規範的架構提供了強大的架構。 我們的服務營運小組可透過內部入口網站取得診斷資料。

## <a name="data-handling"></a>資料處理

Microsoft 受到資料傳輸、儲存、使用和保留的嚴格標準所規範。 Microsoft 有資料處理標準原則，應根據資料分類來處理資料。

Microsoft 會將一般資料保護規定 (GDPR) 資料保護權延伸到全球所有客戶，而不只是在歐洲。

## <a name="data-classification"></a>資料分類

資料分類可用來遵守安全性、合規性，以及收集、儲存及使用使用者個人資訊的隱私權需求和程式。


|分類|描述|範例|
| :- | :- | :- |
|客戶內容|系統管理員和使用者直接提供/建立的內容。|<p>- 客戶產生的 BLOB 或結構化儲存資料</p><p>- 客戶擁有/提供的機密 (密碼、憑證、加密金鑰、儲存金鑰) </p>|
|EUII)  (使用者標識資訊|識別或可用來識別 Microsoft 服務使用者的資料。 EUII 不包含客戶內容。|<p>- domain\UserName (使用者名稱或顯示名稱) </p><p>- 使用者主體名稱 (name@company.com) </p><p>- 使用者專屬的 IP 位址</p>|
|帳戶資料|<p>客戶帳單資訊和付款工具資訊，包括系統管理員連絡資訊，例如租使用者</p><p>系統管理員的名稱、位址或</p><p>電話號碼。</p>|<p>- 租使用者系統管理員 (連絡資訊，例如</p><p>租使用者系統管理員的名稱、位址、電子郵件地址、電話號碼) </p><p>- 客戶布建</p><p>資訊</p>|
|EUPI (使用者虛擬名識別碼) |<p>Microsoft 所建立的識別碼系結至 Microsoft 服務的使用者。 當 EUPI 與其他資訊結合時，例如對應資料表，它會識別使用者。 EUPI 不包含客戶上傳或建立的資訊</p><p> (客戶內容或 EUII) </p>|<p>- 使用者 GUID、PUID 或 SIM 卡</p><p>- 會話識別碼</p>|
|組織標識資訊 (OII) |可用來識別租使用者的資料，通常是設定或使用狀況資料。 此資料無法連結至使用者，也不包含客戶內容。|<p>- 非 GUID)  (租使用者識別碼</p><p>- 電子郵件地址中的功能變數名稱 (xxx@contoso.com) 或其他租使用者專屬網域</p><p>資訊</p>|
|系統中繼資料|執行無法連結至使用者或租使用者的服務或程式時所產生的資料。|<p>- 事件記錄檔</p><p>- 使用狀況資料</p><p>- 設定資料</p>|

技術描述

為了監控、診斷及減輕部署中的任何問題，技術會將資料傳送至 Microsoft。 範例包括

1. 確保裝置是最新 (，包括應用程式、作業系統、驅動程式、F/W) 
1. 確保裝置已準備好使用 (登入、所有周邊設備報告健康狀態等) 
1. 確保已布建帳戶 (環境就緒、網路速度夠快等等，) 
1. 判斷是否有硬體問題或安裝問題， (例如鬆散的佈線) 
1. 判斷過度重新開機 (問題的語言)  

技術會使用動作來管理裝置，例如

1. 更新軟體
1. 透過重新開機、重設 USB 連線&狀態來減輕問題
1. 收集特定記錄以協助診斷問題

技術不會監視或錄製解決方案套件中的音訊、視訊、媒體或會議內容。 

### <a name="service-collected-data-categories"></a>服務收集的資料類別
 
|類別|詳細資料|查詢理由|
| :- | :- | :- |
|持續的資料收集&管理|IP 位址、會議室帳戶 (Exchange的身分識別、商務用 Skype和/或Teams) 、位置座標、與 Microsoft 或軟體在入口網站內的電子郵件和通訊|識別並連線管理下的系統;識別、診斷及減輕失敗;追蹤使用量、分析和Insights;查詢&修復線上狀態|
|管理&特設資料收集|<p>事件記錄資訊、從會議室使用者登入記錄檔的使用者活動/身分識別，以及診斷資訊 \* 、Windows系統查詢 (範例：USB 裝置清單、</p><p>電源狀態等) </p>|識別、診斷和減輕失敗，以及使用方式、分析和Insights|
|<p>試用註冊和</p><p>設置</p>|<p>Windows系統查詢]</p><p>範例：USB 裝置清單、電源狀態等</p>|<p>註冊、上線、訂單和遞送需要，</p><p>並設定試用版。</p>|

\* [裝置活動] 記錄檔中的敏感性 PII 會在本機轉譯， (技術) 不會收集：

1. 會議主旨&內文
1. 會議出席者 (的連絡人卡片資訊，例如標題、電話號碼等) 
1. 在會議 IM 訊息內容中

>> [!NOTE]
>隨著 Microsoft 不斷演進技術，特定資料可能會變更。 

### <a name="agent-data-classification"></a>代理程式資料分類

**MTRP 代理程式在持續監視期間所收集之所有資料的詳細描述**
|收集的資料描述|分類|
| :- | :- |
|共用裝置的身分識別|OII|
|客戶識別碼|OII|
|MMR 代理程式目錄位置|系統中繼資料|
|MTR 應用程式記錄目錄位置|系統中繼資料|
|裝置序號|系統中繼資料|
|Device Bios Information|系統中繼資料|

|MMR 代理程式版本|系統中繼資料|
| :- | :- |
|MTR 應用程式的版本|系統中繼資料|
|Teams 應用程式的版本|系統中繼資料|
|MTR 應用程式的夜間維護工作時間|系統中繼資料|
|MMR 代理程式更新 URL|系統中繼資料|
|MMR 代理程式通道|系統中繼資料|
|Windows作業系統版本|系統中繼資料|
|目前已登入的使用者|系統中繼資料|
|MMR 代理程式會話 GUID|系統中繼資料|
|功能變數名稱|系統中繼資料|
|上次作業系統重新開機後的時間|系統中繼資料|
|上次 MMR 代理程式啟動後的時間|系統中繼資料|
|MTR 裝置製造商和型號|系統中繼資料|
|裝置處於使用狀態|系統中繼資料|
|裝置上線類型|系統中繼資料|
|連接的監視器數目|系統中繼資料|
|MTR 喇叭詳細資料|系統中繼資料|
|MTR 麥克風詳細資料|系統中繼資料|
|MTR 預設喇叭詳細資料|系統中繼資料|
|MTR 應用程式自動螢幕畫面分享設定|系統中繼資料|
|MTR 應用程式藍牙廣告設定|系統中繼資料|
|上次變更密碼的日期|系統中繼資料|
|[MTR 密碼旋轉] 設定|系統中繼資料|
|MTR 應用程式Teams/商務用 Skype設定|系統中繼資料|
|MTR 應用程式更新通道|系統中繼資料|
|MTR 應用程式內容相機設定|系統中繼資料|
|MTR 應用程式會議名稱設定|系統中繼資料|
|會議室前方的 MTR 應用程式顯示設定|系統中繼資料|
|MTR 應用程式 GUID|系統中繼資料|
|Proxy 位址和埠|系統中繼資料|
|MTR 裝置的健康情況|系統中繼資料|
|MTR 會議室帳戶的詳細資料|OII|
|IPV4 位址和 IPV6 位址|OII|
|經度和緯度|OII|
|MTR 裝置主機名稱|OII|
|MTR 裝置時區|系統中繼資料|
|MTR 應用程式的狀態|系統中繼資料|
|Cres 要服務詳細資料|系統中繼資料|
|Logitech 韌體版本和 Logitech 同步處理版本|系統中繼資料|
|使用中的 CPU 總數百分比|系統中繼資料|
|使用中的 RAM 總數|系統中繼資料|
|MTR Skype 或 Teams 應用程式使用的 CPU|系統中繼資料|
|MTR 裝置溫度|系統中繼資料|
|內部磁片磁碟機的狀態|系統中繼資料|
|任何 MTR 應用程式當機的詳細資料|系統中繼資料|
|裝置上應用程式所偵測到之記憶體洩漏的詳細資料|系統中繼資料|

|<p>任何裝置藍色畫面錯誤的詳細資料</p><p>過去 24 小時</p>|系統中繼資料|
| :- | :- |
|<p>MTR 應用程式在會議期間偵測到的任何錯誤詳細資料</p><p>裝置</p>|系統中繼資料|
|已安裝的軟體詳細資料|系統中繼資料|
|已安裝 / 擱置中 / 缺少快捷方式修正詳細資料|系統中繼資料|
|辨識的硬體詳細資料|系統中繼資料|
|裝置上所有驅動程式的詳細資料|系統中繼資料|
|任何 MMR 裝置補救的詳細資料|系統中繼資料|
|過去 24 小時內的會議室使用量詳細資料、會議時間和計數|系統中繼資料|
|自動Windows商店更新的詳細資料|系統中繼資料|
|Windows作業系統更新的詳細資料|系統中繼資料|
|MMR 代理程式的擠壓詳細資料|系統中繼資料|
|MMR 代理程式連線錯誤詳細資料|系統中繼資料|
|TPM 安全性是否已啟用的詳細資料|系統中繼資料|
|MTR 裝置線上狀態的詳細資料|系統中繼資料|

**針對事件診斷與補救收集的資料 MTRP 代理程式**
|收集的資料描述|分類|
| :- | :- |
|<p>事件記錄檔：系統、應用程式、Skype會議室系統、Microsoft-Windows-AppXDeploymentServer%4Operational、Microsoft-Windows- PowerShell%4Operational、Microsoft-Windows- AppXDeployment%4Operational、Microsoft-Windows- AppXDeploymentServer%4Operational、Microsoft-Windows- TWinUI%4Operational、Microsoft Managed Rooms、Microsoft-Windows-</p><p>TaskScheduler%4Operational， Security</p>|系統中繼資料|
|已編輯的 MTR 應用程式記錄檔\*|系統中繼資料|
|Microsoft Teams 記錄檔|系統中繼資料|
|MMR 代理程式 sqlLitedb|系統中繼資料|
|裝置電源狀態資訊的詳細資訊|系統中繼資料|
|裝置群組原則資訊|系統中繼資料|
|所有 MMR 代理程式動作的稽核追蹤|系統中繼資料|
\* 裝置活動記錄檔中的敏感性 PII 會在本機轉譯。

### <a name="enrollment"></a>註冊


這項技術將向線上入口網站註冊，以進行自動化監控和支援服務，包括診斷和報告。 註冊是透過使用裝置信賴平臺模組 (TPM) 型公開金鑰加密的網路通訊來完成。

### <a name="un-enrollment"></a>取消註冊

您可以卸載技術來取消註冊裝置。 Microsoft 也會在解除委任期間將裝置從後端監視中移除，並可視要求刪除收集的資料。

### <a name="data-flow"></a>資料流程程

技術會將代理程式的資料流程程新增至 MTR Managed Services。

![從代理程式到 MTR 受管理服務的資料流程](../media/data-and-privacy-info-005.png)

啟用適用於端點的 Microsoft Defender整合，將帶來從 MDE 代理程式到 Microsoft Defender 基礎結構的其他資料流程程。

![從 MDE 代理程式到 Defender 的其他資料流程程](../media/data-and-privacy-info-006.png)

## <a name="compliance"></a>合規性

所有使用產品的工程師都必須接受安全性與隱私權意識訓練。 Microsoft 也確保所有人員都接受隱私權需求的責任。

此技術會透過歐洲 (歐盟) 、亞太地區 (APAC) 以及美國 (美國) 的資料中心提供地區資料居住支援。 這表示服務客戶將擁有與組織相關的資料，儲存在其所選區域的資料中心。

## <a name="additional-resources"></a>其他資源

Microsoft Teams 會議室安全性：/microsoftteams/rooms/security Microsoft 隱私權聲明： https://aka.ms/privacyMicrosoft 的資料管理： https://www.microsoft.com/trust-center/privacy/data-management 技術服務描述：[Microsoft Teams Room 管理服務](microsoft-teams-rooms-premium.md)
