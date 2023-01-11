---
title: 在 Teams 中管理資源帳戶
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 在本文中，您將瞭解如何在 Microsoft Teams 中建立、編輯及管理資源帳戶。
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763574"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理資源帳戶

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>後續步驟

當您完成資源帳戶設定，並視需要指派電話號碼後，就可以透過自動語音應答或通話佇列使用資源帳戶。

若要深入瞭解，請參閱下列參照：

- [雲端自動語音應答](create-a-phone-system-auto-attendant.md)
- [雲端通話佇列](create-a-phone-system-call-queue.md)

您可以使用 [**編輯**] 選項編輯資源帳戶 **顯示名稱** 和 **資源帳戶** 類型。 完成 **後，** 選取 [儲存]。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>將現有的資源帳戶變更為使用Microsoft Teams 電話資源帳戶授權

若要將現有資源帳戶的授權從 **Teams 電話標準方案** 授權切換為 **Microsoft Teams 電話資源帳戶** 授權，您必須取得 **Microsoft Teams 電話資源帳戶** 授權，然後依照Microsoft 365 系統管理中心 [將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 一律移除 **Teams 電話標準方案** 授權，並在相同的授權活動中指派 **Microsoft Teams 電話資源帳戶** 授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法再如預期般運作。 如果發生這種情況，建議您為 **Microsoft Teams 電話資源** 帳戶授權建立新的資源帳戶，並移除損毀的資源帳戶。

## <a name="skype-for-business-server-2019"></a>商務用 Skype Server 2019

如果是儲存在商務用 Skype Server 2019 上的資源帳戶，可以搭配雲端通話佇列和雲端自動語音應答使用，請參閱 [規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue) 或 [規劃雲端自動語音應](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)答。 混合式實作 (直接路由) 上儲存的數位是使用內部部署 商務用 Skype Server 2019 伺服器上的[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) Cmdlet 來設定。

建立應用程式實例時，您需要使用的應用程式識別碼如下：

- **自動語音應答：** ce933385-9390-45d1-9512-c8d228074e07
- **通話佇列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果您希望商務用 Skype Server 2019 使用者能夠搜尋通話佇列或自動語音應答，您應該在商務用 Skype Server 2019 上建立資源帳戶，因為線上資源帳戶不會同步處理到 Active Directory。 當 sipfederationtls 的 DNS SRV 記錄解析為 商務用 Skype Server 2019 時，資源帳戶 **必須在** 商務用 Skype Server 2019 上使用 SfB 管理命令介面建立，並同步處理至 Azure AD。

針對混合式實作與商務用 Skype Server：

- [規劃雲端自動語音應答](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。
- [規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue)。
- [設定內部部署資源帳戶](/SkypeForBusiness/hybrid/configure-onprem-ra)。

## <a name="delete-a-resource-account"></a>刪除資源帳戶

請務必先將電話號碼與資源帳戶解除關聯再刪除，以免電話號碼卡在擱置模式中。

完成之後，您可以在 [使用者] 索引 **標籤底** 下刪除Microsoft 365 系統管理中心中的資源帳戶。

若要解除直接路由電話號碼與資源帳戶的關聯，請使用下列 Cmdlet：

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>隱藏 Teams 使用者的資源帳戶

您可能會想要隱藏 Teams 使用者的特定資源帳戶。 例如，您可能會想要防止 Teams 使用者直接撥打通話佇列，並略過設定上班時間的自動語音應答。

[資訊障礙](information-barriers-in-teams.md) 是用來隱藏資源帳戶。  繼續進行下列步驟之前，請先檢閱資訊障礙檔以瞭解可能的影響。

### <a name="required-subscriptions-and-permissions"></a>必要的訂閱和許可權 

若要存取和使用資訊障礙，貴組織必須擁有下列其中一個訂閱或附加元件： 

-   Microsoft 365 E5/A5 訂閱 (付費版或試用版) 。
-   Office 365 E5/A5/A3/A1 訂閱 (付費版或試用版) 。
-   Office 365 進階合規性附加元件。
-   Microsoft 365 E3/A3/A1 訂閱 + Microsoft 365 E5/A5 合規性附加元件。
- Microsoft 365 E3/A3/A1 訂閱 + Microsoft 365 E5/A5 測試人員風險管理附加元件。

> [!NOTE]
> 如果您已設定[Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)通訊錄原則，則必須先移除這些原則，再繼續執行下列步驟。   
> 
> 下列所有步驟均由租使用者全域系統管理員執行。 
>   
> 這些指示假設沒有設定其他資訊障礙。

#### <a name="teams-admin-center"></a>Teams 系統管理中心

1. 登入 [Teams 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2066851)。
2. 在左側的 [軌選] 功能表中，展開 **[Teams]**。
3. 選 **取 [Teams 設定]**。 
4. 向下捲動至 **[依名稱搜尋]**。
5. 開啟切換開關，並儲存變更。

如需此選項的詳細資訊，請參閱 [限制使用者在 Teams 中搜尋目錄時可以查看的](teams-scoped-directory-search.md)人員。

#### <a name="compliance---auditing"></a>合規性 - 稽核

1. 登入[Microsoft Purview 合規性入口網站](https://compliance.microsoft.com/)。
2. 在左側功能窗格中，選取 [ **稽核]**。
3. 如果稽核已關閉，將會顯示下列橫幅： 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="未啟用稽核時顯示稽核橫幅的螢幕擷取畫面":::
  
4. 選取 **[開始錄製使用者和系統管理員活動]**。 

如需稽核的詳細資訊，請參閱 [在 Microsoft 365 中設定稽核 (標準) ](/microsoft-365/compliance/audit-standard-setup)。

#### <a name="segmenting-data"></a>區段資料

不應該直接稱呼的資源帳戶必須進行區段和輕鬆識別。  您可以讓他們成為特定群組的成員，或是使用者設定檔中的一些唯一資訊，例如： 

-   公司
-   使用者主體名稱
-   位置
-   部門
-   使用位置
-    (別名) 的郵件昵稱
-   Office)  (實體遞送辦公室名稱
-   郵遞區號
-   Proxy 位址 (Email位址) 
-   街地道址
-   ExternalEmailAddress)  (目標位址
-   郵件 (WindowsEmailAddress) 
-   描述

在下面的範例步驟中，將會使用該 `Department` 欄位。 

如需區段使用者的詳細資訊，請參閱  [識別區段](/microsoft-365/compliance/information-barriers-policies)。

#### <a name="microsoft-admin-center"></a>Microsoft 系統管理中心

1. 登入[Microsoft 365 系統管理中心。](https://go.microsoft.com/fwlink/p/?linkid=2024339)
2. 在左側功能窗格中，選取 [ **作用中的使用者]**。
3. 選取第一個 [資源帳戶] 來封鎖直接通話。
4. 選取右窗格中的 **[管理連絡人資訊** ]。
5. 以不做為部門名稱的唯一單字或縮寫取代欄位的內容 `Department` 。 例如， `DNC` .
6. 儲存變更。
7. 針對每個需要封鎖才能接收直接來電的資源帳戶重複此步驟。

#### <a name="compliance---information-barriers"></a>合規性 - 資訊障礙

1. 登入[Microsoft Purview 合規性入口網站](https://compliance.microsoft.com/)。
2. 在左側功能窗格中，選取 **[資訊障礙**  >  **區段]**。
3. 選取 **[新增區段]**。
4. 輸入區段的名稱，然後選取 [ **下一步]**。 例如， `Uncallable Resource Accounts` .
5. 選取 **[+ 新增**]，然後選取 [ **部門]**。
6. 輸入上述 Microsoft 系統管理中心步驟 5 中使用的唯一單字或縮寫。 例如， `DNC` .
7. 選 **取 [下一步**]，然後選取 [ **提交]**。
8. 選取 **[新增區段]**。
9. 輸入區段的名稱，然後選取 [ **下一步]**。 例如， `Callable Users` .
10. 選取 **[+ 新增**]，然後選取 [ **部門]**。
11. 選取 **[等於** ] 下拉式清單，然後選取 [ **不等於]**。
12. 輸入上述 Microsoft 系統管理中心步驟 5 中使用的唯一單字或縮寫。 例如， `DNC` .
13. 選 **取 [下一步**]，然後選取 [ **提交]**。 
14. 在左側功能窗格中，選取 **[資訊障礙**  >  **原則]**。
15. 選 **取 [建立原則]**。
16. 輸入原則的名稱，然後選取 [ **下一步]**。 例如， `Uncallable Resource Accounts` .
17. 選取 **+ 選擇區段**、新增上述步驟 9 中建立的區段，然後選取 [ **下一步]**。 例如， `Callable Users` .
18. 從 **[通訊與共同作業]** 下拉式清單中選 **取 [封鎖**]。
19. 選取 **+ 選擇區段**、新增上述步驟 4 中建立的區段，然後選取 [ **下一步]**。 例如， `Uncallable Resource Accounts` .
20. 將原則設為 [ **開啟**]，選取 [ **下一步]**，然後 [ **提交]**。
21. 選 **取 [建立原則]**。
22. 輸入原則的名稱，然後選取 [ **下一步]**。 例如， `Callable Users` .
23. 選取 **+ 選擇區段**、新增步驟 4 中建立的區段，然後選取 [ **下一步]**。
24. 從 **[通訊與共同作業]** 下拉式清單中選 **取 [封鎖**]。 
25. 選取 **+ 選擇區段**、新增上述步驟 9 中建立的區段，然後選取 [ **下一步]**。
26. 將原則設為 [ **開啟**]，選取 [ **下一步]**，然後 [ **提交]**。
27. 在左側功能窗格中，選取 **[資訊障礙**  >  **原則應用程式]**。
28. 選 **取 [套用所有原則]**。

> [!NOTE]
> 套用原則可能需要 30 分鐘或更久的時間。  
> 
> 狀態顯示完成後，請移至 Teams 用戶端，並嘗試搜尋已封鎖的資源帳戶。 您可能需要清除 Teams 快取。  
> 
> 如果 Teams 使用者已將資源帳戶儲存為連絡人，他們將無法再撥打該帳戶。
