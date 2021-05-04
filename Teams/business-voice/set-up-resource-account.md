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
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130342"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a>步驟 4：設定商務語音資源帳戶

在 Microsoft Teams中，每個自動電話機或通話佇列都需要資源帳戶。 資源帳戶也可能被指派服務電話號碼。 這是您將電話號碼指派給自動語音機和通話佇列，讓來自Teams的來電者能夠到達自動語音機或通話佇列。

## <a name="obtain-virtual-user-licenses"></a>取得虛擬使用者授權

資源帳戶需要授權才能使用自動電話機和通話佇列。 您可以使用免費的虛擬使用者 *Microsoft 365 電話系統虛擬使用者* 授權。

1. 請Microsoft 365系統管理中心。
2. 前往 **帳單**  >  **購買服務**  >  **附加元件**  >  **查看所有附加元件產品**
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

1. 在 Teams系統管理中心中，展開 **整個組織設定**，然後按一下 [**資源帳戶**。
2. 選取 [新增 **]**。
3. 在新增 **資源帳戶窗格中** ，填寫 **顯示名稱**，然後填入 **使用者名稱**。 選擇描述性顯示名稱 ，例如「主行自動助理」，以描述資源帳戶的用途。
4. 在 **資源帳戶類型中**，選取自動 **助理**。
5. 選取 [儲存 **]**。

![資源帳戶清單的螢幕擷取畫面](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a>指派授權

建立資源帳戶之後，您需要指派一個Microsoft 365 電話系統 *- 虛擬* 使用者 *授權或電話系統* 授權。

![系統管理中心指派授權使用者介面的螢幕擷取畫面Microsoft 365螢幕擷取畫面](../media/resource-account-assign-virtual-user-license.png)

1. 在 Microsoft 365系統管理中心，前往 **使用者**  >  **活動使用者**。
2. 選取您的資源帳戶。
1. 在 "**授權與應用程式"** 選項卡的 **"授權**" 下，選取 Microsoft 365 電話系統 -**虛擬使用者**。
1. 選取 **儲存變更，** 然後 **關閉**。

## <a name="assign-a-service-number"></a>指派服務號碼

![指派服務編號使用者介面的螢幕擷取畫面](../media/resource-account-assign-phone-number.png)

1. 在 Teams系統管理中心，請前往整個 **組織設定**，然後前往 **資源帳戶**。 
1. 選取您剛剛建立的資源帳戶，然後按一下 [ **指派/取消指派**> 。
1. 在 電話 **數位類型** 下拉式下拉清單 **中，選擇** Online 。
1. 在 **[已指派的電話號碼** > 方塊中，搜尋您想要使用的號碼，然後按一下 [ **新增**。 請務必包含國家/地區代碼 (例如 **+1** 250 555 0012) 
1. 按一下 [儲存]。
    > [!NOTE]
    > 由於已選取要新增號碼的自動話務員，因此不需要選取指派給下的自動電話機。

> [!div class="nextstepaction"]
> [下一個步驟：指派電話號碼給使用者](set-up-assign-numbers.md)
