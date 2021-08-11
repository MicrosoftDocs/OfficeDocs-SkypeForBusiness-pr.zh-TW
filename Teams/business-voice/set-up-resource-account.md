---
title: 設定Microsoft 365 商務語音資源帳戶
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 瞭解如何設定與自動Microsoft 365 商務語音一起使用的資源帳戶。
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb36a0f3a1327bb3b42b0148c889a05e377ccf1af80c4a3c42d51299677b9692
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54331075"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>步驟 4：設定商務語音資源帳戶

資源帳戶不會指派給任何特定使用者。 相反地，使用免費虛擬使用者授權的資源帳戶，會由 Microsoft 365。 在 Microsoft Teams中，資源帳戶會指派電話號碼，然後與自動總機和通話佇列相關聯。

將資源帳戶與自動電話機和通話佇列建立關聯，您可以新增一或多個付費電話號碼或免付費電話號碼。 例如，您可以將一個資源帳戶與付費號碼關聯到當地來電者的自動語音服務。 針對長途通話，您可以將另一個資源帳戶與免付費號碼關聯到相同的自動話務員。

本文中的各節將說明如何設定資源帳戶，然後為其指派電話號碼。 稍後，您將將資源帳戶與自動助理建立關聯。

下列影片將說明如何在系統管理中心完成Teams步驟。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a>取得虛擬使用者授權

資源帳戶需要授權才能使用自動電話機和通話佇列。 您可以使用免費的虛擬使用者 *Microsoft 365 電話系統虛擬使用者* 授權。

> [!NOTE]
> 如果您註冊了商務語音試用期，您只需要執行下列步驟。 如果您購買 Business Voice 授權，虛擬授權應該已經適用于您的帳戶。 
>
> 若要查看您是否已經有虛擬授權，請Microsoft 365全域系統管理員許可權的帳戶登入。 然後前往帳單> [您的產品](https://admin.microsoft.com/Adminportal/Home#/subscriptions)。 如果您有虛擬授權，這些授權會顯示為 Microsoft 365 電話系統 **- 虛擬使用者**。

1. 開啟 Microsoft 365 系統管理中心，然後使用全域系統管理員的使用者登入 (通常是您用來註冊帳戶Microsoft 365) 。
2. 在左側流覽窗格中，前往帳單 <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">****  >  **購買服務**</a>附加元件  >    >  **查看所有附加元件產品**。
3. 卷起到結尾以尋找Microsoft 365 電話系統 **– 虛擬使用者** 授權。 選取 **詳細** 資料，然後 **選取購買**。
4. 在授權購買頁面上，選取您想要的虛擬使用者授權數目。 針對您打算設定的每個自動電話機和通話佇列，您需要一個虛擬授權。 我們建議您至少選取五個授權，以便日後輕鬆設定更多自動電話機和通話佇列，而不需要立即購買更多授權。
5. 取消 **勾選自動指派給沒有授權的所有使用者**。
6. 選取 **現在簽出**。
7. 確認您的訂單， **選取下一** 步，然後 **下單**。

> [!NOTE]
> 請記住，您仍必須  **購買授權** ，即使其成本為零。

## <a name="create-a-resource-account"></a>建立資源帳戶

在您收到您的 Microsoft 365 電話系統 *- 虛擬使用者* 授權之後，您可以建立資源帳戶。

![新增資源帳戶使用者介面的螢幕擷取畫面](../media/resource-account-add.png)

1. 開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。
2. 在左側流覽窗格中，前往 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**全組織** 設定  >  **資源帳戶**</a>。
3. 選取 [新增 **]**。
4. 在新增 **資源帳戶窗格中** ，填寫 **顯示名稱**，然後填入 **使用者名稱**。 選擇描述性顯示名稱 ，例如「主行自動助理」，以描述資源帳戶的用途。
5. 在 **資源帳戶類型中**，選取自動 **助理**。
6. 選取 [儲存 **]**。

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a>指派授權

建立資源帳戶之後，您需要指派一個Microsoft 365 電話系統 *- 虛擬* 使用者 *授權或電話系統* 授權。

![指派授權使用者介面的螢幕擷取畫面Microsoft 365 系統管理中心](../media/resource-account-assign-virtual-user-license.png)

1. 開啟 Microsoft 365 系統管理中心，然後使用全域系統管理員的使用者登入 (通常是您用來註冊帳戶Microsoft 365) 。
1. 在左側流覽窗格中，前往使用者 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">****  >  **活動使用者**</a>。
1. 選取您的資源帳戶。
1. 在 "**授權與應用程式"** 選項卡的 **"授權**" 下，選取 Microsoft 365 電話系統 -**虛擬使用者**。
1. 選取 **儲存變更，** 然後 **關閉**。

## <a name="assign-a-service-number"></a>指派服務號碼

![指派服務編號使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

1. 開啟 Microsoft Teams系統管理中心，然後使用全域系統管理員使用者登入 (這通常是您用來註冊帳戶Microsoft 365) 。
1. 在左側流覽窗格中，前往 <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**全組織** 設定  >  **資源帳戶**</a>。
1. 選取您剛剛建立的資源帳戶，然後按一下 [ **指派/取消指派**> 。
1. 在 電話 **數位類型** 下拉式下拉清單 **中，選擇** Online 。
1. 在 **[已指派的電話號碼** > 方塊中，搜尋您想要使用的號碼，然後按一下 [ **新增**。 請務必包含國家/地區代碼 (例如 **+1** 250 555 0012) 
1. 按一下 [儲存]。

> [!div class="nextstepaction"]
> [下一個步驟：指派電話號碼給使用者](set-up-assign-numbers.md)
