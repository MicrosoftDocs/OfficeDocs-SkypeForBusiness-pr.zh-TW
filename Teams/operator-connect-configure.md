---
title: 設定運算子連線
author: cazawideh
ms.author: czawideh
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
ms.openlocfilehash: aa31a954bb36369417f408734fa3b1622e101e69
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384161"
---
# <a name="configure-operator-connect"></a>設定運算子連線

本文將說明如何設定運算子連線。 在安裝運算子連線，請務必閱讀運算子方案連線，以瞭解[](operator-connect-plan.md)先決條件和授權的資訊。

## <a name="enable-an-operator"></a>啟用運算子

您可以在系統管理中心啟用、編輯及移除Teams運算子。 在左側流覽窗格中，前往語音> **運算子**。

若要啟用運算子：

1. **選擇運算子。** 在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。 然後選取您想要啟用的運算子。  

2. **選取國家/地區。** 在 **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。

3. **提供連絡人資訊** 您的連絡人資訊 ，包括您的全名和電子郵件地址，會自動與您的接線員共用。 您可以稍後變更這項資訊。 此外，您需要提供公司規模，而且您可以選擇提供電話號碼。 運算子會使用這項資訊來與您聯繫，以進一步瞭解運算子連線。

4. 接受資料傳輸通知。

5. **新增運算子。** 選取 **新增為運算子** 以儲存。

## <a name="set-up-phone-numbers"></a>設定電話號碼

您設定電話號碼的方式取決於您要設定新使用者的電話號碼，或移動 Microsoft 通話方案或直接路由的現有號碼。

