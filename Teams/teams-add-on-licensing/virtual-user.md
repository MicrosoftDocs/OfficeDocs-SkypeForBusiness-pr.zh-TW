---
title: Microsoft 365 電話系統 – 虛擬使用者授權
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: waseemh
ms.topic: reference
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 瞭解如何為貴組織的資源帳戶電話系統虛擬使用者授權或付費電話系統使用者授權。
ms.openlocfilehash: 2481d119bd1f053f0836c57d237d34edfbf6e260d9b8be9b9f7d40033dc6282a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328938"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 電話系統 – 虛擬使用者授權

擁有授權電話系統的組織可以指派免費授權Microsoft 365 電話系統虛擬使用者授權或付費電話系統使用者授權給資源帳戶。 不需要通話方案。 所有自動電話機或通話佇列都需要相關聯的資源帳戶。 需要電話號碼的資源帳戶需要免費授權Microsoft 365 電話系統虛擬使用者授權或付費 電話系統使用者授權，才能將電話號碼用於資源帳戶。

> [!TIP]
> 資源帳戶不需要授權，而資源帳戶會與巢式自動總機或未指派電話號碼的通話佇列一起使用。 請參閱下列圖表以參考： 

![虛擬使用者授權](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>虛擬使用者授權配置

貴組織會依其整體Microsoft 365 電話系統 –虛擬使用者授權進行配置。 任何擁有至少一個授權的組織，電話系統已新增電話系統有 25 個虛擬使用者授權，且無需付費。 當您在組織中新增 10 電話系統使用者授權時，會再新增一Microsoft 365 電話系統 – 虛擬使用者授權即可供使用。

> [!NOTE]
> 電話系統附加元件授權，適用于 Microsoft 365 和 Office 365 E1 E3。 電話系統也包含在授權、Microsoft 365 E5、Office 365 E5 Microsoft 365 商務語音中。

如果貴組織在建立自動Microsoft 365 電話系統或通話佇列節點時，會使用可用的免費授權 -虛擬使用者授權，您仍可在資源帳戶電話付費的 電話 系統授權。 根據縮放比例方案，大部分組織都會擁有足夠的虛擬使用者授權。 

### <a name="license-allocation-example"></a>授權配置範例

Contoso， Inc. 已購買 600 個授權，每個電話系統 (一個授權) 。 Contoso 會獲得初始 25+ 60 Microsoft 365 電話系統 – 虛擬使用者授權，總計 85 個。 他們的組織有 90 個通話佇列和具有電話號碼的自動電話機。 他們需要指派所有授權Microsoft 365 電話系統虛擬使用者授權，並取得五個固定價格電話系統授權。

Contoso 應考慮重新設計自動電話機和通話佇列系統。 如果他們使用的電話號碼較少，且巢中節點更多，而不需要電話號碼，則能簡化實現並降低成本。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>如何購買Microsoft 365 電話系統 – 虛擬使用者授權

1. 請登錄Microsoft 365 系統管理中心。
2. 前往 **帳單**  >  **購買服務**  >  **附加元件**
3. 卷起到結尾以尋找Microsoft 365 電話系統 **– 虛擬使用者** 授權。 選取 **立即購買**。

> [!NOTE]
> 請記住，您仍必須  **購買授權** ，即使其成本為零。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>將現有的資源帳戶變更為使用 Microsoft 365 電話系統 – 虛擬使用者授權

如果您決定將資源帳戶上的授權從 電話系統切換到 Microsoft 365 電話系統 – 虛擬使用者授權：

1. 取得新的 Microsoft 365 電話系統 – 虛擬使用者授權。
2. 請遵循中心中的Microsoft 365 系統管理步驟[，將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 永遠移除完整的授權電話系統，並在同一Microsoft 365 電話系統活動中指派虛擬使用者授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能不再如預期運作。 如果發生此情況，建議您為虛擬使用者Microsoft 365 電話系統建立新資源帳戶，並移除中斷的資源帳戶。 

## <a name="related-information"></a>相關資訊

[自動電話機和通話佇列服務更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理資源帳戶](../manage-resource-accounts.md)