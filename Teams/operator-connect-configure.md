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
ms.openlocfilehash: 47ed8fc4f8ca36a1d987456ff393a1b771c6fb10
ms.sourcegitcommit: e7f6125d348b6f14eeba28e09d5f1975ad4fde69
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/09/2021
ms.locfileid: "60249675"
---
# <a name="configure-operator-connect"></a>設定運算子連線

本文將說明如何設定運算子連線。 在安裝運算子連線，請務必閱讀運算子連線，以瞭解[](operator-connect-plan.md)先決條件和授權的資訊。

## <a name="enable-an-operator"></a>啟用運算子

您可以在系統管理中心啟用、編輯及移除Teams運算子。 在左側流覽窗格中，前往 **Voice > 運算子**。

若要啟用運算子：

1. **選擇運算子。** 在 " **所有運算子"** 的 Tab 中，根據地區或服務篩選可用的運算子，以尋找適合您語音需求的運算子。 然後選取您想要啟用的運算子。  

2. **選取國家/地區。** 在 **運算子設定** 下，選取您想要使用所選運算子啟用的國家/地區。

3. **提供連絡人資訊** 您的連絡人資訊 ，包括您的全名和電子郵件地址，會自動與您的接線員共用。 您可以稍後變更這項資訊。 此外，您需要提供公司規模，而且您可以選擇提供電話號碼。 運算子會使用這項資訊來與您聯繫，以進一步瞭解運算子連線。

4. 接受資料傳輸通知。

5. **新增運算子。** 選取 **新增為我的運算子** 以儲存。

## <a name="set-up-phone-numbers"></a>設定電話號碼

您設定電話號碼的方式取決於您要設定新使用者的電話號碼，或移動 Microsoft 通話方案或直接路由的現有號碼。

- 如果您需要取得新使用者的電話號碼，請參閱取得新[使用者Teams號碼](#acquire-numbers-for-new-teams-users)。

- 如果您想要將現有的號碼從通話方案移至運算子連線，請參閱將號碼從通話方案移至[運算子連線。](#move-numbers-from-calling-plans-to-operator-connect)

- 如果您想要將現有號碼從直接路由移至運算子連線，請參閱將數位從直接路由移至[運算子連線。](#move-numbers-from-direct-routing-to-operator-connect)

### <a name="acquire-numbers-for-new-teams-users"></a>取得新使用者Teams號碼

若要取得新使用者Teams號碼，請遵循下列步驟：

1. **指派授權電話系統授權。** 您可以指派授權電話系統授權給使用者，Microsoft 365 系統管理中心 PowerShell。 詳細資訊請參閱指派[Teams附加元件授權給使用者](teams-add-on-licensing/assign-teams-add-on-licenses.md)。

2. 使用 Operator 連線取得的電話號碼的使用者必須位於 TeamsOnly 模式。 如果貴組織是 TeamsOnly 模式，則所有使用者都使用 TeamsOnly 模式。 若要檢查這項功能，Teams系統管理中心，請前往整個組織設定 **> Teams升級**。 如果貴組織是群島模式，請檢查特定使用者是否位於 TeamsOnly 模式。 前往使用者 **並** 選取使用者帳戶。 在帳戶 **選項卡** 的 **Teams，** 共存模式應該設定為 'TeamsOnly'。

3. **取得數位。** 請前往您的接線員網站訂購及取得電話號碼。 若要查看運算子網站清單，請前往 Microsoft 365[運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找[Microsoft 365租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。

4. **指派數位。** 您的接線員完成訂單後，就會將號碼上傳至您的租使用者。 您可以在系統管理中心查看號碼和提供者Teams到 **Voice > 電話號碼**。 從系統管理中心Teams或使用 PowerShell 將號碼指派給使用者。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

> [!NOTE]
> 除了為使用者 [](getting-phone-numbers-for-your-users.md)取得電話號碼之外，您還可以取得電話或免付費電話號碼，例如會議橋接器) 的音訊會議 (、自動語音電話和通話佇列 (也稱為服務號碼) 。 服務電話號碼的並行通話容量高於使用者或訂閱者電話號碼。 例如，服務號碼可以同時處理數百個通話，而使用者的電話號碼只能同時處理幾個通話。 若要取得服務號碼，請與您的接線員聯繫。

### <a name="emergency-addresses"></a>緊急位址

緊急位址是一個與數位相關聯的靜態位置。 一旦在系統管理中心Teams緊急位址，您指派位址或稍後變更位址，將取決於您的運算子。

若要將號碼指派給緊急位址，您的運算子會執行三種案例之一：

- 接線員會指派緊急位址給電話號碼，讓您稍後在系統管理中心Teams位址。

- 接線員不會指派位址，而且可讓您將緊急位址指派給系統管理中心Teams電話號碼。

- 接線員會指派緊急位址給電話號碼，而且不允許您變更。 在這種情況下，您必須與您的接線員聯繫，以變更電話號碼及其指定的緊急位址。

有關緊急電話詳細資訊，請參閱 [管理緊急](what-are-emergency-locations-addresses-and-call-routing.md) 電話和 [規劃及設定動態緊急電話](configure-dynamic-emergency-calling.md)。

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a>將號碼從通話方案移至運算子連線

1. 請與您的接線員聯繫，將號碼連線。 請參閱[Microsoft 365運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)尋找您的運算子網站。

2. 您的接線員完成移移訂單之後，您可以取消為使用者的通話方案電話號碼進行分配，並移除通話方案授權。 然後，您的運算子可以將數位上傳到您的租使用者。

3. 使用系統連線或 PowerShell 將運算子指派給使用者Teams運算子。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

### <a name="move-numbers-from-direct-routing-to-operator-connect"></a>將數位從直接路由移至運算子連線

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

3. 請前往您的接線員網站訂購及取得電話號碼。 若要尋找您的運算子網站，請參閱 Microsoft 365[運算子連線目錄](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory)。 您必須提供租使用者識別碼。 如果您不知道您的租使用者識別碼，請參閱尋找[Microsoft 365租使用者識別碼](/onedrive/find-your-office-365-tenant-id)以瞭解更多資訊。

4. 您的接線員完成訂單後，就會將號碼上傳至您的租使用者。 您可以在系統管理中心查看號碼和提供者Teams到 **Voice > 電話號碼**。 使用系統連線或 PowerShell 將運算子指派給使用者Teams運算子。 詳細資訊，請參閱指派 [數位](#assign-numbers)。

### <a name="assign-numbers"></a>指派數位

若要瞭解如何指派電話號碼給使用者，請參閱指派、變更或移除使用者 [的電話號碼](assign-change-or-remove-a-phone-number-for-a-user.md)。

## <a name="manage-your-operators"></a>管理運算子

在 " **我的運算子"** 選項卡中，您可以查看運算子及其狀態，並變更您的選取範圍：  

- 根據國家/地區管理運算子服務
- 暫停運算子
- 移除運算子

> [!NOTE]
> 在將接線員從貴組織或國家/地區移除之前，您必須移除指派給組織或國家/地區使用者的所有電話號碼，並請聯絡接線員以釋出號碼。

## <a name="release-numbers"></a>發行編號

若要從系統管理中心Teams電話號碼，請前往 電話 **號碼頁面**，然後選取號碼。

- 如果電話號碼未指派給使用者，請選取 **發行**。

- 如果電話號碼是指派給使用者，您必須取消指派號碼。 選取 **編輯**，然後 **移除使用者**。 儲存變更之後， **請選取** 發行 。

## <a name="related-topics"></a>相關主題

- [規劃自動Teams和通話佇列](plan-auto-attendant-call-queue.md)
