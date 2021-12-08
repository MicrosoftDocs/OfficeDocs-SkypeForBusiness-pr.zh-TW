---
title: 客戶的合作夥伴管理
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
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
description: 客戶合作夥伴管理。
f1keywords: ''
ms.openlocfilehash: 84d15f43ff49565dbba915470ea618a69ff74ee8
ms.sourcegitcommit: c8951fe3504c1776d7aec14b79605aaf5d317e7f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/08/2021
ms.locfileid: "61331218"
---
# <a name="partner-management-for-customers"></a>客戶的合作夥伴管理


在受管理Teams 會議室 TRM (服務) 中的合作夥伴管理可讓客戶順暢地將存取權與責任委派給一或多個合作夥伴組織。 合作夥伴只能管理指派給管理聊天室。 

## <a name="on-boarding-partners"></a>上機合作夥伴
   透過 TRM 入口網站邀請合作夥伴，以建立貴組織與合作夥伴組織租使用者之間的關係。 

### <a name="invitation-to-partner"></a>邀請合作夥伴

   在這個方法中，合作夥伴應提供指派 (使用者) *UPNs。* 

**啟動邀請** 

1. 以 MMR 系統管理員Teams 會議室登入受管理入口網站。
1. 前往合作夥伴 **設定 >，** 然後選取新增 **合作夥伴。**
1. 在首列輸入主要系統管理員的名稱和 UPN。
1. 選取 **新增連絡人** 以確認。
1. 執行下列其中一項：
   - 若要新增其他使用者，請重複步驟 4。
   - 若要刪除使用者，請選取使用者右邊的 bin 圖示。

    > [!NOTE]
    > 由於邀請系結到 UPN，因此無法使用群組或通訊群組清單。

1. 選取 **下一步。**
1. 設定需要變更控制項核准的事件。 根據預設，所有控制項都設為 **自動核准。**

   > [!NOTE]
   > *目前僅提供自動核准。*
   > 
   >  1.  *手動核准：* 當合作夥伴執行動作時，會產生核准要求，要求客戶進行審核和核准。 直到要求核准之後，才會執行此動作。
   >  
   >  1. *自動核准：* 當合作夥伴執行動作時，系統不會產生核准要求，而且會立即執行該動作。
     
1. 選取 **下一步。**
1. 指派合作夥伴要管理的會議室，然後選取下 **一步。**
1. 若要繼續，請閱閱條款，然後選取 **我同意。**
1. 請閱閱邀請詳細資料。
1. 選取 **新增合作夥伴** 以傳送邀請。

邀請對於每個使用者都是唯一的，而且是獨立的。 第一個接受邀請的合作夥伴使用者將建立合作夥伴和租使用者之間的連結。 建立連結的使用者沒有特殊關聯，因此可讓使用者在重新指派時有彈性。 後續要接受的使用者會自動指派給主要系統管理員角色。 主系統管理員角色中必須至少有一個使用者。

若要管理主要系統管理員角色中的使用者，請參閱 [合作夥伴的多租使用者管理](multi-tenant-management-partner.md)。


## <a name="off-boarding-partners"></a>離機合作夥伴

**移除合作夥伴**

1. 以 MMR 系統管理員的登入 TRM-MTM 入口網站。
1. 流覽 至 設定 >**合作夥伴。**
1. 選取要移除的合作夥伴。
1. 在客戶詳細資料窗格中，選取移除 **合作夥伴。**
1. 選取 [刪除]。 
1. 在終止您與客戶租使用者之間關聯之確認提示時，選取 **刪除**。

## <a name="managing-partner-roles"></a>管理合作夥伴角色

合作夥伴角色可以讓合作夥伴更精細地將責任委派給其他人員。 這些角色的概念與角色 [型存取控制中所述的概念相同](microsoft-teams-rooms-premium-rbac.md)。 請注意，合作夥伴角色與自訂角色不同。 

