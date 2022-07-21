---
title: 設定運算子連線
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
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
description: 深入瞭解如何設定運算子連線。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e9a773e7c8767164480374826a2410050681505a
ms.sourcegitcommit: 5a8a077b30a0eab2342afc422869adaa682a015b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/20/2022
ms.locfileid: "66915191"
---
# <a name="configure-operator-connect"></a>設定運算子連線

本文將說明如何設定運算子連線。 在設定運算子連線之前，請務必閱讀 [運算子連線方案](operator-connect-plan.md) ，以取得先決條件和授權的相關資訊。

## <a name="enable-an-operator"></a>啟用運算子

您可以在 Teams 系統管理中心啟用、編輯及移除運算子。 在左側功能窗格中，移至 **[語音>運算子]**。

若要啟用運算子：

1. **選擇運算子。** 在 [ **所有運算子]** 索引標籤中，依地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。 然後選取您要啟用的運算子。  

2. **選取 [國家/地區]。** 在 [ **運算子設定] 底** 下，選取您要使用所選運算子啟用的國家/地區。

3. **提供連絡資訊** 您的連絡資訊，包括全名和電子郵件地址，將會自動與您的電信業者共用。 您可以稍後變更這項資訊。 此外，您必須提供公司規模，而且您也可以選擇提供電話號碼。 運算子會使用此資訊與您連絡，提供有關運算子連線的詳細資料。

4. 接受資料傳輸通知。

5. **新增您的運算子。** 選 **取 [新增為我的運算子** ] 以儲存。

## <a name="set-up-phone-numbers"></a>設定電話號碼

設定電話號碼的方式取決於您要為新使用者設定號碼，或是從 Microsoft 通話方案或直接路由移動現有號碼。

