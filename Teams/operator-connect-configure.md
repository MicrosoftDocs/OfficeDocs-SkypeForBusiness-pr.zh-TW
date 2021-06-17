---
title: 設定運算子連接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 深入瞭解如何設定運算子連接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: c4f4ec3d1d7cf39402da562e5939d794ac9f1624
ms.sourcegitcommit: 1b057bfcc3207960b956962845fd5051afe91722
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/15/2021
ms.locfileid: "52947575"
---
# <a name="configure-operator-connect"></a>設定運算子連接

>[!NOTE]
>運算子連接目前僅適用于公用 **預覽** 版。 公開預覽可讓您測試即將推出的功能，並提供意見回饋。 公開預覽中包含的功能可能不完整、可能會變更，且 Office 365 政府雲端不支援。

本文將說明如何設定運算子連接。 在配置運算子連接之前，請務必閱讀運算子 [連接](operator-connect-plan.md) 方案，以瞭解先決條件和授權的資訊。

## <a name="enable-an-operator"></a>啟用運算子

您可以在 Teams 系統管理中心啟用、編輯及移除運算子。 在左側流覽窗格中，前往語音> **運算子**。

若要啟用運算子：

1. **選擇運算子。** 在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。 然後選取您想要啟用的運算子。  

2. **選取國家/地區。** 在 **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。

3. **提供連絡人資訊 (選) 。** 如果您想要讓接線員連上運算子 Connect 的其他資訊，請勾選該方塊，並提供您的連絡人資訊。  

4. **接受資料傳輸通知。**

5. **新增運算子。** 選取 **新增為我的運算子** 以儲存。

## <a name="set-up-phone-numbers"></a>設定電話號碼

您設定電話號碼的方式取決於您要設定新使用者的電話號碼，或移動 Microsoft 通話方案或直接路由的現有號碼。

- 如果您需要取得新使用者的電話號碼，請參閱取得新 Teams [使用者的電話號碼](#acquire-numbers-for-new-teams-users)。

- 如果您想要將現有的號碼從通話方案移至運算子連接，請參閱將號碼從通話方案移至 [運算子連接](#move-numbers-from-calling-plans-to-operator-connect)。

- 如果您想要將現有號碼從直接路由移至運算子連接，請參閱將號碼從直接路由 [移至運算子連接](#move-numbers-from-direct-routing-to-operator-connect)。

>[!IMPORTANT]
>**緊急位址：** 與緊急位址相關聯的電話號碼是由您的接線員管理。 在 Teams 系統管理中心建立緊急位址後，您的接線員會指派電話號碼給這些緊急位址。 若要變更緊急位址及其指派的電話號碼，請與您的接線員聯繫。

### <a name="acquire-numbers-for-new-teams-users"></a>取得新 Teams 使用者的數位

若要取得新 Teams 使用者的數位，請遵循下列步驟：

1. **指派電話系統授權。** 您可以從 Microsoft 365 系統管理中心或 PowerShell 指派電話系統授權給使用者。 詳細資訊，請參閱指派 [Teams 附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. **請確定您目前使用 Teams 模式。** 若要檢查貴組織是否位於 Teams 模式，請在 Teams 系統管理中心，前往 Teams 升級> **全組織設定**。 若要檢查使用者是否位於 Teams 模式，請前往使用者 **並選取** 使用者帳戶。 在帳戶 **選項卡** 的 **Teams 升級下** ，確認您的共存模式已設定為'僅 Teams'。

3. **建立及驗證緊急位址。** 在 Teams 系統管理中心，前往緊急> **位置設定** 緊急位址。 若要深入瞭解，請參閱 [新增、變更或移除貴組織的緊急位置](add-change-remove-emergency-location-organization.md)。

4. **取得數位。** 請前往您的接線員網站訂購及取得電話號碼。 有關運算子網站的清單 [，請參閱運算子](#operators)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找您的 [Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以瞭解更多資訊。

5. **指派數位。** 您的接線員完成訂單後，就會將號碼上傳至您的租使用者。 您可以流覽 Teams 系統管理中心中的號碼和提供者，> **電話號碼**。 使用 Teams 系統管理中心或 PowerShell 指派號碼給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>將號碼從通話方案移至運算子連接

1. 請連連您的接線員，將您的號碼移植到運算子 Connect。 請參閱 [運算子](#operators) 以尋找您的運算子網站。

2. 您的接線員完成移移訂單之後，您可以取消為使用者的通話方案電話號碼進行分配，並移除通話方案授權。 然後，您的運算子可以將數位上傳到您的租使用者。

3. 使用 Teams 系統管理中心或 PowerShell 將號碼指派給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>將號碼從直接路由移至運算子連接

1. 從使用者移除現有電話號碼，如下所示：  

   執行下列 PowerShell 命令以取得現有的 On-prem Line URI：

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   執行下列 PowerShell 命令以移除 On-prem Line URI：  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. 移除任何與使用者相關聯的 PSTNUsage，否則通話會路由至 PSTN 使用量中指定的閘道。 若要瞭解如何移除 PSTN 使用量，請參閱 [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)。

3. 請前往您的接線員網站訂購及取得電話號碼。 有關運算子網站的清單 [，請參閱運算子](#operators)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找您的 [Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以瞭解更多資訊。

4. 您的接線員完成訂單後，就會將號碼上傳至您的租使用者。 您可以流覽 Teams 系統管理中心中的號碼和提供者，> **電話號碼**。 使用 Teams 系統管理中心或 PowerShell 將號碼指派給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

   

### <a name="assign-numbers"></a>指派數位

無論您是新增 Teams 使用者，或將現有使用者移動至 Operator Connect，指派號碼的步驟如下：

若要使用 Teams 系統管理中心指派號碼，請前往 **電話號碼**。 步驟與指派通話方案號碼的步驟相同。 詳細資訊，請參閱 [指派電話號碼給使用者](assign-change-or-remove-a-phone-number-for-a-user.md)。

若要使用 PowerShell 指派數位，請使用 Set-CsOnlineVoiceUser Cmdlet，如下所示：

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

例如：

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

若要瞭解如何指派電話號碼給使用者，請參閱指派、變更或移除使用者 [的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。



## <a name="manage-your-operators"></a>管理運算子

在 "我的運算子" 選項卡中，您可以查看運算子及其狀態，並變更下列選取專案：  

- 根據國家/地區管理運算子服務
- 暫停運算子
- 移除運算子

> [!NOTE]
> 在將接線員從貴組織或國家/地區移除之前，您必須移除指派給組織或國家/地區使用者的所有電話號碼，並請聯絡接線員以釋出號碼。

## <a name="operators"></a>運算元

您可以到此處連結的網站，從下列運算子取得電話號碼：


|運算元  |運算子網站  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
