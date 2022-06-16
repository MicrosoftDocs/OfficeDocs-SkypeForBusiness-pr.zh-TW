---
title: 在 Teams 中管理資源帳戶
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
description: 在本文中，您將瞭解如何在Microsoft Teams中建立、編輯和管理資源帳戶。
ms.openlocfilehash: 176cf304909094ae12c102f26ccbcd777366b649
ms.sourcegitcommit: e38dc23e3968f55625e90c8883884045f80d22ee
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2022
ms.locfileid: "66124158"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>在 Microsoft Teams 中管理資源帳戶

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>後續步驟

當您完成資源帳戶設定，並視需要指派服務號碼後，就可以將資源帳戶與自動語音應答或通話佇列搭配使用。

若要深入瞭解，請參閱下列參照：

- [雲端自動語音應答](create-a-phone-system-auto-attendant.md)
- [雲端通話佇列](create-a-phone-system-call-queue.md)

您可以使用 [**編輯**] 選項編輯資源帳戶 **顯示名稱** 和 **資源帳戶** 類型。 完成 **後，** 按一下 [儲存]。

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a>將現有的資源帳戶變更為使用虛擬使用者授權

如果您決定將現有資源帳戶的授權從 **Teams 電話標準方案** 授權切換為虛擬使用者授權，您將需要取得免費的虛擬使用者授權，然後依照Microsoft 365 系統管理中心中的步驟 [將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 一律移除完整Teams 電話標準方案授權，並在相同的授權活動中指派虛擬使用者授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法再如預期般運作。 如果發生這種情況，建議您為虛擬使用者授權建立新的資源帳戶，並移除損毀的資源帳戶。

## <a name="skype-for-business-server-2019"></a>商務用 Skype Server 2019

針對儲存在 Skype For Business Server 2019 上的資源帳戶，可用於雲端通話佇列和雲端自動語音應答，請參閱[規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue)或[規劃雲端自動語音應答](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。 混合式實作 (直接路由) 上儲存的數位是使用內部部署 商務用 Skype Server 2019 伺服器上的[New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) Cmdlet 來設定。

建立應用程式實例時，您需要使用的應用程式識別碼如下：

- **自動語音應答：** ce933385-9390-45d1-9512-c8d228074e07
- **通話佇列：** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> 如果您希望商務用 Skype Server 2019 使用者能夠搜尋通話佇列或自動語音應答，您應該在商務用 Skype Server 2019 上建立資源帳戶，因為線上資源帳戶不會同步到 Active Directory。 當 sipfederationtls 的 DNS SRV 記錄解析為 商務用 Skype Server 2019 時，資源帳戶 **必須在** 商務用 Skype Server 2019 上使用 SfB 管理命令介面建立，並同步處理至 Azure AD。

針對與商務用 Skype Server混合的實作：

   [規劃雲端自動語音應答](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

   [規劃雲端通話佇列](/SkypeforBusiness/hybrid/plan-call-queue)

   [設定內部部署資源帳戶](/SkypeForBusiness/hybrid/configure-onprem-ra)

## <a name="delete-a-resource-account"></a>刪除資源帳戶

請務必在刪除之前先將電話號碼與資源帳戶解除關聯，以免服務號碼卡在擱置模式中。

完成之後，您可以在 [使用者] 索引標籤底下刪除Microsoft 365 系統管理中心中的資源帳戶。

若要解除直接路由電話號碼與資源帳戶的關聯，請使用下列 Cmdlet：

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```