- 如果您需要取得新使用者的電話號碼，請參閱取得新[使用者Teams號碼](#acquire-numbers-for-new-teams-users)。

- 如果您想要將現有的號碼從通話方案移至運算子連線，請參閱將號碼從通話方案移至[運算子](#move-numbers-from-calling-plans-to-operator-connect)連線。

- 如果您想要將現有號碼從直接路由移至運算子連線，請參閱將數位從直接路由移至[運算子](#move-numbers-from-direct-routing-to-operator-connect)連線。

### <a name="acquire-numbers-for-new-teams-users"></a>取得新使用者Teams號碼

若要取得新使用者Teams號碼，請遵循下列步驟：

1. **指派授權電話系統授權。** 您可以指派授權電話系統授權給使用者，Microsoft 365 系統管理中心 PowerShell。 詳細資訊請參閱指派[Teams附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 使用 Operator 連線取得的電話號碼的使用者必須位於 TeamsOnly 模式。 如果貴組織是 TeamsOnly 模式，則所有使用者都使用 TeamsOnly 模式。 若要檢查這項功能，請Teams系統管理中心，前往Teams > Teams **設定**。 如果貴組織是群島模式，請檢查特定使用者是否位於 TeamsOnly 模式。 前往 **使用者並** 選取使用者帳戶。 在帳戶 **選項卡** 的 Teams **，** 共存模式應該設定為 'TeamsOnly'。

3. **取得數位。** 請前往您的接線員網站訂購並取得電話號碼。 若要查看運算子網站清單，請前往 Microsoft 365[運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找Microsoft 365[租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。

4. **指派數位。** 您的運算子完成訂單後，就會將號碼上傳至您的租使用者。 您可以在系統管理中心查看號碼Teams提供者，> 電話 **號碼**。 從系統管理中心Teams或 PowerShell 指派號碼給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

> [!NOTE]
> 除了忘記使用者 [](getting-phone-numbers-for-your-users.md)的電話號碼之外，您還可以取得電話或免付費電話號碼服務，例如會議橋接器) 的音訊會議 (、自動語音電話和通話佇列 (也稱為服務號碼) 。 服務電話號碼的並行通話容量高於使用者或訂閱者電話號碼。 例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。 若要取得服務號碼，請與您的接線員聯繫。

### <a name="emergency-addresses"></a>緊急位址

緊急位址是一個與數位相關聯的靜態位置。 一旦在系統管理中心Teams緊急位址，您指派位址或稍後變更位址，將取決於您的運算子。

若要將號碼指派給緊急位址，您的運算子會執行三種案例之一：

- 接線員會指派緊急位址給電話號碼，讓您稍後在系統管理中心Teams位址。

- 接線員不會指派位址，而且可讓您將緊急位址指派給系統管理中心Teams電話號碼。

- 接線員會指派緊急位址給電話號碼，而且不允許您變更。 在這種情況下，您必須與您的接線員聯繫，以變更電話號碼及其指定的緊急位址。

有關緊急電話詳細資訊，請參閱 [管理緊急電話](what-are-emergency-locations-addresses-and-call-routing.md) 和 [規劃及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>將號碼從通話方案移至運算子連線

1. 請與您的接線員聯繫，將號碼連線。 請參閱[Microsoft 365運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)以尋找您的運算子網站。

2. 您的接線員完成移移訂單之後，您可以取消為使用者的通話方案電話號碼進行分配，並移除通話方案授權。 然後，您的運算子可以將數位上傳到您的租使用者。

3. 使用 連線系統管理中心或 PowerShell 將運算子Teams號碼指派給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>將數位從直接路由移至運算子連線

若要將號碼從直接路由移至運算子連線，您的運算子上傳至租使用者的現有直接路由號碼必須從指派的使用者中移除。 接著，將號碼移連線運算子之後，您可以重新指派號碼給使用者。 若要使用內部部署或線上連線從直接路由移至運算子，請遵循下列步驟：

>[!IMPORTANT]
> 電話號碼在移移期間將會無法使用，因此在開始之前，請與接線連線接線員協調。

#### <a name="step-1---remove-existing-direct-routing-numbers"></a>步驟 1 - 移除現有的直接路由號碼。

您移除現有直接路由號碼的方式取決於該號碼是指派于內部部署還是線上。 若要檢查，請執行下列命令：
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```

如果 `OnPremLineUriManuallySet` 已設定 `False` `LineUri` 為且填上 E.164 電話號碼，電話號碼會指派至內部部署，並同步處理Office 365。
    
**若要移除指派于內部部署的直接路由號碼，請** 執行下列命令：
    
```PowerShell
Set-CsUser -Identity <user> -LineURI $null 
```

移除生效所花的時間取決於您的組配置。 若要檢查內部部署號碼是否已被移除且變更已同步，請執行下列 PowerShell 命令： 
    
```PowerShell
Get-CsOnlineUser -Identity <user> | fl RegistrarPool,OnPreLineURIManuallySet, OnPremLineURI, LineURI 
```
       
變更同步到線上Office 365之後，預期輸出為： 
       
 ```console
RegistrarPool                        : pool.infra.lync.com
 OnPremLineURIManuallySet             : True
 OnPremLineURI                        : 
LineURI                              : 
```

<br> **若要移除線上指派的現有線上直接路由號碼，請** 執行下列 PowerShell 命令：


```PowerShell
Remove-CsPhoneNumberAssignment -Identity <user> -PhoneNumber <pn> -PhoneNumberType DirectRouting
```

移除電話號碼最多可能需要 10 分鐘。 在少數情況下，最多可能需要 24 小時。 若要檢查內部部署號碼是否已被移除且變更已同步，請執行下列 PowerShell 命令： 


```PowerShell
Get-CsOnlineUser -Identity <user> | fl Number
```

#### <a name="step-2---remove-the-online-voice-routing-policy-associated-with-your-user"></a>步驟 2 - 移除與使用者相關聯的線上語音路由策略

取消分配號碼後，請執行下列 PowerShell 命令，移除與使用者相關聯的線上語音路由策略：

```PowerShell
Grant-CsOnlineVoiceRoutingPolicy -Identity <user> -PolicyName $Null
```

#### <a name="step-3---acquire-phone-numbers"></a>步驟 3 - 取得電話號碼

請前往您的接線員網站訂購並取得電話號碼。 若要尋找您的運算子網站，請參閱 Microsoft 365[運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找Microsoft 365[租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。

#### <a name="step-4---assign-phone-numbers"></a>步驟 4 - 指派電話號碼

您的運算子完成訂單後，就會將號碼上傳至您的租使用者。 您可以在系統管理中心查看號碼Teams提供者，> 電話 **號碼**。 使用 連線系統管理中心或 PowerShell 將運算子指派給使用者Teams運算子。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

### <a name="assign-numbers"></a>指派數位

若要瞭解如何指派電話號碼給使用者，請參閱指派、變更或移除使用者 [的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>管理運算子

在 " **我的運算子"** 選項卡中，您可以查看您的運算子及其狀態，並變更您的選取範圍：  

- 根據國家/地區管理運算子服務
- 暫停運算子
- 移除運算子

> [!NOTE]
> 在從貴組織或國家/地區移除接線員之前，您必須移除指派給組織或國家/地區使用者的所有電話號碼，並請聯絡接線員以釋出號碼。

## <a name="release-numbers"></a>發行編號

若要從系統管理中心Teams電話號碼，請前往 電話 **號碼頁面，** 然後選取號碼。

- 如果電話號碼未指派給使用者，請 **選取發行。**

- 如果電話號碼是指派給使用者，您必須取消指派號碼。 選取 **編輯**，然後 **移除使用者**。 儲存變更之後， **請選取發行**。

## <a name="related-topics"></a>相關主題

- [規劃自動Teams和通話佇列](plan-auto-attendant-call-queue.md)
