---
title: 管理資源帳戶Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: 本文將瞭解如何在 Microsoft Teams 中建立、編輯及管理資源Microsoft Teams。
ms.openlocfilehash: 84ca7a68cfc620c5f62dbdd6308c1862a7e7bda7
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249465"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理資源帳戶

資源帳戶是 Azure AD 中的停用使用者物件，一般可用來表示資源。 例如，資源帳戶可用於Exchange會議室，並允許會議室擁有電話號碼和日曆。 資源帳戶可以使用 2019 Microsoft 365或內部部署商務用 Skype Server中。

在 Microsoft Teams中，每個自動電話機或通話佇列都需要資源帳戶。 資源帳戶也可能被指派服務電話號碼。 這是您將電話號碼指派給自動語音機和通話佇列，讓來自Teams的來電者能夠到達自動語音機或通話佇列。

本文涵蓋如何建立資源帳戶，並準備好與自動通話和通話佇列一起使用。

在啟動本文中的程式之前，請確保您已完成下列操作：

- [取得虛擬使用者授權](#obtain-virtual-user-licenses)
- [取得服務編號](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a>取得虛擬使用者授權

每個資源帳戶都需要授權才能使用自動電話機和通話佇列。 您可以使用免費的虛擬使用者 *Microsoft 365 電話系統虛擬使用者* 授權。 若要取得這些授權，請參閱 [虛擬使用者授權](teams-add-on-licensing/virtual-user.md)。

本文稍後將說明如何將授權指派給資源帳戶。

若要取得虛擬使用者授權，請Microsoft 365 系統管理中心到帳單購買服務附加元件訂閱，然後卷電話系統 - 虛擬使用者  >    >  授權。  選取 **立即購買**。 零成本，但您仍然需要遵循這些步驟取得授權。

### <a name="obtain-service-numbers"></a>取得服務編號

自動語音機和通話佇列的服務號碼是選擇性的，不過您至少需要一個服務號碼，來電者才能撥打您的自動語音通話和通話佇列組。 對於您想要由服務號碼直接連接的任何自動電話機或通話佇列，您必須有具有關聯服務號碼的資源帳戶。

資源帳戶可以使用付費或免付費服務號碼。 您可以要求新的號碼，或從另一個電信公司埠現有的號碼。

若要取得新的服務號碼，請參閱取得 [服務電話號碼](getting-service-phone-numbers.md)。

若要從另一個電信公司移轉號碼，請參閱[將電話號碼移](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)Teams。

## <a name="create-a-resource-account"></a>建立資源帳戶

您可以在系統管理中心建立Teams帳戶。

![新增資源帳戶使用者介面的螢幕擷取畫面。](media/resource-account-add.png)

1. 在 Teams系統管理中心中，展開 **[語音**，然後按一下 **[資源帳戶**> 。

2. 按一下 [新增 **]**。

3. 在新增 **資源帳戶窗格中**，填寫 **顯示名稱**、**使用者名稱和****資源帳戶類型**。 資源帳戶類型可以是自動電話 **機或** 通話 **佇列**，取決於您打算使用此資源帳戶。

4. 按一下 [儲存]。

![資源帳戶清單的螢幕擷取畫面。](media/resource-accounts-page.png)

## <a name="assign-a-license"></a>指派授權

針對每個資源帳戶，您必須指派一個Microsoft 365 電話系統 *- 虛擬使用者**授權或* 電話系統授權。

![指派授權使用者介面的螢幕擷取畫面Microsoft 365 系統管理中心。](media/resource-account-assign-virtual-user-license.png)

1. 在 Microsoft 365 系統管理中心中，按一下要指派授權的資源帳戶。

2. On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.

3. 按一下 **[儲存變更]**。

## <a name="assign-a-service-number"></a>指派服務編號

如果您打算將資源帳戶與需要服務號碼的自動電話機或通話佇列一起使用，請指派號碼給資源帳戶。

![指派服務編號使用者介面的螢幕擷取畫面。](media/resource-account-assign-phone-number.png)

1. 在 Teams系統管理中心，在 [資源 **帳戶**> 頁面上，選取要指派服務號碼的資源帳戶，然後按一下 [**指派/取消指派**> 。

2. 在電話 **數位類型** 下拉式下拉清單中，選擇您想要使用的號碼類型。

3. 在 **[已指派的電話號碼** > 方塊中，搜尋您用的電話號碼，然後按一下 [ **新增**。

4. 按一下 [儲存]。


若要將直接路由或混合式號碼指派給資源帳戶，您需要使用 PowerShell：

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a>後續步驟

完成資源帳戶設定並指派服務號碼之後，就可以使用資源帳戶與自動電話機或通話佇列。

請參閱下列參照：

 - [雲端自動傳話機](create-a-phone-system-auto-attendant.md)

 - [雲端通話佇列](create-a-phone-system-call-queue.md)

您可以使用編輯選項編輯資源帳戶 **顯示** 名稱和資源 **帳戶** 類型。 完成 **時** ，按一下 [儲存。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>將現有的資源帳戶變更為使用虛擬使用者授權

如果您決定將現有資源帳戶上的授權從 **電話系統** 授權切換到虛擬使用者授權，您必須取得免費的虛擬使用者授權，然後按照 Microsoft 365 系統管理中心 中的步驟將使用者移至不同的 [訂閱。](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)

> [!WARNING]
> 永遠移除完整授權電話系統，並在同一個授權活動中指派虛擬使用者授權。 如果您移除舊授權，請儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能不再如預期運作。 如果發生這種情況，建議您為虛擬使用者授權建立新資源帳戶，並移除中斷的資源帳戶。

## <a name="skype-for-business-server-2019"></a>Skype商務用伺服器 2019

如果資源帳戶位於 Skype 商務用伺服器 2019，可用於雲端通話佇列和雲端自動話務員，請參閱規劃[雲端](/SkypeforBusiness/hybrid/plan-call-queue)通話佇列或[規劃雲端自動](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)話務員。 混合式 (直接路由) 上的數位是使用內部部署 商務用 Skype Server 2019 伺服器上[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) Cmdlet 設定。

建立應用程式實例時，您需使用的應用程式代碼為：

- **自動總機** ：ce933385-9390-45d1-9512-c8d228074e07
- **通話佇列** ：11cd3e2e-fcb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果您希望 Skype For Business Server 2019 使用者可搜尋通話佇列或自動話務員，您應該在 Skype for Business Server 2019 上建立資源帳戶，因為線上資源帳戶不會同步處理至 Active Directory。 當 sipfederationtls 的 DNS SRV 記錄解析為 商務用 Skype Server 2019時，必須在 Skype for Business Server 2019 使用 SfB Management shell 建立資源帳戶，並同步處理至 Azure AD。

針對與商務用 Skype Server的商務用 Skype Server：

   [規劃雲端自動語音應答](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [設定 on-prem 資源帳戶](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a>刪除資源帳戶

在刪除電話號碼之前，請務必先將電話號碼與資源帳戶解除關聯，以避免您的服務號碼卡在擱置模式。

完成之後，您可以刪除使用者Microsoft 365 系統管理中心中的資源帳戶。

若要從資源帳戶取消關聯直接路由電話號碼，請使用下列 Cmdlet：

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