- 如果您需要取得新使用者的電話號碼，請參閱 [取得新 Teams 使用者的電話號碼](#acquire-numbers-for-new-teams-users)。

- 如果您想要將現有的號碼從通話方案移至運算子連線，請參閱 [將號碼從通話方案移至運算子連線](#move-numbers-from-calling-plans-to-operator-connect)。

- 如果您想要將現有數位從直接路由移至運算子連線，請參閱 [將數位從直接路由移至運算子連線](#move-numbers-from-direct-routing-to-operator-connect)。

### <a name="acquire-numbers-for-new-teams-users"></a>取得新 Teams 使用者的數位

若要取得新 Teams 使用者的數位，請遵循下列步驟：

1. **指派電話系統授權。** 您可以從Microsoft 365 系統管理中心或使用 PowerShell 指派電話系統授權給使用者。 如需詳細資訊，請參閱 [指派 Teams 附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 將透過運算子 Connect 取得的電話號碼指派的使用者必須處於 TeamsOnly 模式。 如果您的組織處於 TeamsOnly 模式，則所有使用者都處於 TeamsOnly 模式。 若要檢查此問題，請在 Teams 系統管理中心移至 **Teams > Teams 升級設定**。 如果您的組織處於群島模式，請檢查特定使用者是否處於 TeamsOnly 模式。 移至 [ **使用者** ]，然後選取使用者帳戶。 在 [ **帳戶]** 索引標籤的 **[Teams 升級** ] 底下，共存模式應設定為 [TeamsOnly]。

3. **取得數位。** 移至您電信業者的網站以訂購及取得電話號碼。 如需電信業者網站清單，請移至 [Microsoft 365 運算子 Connect 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供您的租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱 [尋找您的 Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以取得詳細資訊。

4. **指派號碼。** 您的電信業者完成訂單後，就會將號碼上傳至您的租使用者。 您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 從 Teams 系統管理中心或使用 PowerShell 指派號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](#assign-numbers)。

> [!NOTE]
> 除了 [取得使用者的電話號碼](getting-phone-numbers-for-your-users.md)，您還可以取得電話會議) 橋接器的音訊會議 (、自動語音應答和通話佇列等服務的付費或免付費電話號碼， (也稱為服務號碼) 。 與使用者或訂閱者電話號碼相比，服務電話號碼的並行通話容量較高。 例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。 若要取得服務號碼，請連絡您的電信業者。

### <a name="emergency-addresses"></a>緊急位址

緊急位址是與數位相關聯的靜態位置。 一旦您在 Teams 系統管理中心建立緊急位址，您指派位址或稍後變更位址的方式將取決於您的電信業者。

若要將數位指派給緊急位址，您的電信業者會實作下列三種案例的其中之一：

- 運算子會將緊急位址指派給電話號碼，並允許您稍後在 Teams 系統管理中心變更。

- 電信業者不會指派位址，也可讓您將緊急位址指派給 Teams 系統管理中心的電話號碼。

- 運算子會將緊急位址指派給電話號碼，而且不允許您變更。 在此案例中，您需要連絡您的電信業者，對電話號碼及其指派的緊急位址進行變更。

如需緊急電話的詳細資訊，請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md) 和 [規劃及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>將通話方案中的號碼移至運算子連線

1. 請連絡您的電信業者，將您的號碼移轉至運算子連線。 請參閱 [Microsoft 365 運算子 Connect 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 以尋找您電信業者的網站。

2. 電信業者完成移轉訂單後，您的電信業者會將號碼上傳至您的租使用者。

3. 使用 Teams 系統管理中心或使用 PowerShell 指派運算子連線號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>將數位從直接路由移至運算子連線

若要使用內部部署或線上電話號碼從直接路由移至運算子連線，請遵循下列步驟：

#### <a name="step-1---identify-if-the-existing-direct-routing-numbers-are-assigned-online-or-on-premises"></a>步驟 1 ： 識別是否已在線上或內部部署指派現有的直接路由號碼。

執行 Teams PowerShell 模組命令，檢查使用者是否已獲指派直接路由號碼：

```PowerShell
Get-CsPhoneNumberAssignment -AssignedPstnTargetId <user> 
```

檢查是否為 `NumberType` DirectRouting。

移除現有直接路由號碼的方式，取決於號碼是內部部署還是線上指派。 若要檢查，請執行下列 Teams PowerShell 模組命令：
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```

如果 `OnPremLineUri` 已填入 E.164 電話號碼，電話號碼會被指派到內部部署，並同步處理到 Microsoft 365。

**若要移轉線上指派給運算子連線的現有直接路由號碼**，請連絡您的電信業者。 若要尋找您電信業者的網站，請參閱 [Microsoft 365 運算子 Connect 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 在同意的日期和時間，您的運算子會將您的號碼從直接路由移轉到運算子連線。

**若要將內部部署指派的直接路由號碼移轉到運** 算符連線，請執行下列商務用 Skype Server PowerShell 命令：
>[!IMPORTANT]
> 在移轉期間，電話號碼將會退出服務，因此請在開始之前先與您的運算子連線電信業者協調。

```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

移除程式生效所需的時間取決於您的設定。 若要檢查內部部署號碼是否已移除，以及變更是否已從內部部署同步至 Microsoft 365，請執行下列 Teams PowerShell 模組命令： 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool, OnPremLineURI, LineURI 
```
       
變更同步處理到 Microsoft 365 線上目錄之後，預期的輸出結果為： 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
OnPremLineURI                        : 
LineURI                              : 
```




```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

移除電話號碼最多可能需要 10 分鐘。 在少數情況下，最多可能需要 24 小時。 若要檢查電話號碼是否已移除，請執行下列 Teams PowerShell 模組命令： 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl LineUri
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>步驟 2 - 移除與使用者相關聯的線上語音路由原則

一旦取消指派號碼，請執行下列 Teams PowerShell 模組命令，移除與您的使用者相關聯的線上語音路由原則：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>步驟 3 - 取得電話號碼

移至您電信業者的網站以訂購及取得電話號碼。 若要尋找您的電信業者網站，請參閱 [Microsoft 365 運算子 Connect 目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供您的租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱 [尋找您的 Microsoft 365 租使用者識別碼](/onedrive/find-your-office-365-tenant-id) 以取得詳細資訊。

#### <a name="step-4---assign-phone-numbers"></a>步驟 4 - 指派電話號碼

您的電信業者完成訂單後，就會將號碼上傳至您的租使用者。 您可以移至 **[語音] >** 電話號碼，在 Teams 系統管理中心檢視號碼和提供者。 使用 Teams 系統管理中心或使用 PowerShell 指派運算子連線號碼給使用者。 如需詳細資訊，請參閱 [指派號碼](#assign-numbers)。

### <a name="assign-numbers"></a>指派號碼

如需如何將電話號碼指派給使用者的相關資訊，請參閱 [指派、變更或移除使用者的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>管理您的運算子

您可以從 [ **我的運算子]** 索引標籤檢視您的運算子及其狀態，並針對您的選擇進行下列變更：  

- 依國家/地區管理電信業者服務
- 暫停運算子
- 移除運算子

> [!NOTE]
> 移除貴組織或國家/地區的電信業者之前，您必須先移除指派給組織或國家/地區使用者的所有電話號碼，並連絡電信業者以釋出號碼。

## <a name="release-numbers"></a>版本號碼

若要從 Teams 系統管理中心釋出電話號碼，請移至 **[電話號碼]** 頁面並選取號碼。

- 如果電話號碼未指派給使用者，請選取 [ **發行]**。

- 如果電話號碼已指派給使用者，您將需要取消指派號碼。 選取 **[編輯**]，然後 **[移除使用者]**。 儲存變更之後，選取 **[發行]**。

## <a name="related-topics"></a>相關主題

- [規劃 Teams 自動語音應答和通話佇列](plan-auto-attendant-call-queue.md)
