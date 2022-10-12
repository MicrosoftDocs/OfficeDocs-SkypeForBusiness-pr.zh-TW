---
title: 資料與隱私權資訊
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 06/01/2022
ms.reviewer: ''
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 資料與隱私權資訊
f1keywords: Microsoft Teams Rooms Managed Service Data and Privacy Information
ms.openlocfilehash: 50806ffce468ac9add956d6942c2b3b2e5885125
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532463"
---
# <a name="approach"></a>方法

使用Microsoft Teams 會議室受管理服務的客戶會將 Microsoft 最有價值的資產 — 資料。 他們信任其隱私權會受到保護，而且只會以符合其期望的方式使用。

技術會遵循隱私權程式，以確保符合客戶在收集和使用有效執行服務的資料時的承諾。
## <a name="data-collection-and-privacy"></a>資料收集與隱私權

 Microsoft Teams 會議室受管理的服務會監視裝置、收集客戶內容資料，並以系統管理員身分遠端存取和管理裝置。 收集的資料僅限於監控已註冊會議室中所識別之健康情況、根本原因及減輕問題所需的資訊。 收集的特定資料是聊天室帳戶的專屬資料，而非個別使用者。

> [!Note]
> 個別使用者的附隨性參照可能會在使用裝置期間出現在活動記錄檔中。

## <a name="who-can-access-data"></a>誰可以存取資料

受管理的服務會採取強烈措施，協助保護客戶資料，避免未經授權的人員不當存取或使用。 這些措施包括限制 Microsoft 人員和轉包商的存取權。

## <a name="zero-standing-access-data-storage"></a>零常用存取資料儲存空間

受管理的服務可透過零獨立存取原則，降低與具有組織內外惡意行為者許可權存取權之帳戶相關聯的風險。 此原則可讓受管理的服務在沒有任何使用者預設可用的許可權下運作。 結合「時間僅限時間」和「Just-Enough-Access」原則，為預設安全且符合規範的架構提供了強大的架構。 診斷資料可透過內部入口網站提供給 Microsoft 服務營運小組使用。

## <a name="data-handling"></a>資料處理

Microsoft 受到資料傳輸、儲存、使用和保留的嚴格標準所規範。 Microsoft 提供資料處理標準原則，以規範資料分類處理方式。

## <a name="technology-description"></a>技術描述

受管理的服務會將資料傳送至 Microsoft，以便監控、診斷及減輕部署中的任何問題。 範例包括

- 確保裝置是最新 (包括應用程式、作業系統、驅動程式、F/W) 
- 確保裝置已準備好使用 (登入、所有周邊設備報告健康狀態等) 
- 確保已布建帳戶 (環境就緒、網路速度夠快等等，) 
- 判斷是否有硬體問題或安裝問題， (例如鬆散的佈線) 
- 判斷過度重新開機 (問題的語言) 

受管理的服務會使用下列動作管理裝置：

- 更新軟體
- 透過重新開機、重設 USB 連線&狀態來減輕問題
- 收集特定記錄以協助診斷問題

受管理的服務不會從解決方案套件監控或錄製音訊、視訊、媒體或會議內容。

### <a name="service-collected-data-categories"></a>服務收集的資料類別
 
|類別|詳細資料|查詢理由|
| :- | :- | :- |
|持續的資料收集與管理|IP 位址、Exchange (聊天室帳戶的身分識別、商務用 Skype和/或 Teams) 、位置座標、與 Microsoft 或軟體在入口網站內的電子郵件和通訊|識別並聯機到管理下的系統;識別、診斷及減輕失敗;追蹤使用狀況、分析和深入資訊;查詢與修復線上狀態|
|臨機操作資料收集與管理|事件記錄資訊、使用者登入記錄檔之聊天室的使用者活動/身分識別，以及診斷資訊、Windows 系統查詢 (範例：USB 裝置清單、電源狀態等) |識別、診斷及減輕失敗，以及使用方式、分析和深入解析|

[裝置活動] 記錄檔中的某些機密資料會在本機轉帳 (不受 Managed Services) 收集：

- 會議主旨和本文
- 會議出席者 (的連絡人卡片資訊，例如職稱、電話號碼等) 
- 在會議 IM 訊息內容中

> [!NOTE]
> 隨著 Microsoft 不斷演進受管理的服務，特定資料可能會變更。

### <a name="enrollment"></a>註冊

Managed Services 已在線上入口網站註冊，以用於自動化監控和支援服務，包括診斷和報告。 註冊是透過使用裝置信賴平臺模組 (TPM) 型公開金鑰加密的網路通訊來完成。

### <a name="unenrollment"></a>取消註冊

卸載 Managed Services 可取消註冊裝置。 Microsoft 也會在解除委任期間將裝置從後端監視中移除，並可視要求刪除收集的資料。
## <a name="compliance"></a>合規性

所有使用產品的工程師都必須接受安全性與隱私權意識訓練。 Microsoft 也確保所有人員都接受隱私權需求的責任。

Managed Services 會透過歐洲 (歐盟) 、亞太地區 (APAC) 以及美國 (美國) 的資料中心提供地區資料居住支援。 服務客戶將擁有與組織相關的資料，儲存在其所選區域的資料中心。

## <a name="more-resources"></a>更多資源

Microsoft Teams 會議室 Windows 安全性： [[Microsoft Teams for Windows 安全性](/microsoftteams/rooms/security-windows)] \
Android 安全性Microsoft Teams 會議室：[Android 版 Microsoft Teams 安全性](/microsoftteams/rooms/security-android) \
Microsoft 隱私權聲明： https://aka.ms/privacy \
Microsoft 的資料管理： https://www.microsoft.com/trust-center/privacy/data-management \
受管理的服務服務描述： [Microsoft Teams Room 受管理的服務](microsoft-teams-rooms-premium.md)