主要 **系統管理員** 角色是每個新增合作夥伴的唯一內建角色。 此角色對指派給 TRM 服務之合作夥伴的聊天室擁有幾乎所有 (請參閱 [表格 1](#table-1)) 。 例如，如果您在全球擁有會議室，並指派合作夥伴來管理所有美國會議室，則主要系統管理員只能管理及委派這些聊天室的許可權。 在此案例中，此合作夥伴的主要系統管理員無法看到美國以外的任何會議室。 

### <a name="adding-primary-admins-to-partner"></a>新增主要系統管理員至合作夥伴

如果您已經將邀請寄給合作夥伴，並想要將更多使用者新增到該系統管理員，您可以將他們新增到合作夥伴系統管理員角色。 這實際上會傳送邀請給新增的使用者。

**新增使用者至現有合作夥伴**

1. 以 MMR 系統管理員的登入 TRM-MTM 入口網站。
1. 請前往 **設定 >角色。**
1. 選取  **合作夥伴角色。** 
1. 為 **對應的合作夥伴** 名稱選取主要系統管理員角色。
1. 在角色窗格中 **，選取作業**。
1. 選取已 **邀請的系統管理員** 作業。 
1. 在邀請的系統管理員作業窗格中，選取 **成員**。
1. 選取 **編輯**。
1. 輸入新使用者的 UPN，然後選取新增 **連絡人。**
1. 若要確認變更， **請選取** 儲存 。

<!--To remove users for an existing partner~~

1. ~~Login to the TRM-MTM portal as a MMR administrator~~
1. ~~Navigate to **Settings > Roles**~~
1. ~~Select the **Partner roles** tab~~
1. ~~Select the **Primary admin** role for the corresponding Partner name~~
1. ~~In the role pane, select the **Assignments** tab~~
1. ~~Select the **Invited admins** assignment~~ 
1. ~~In the Invited admins assignment pane, select the **Members** tab~~
1. ~~Select the **Edit** icon~~
1. ~~Enter the UPN of the new user and select **Add contact**~~
1. ~~Click **Save** to confirm the changes-->




### <a name="table-1"></a>表格 1

|功能|許可|**MMR 系統管理員**|**網站潛在客戶**|**網站技術**|**合作夥伴系統管理員**|
| :- | :- | :- | :- | :- | :- |
|房間|檢視|||||
||修改|||||
||重設按鍵|||||
||下載金鑰|||||
||取消註冊|||||
|群組管理|創建 |||||
||檢視|||||
||修改|||||
|更新響鈴管理|創建 |||||
||檢視|||||
||修改|||||
|報告|檢視|||||
|票證管理|建立客戶事件|||||
||檢視|||||
||更新|||||
|MMR 設定|檢視|||||
||修改|||||
|角色管理|檢視 |||||
||修改|||||





## <a name="security"></a>安全性

做為最終客戶，您可以保留對資料的存取權，並隨時完全移除合作夥伴。 

使用委派存取功能，合作夥伴不會取得 TRM 服務入口網站以外的任何其他許可權。 不過，TRM 服務中來自其他 Microsoft 產品的任何資料，都視為 TRM 服務的資料。 例如，雖然通話品質報告是從通話品質Teams匯出，但 TRM 入口網站中的任何資料都位於許可權範圍內。 

系統或系統管理中心AAD系統管理中心Teams任何其他 Microsoft 產品均不授予任何許可權。 此外，合作夥伴也沒有任何許可權來查看或修改邀請範圍中未定義的會議室。 

資料會位於客戶的租使用者中，不會複製到合作夥伴的租使用者。 

MTM 入口網站Azure AD驗證合作夥伴的登入認證。 請注意，目前客戶的驗證原則不適用於合作夥伴。 例如，如果客戶有多重要素驗證政策，它不會轉換成合作夥伴。 

若要拉取合作夥伴活動的記錄，請參閱 [稽核](multi-tenant-auditing.md)。 

> [!NOTE]
> AAD稽核和 O365 稽核不會從 TRM 入口網站中捕獲記錄。 
