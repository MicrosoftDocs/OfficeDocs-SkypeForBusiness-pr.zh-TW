---
title: Microsoft 365 Phone System – 虛擬使用者授權
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
description: 瞭解如何為貴組織的資源帳戶指派免費的 Phone System–虛擬使用者授權或付費電話系統使用者授權。
ms.openlocfilehash: 8e5322ccf7e3e7ad05c499b3dbcfdac65d0dfedb
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116921"
---
# <a name="microsoft-365-phone-system--virtual-user-license"></a>Microsoft 365 Phone System – 虛擬使用者授權

擁有電話系統授權使用者的組織可以將免費的 Microsoft 365 電話系統 – 虛擬使用者授權或付費電話系統使用者授權指派給資源帳戶。 不需要通話方案。 所有自動電話機或通話佇列都需要相關聯的資源帳戶。 需要電話號碼的資源帳戶需要免費的 Microsoft 365 電話系統 - 虛擬使用者授權或付費的 Phone System 使用者授權，才能將電話號碼用於資源帳戶。

> [!TIP]
> 資源帳戶不需要授權，而資源帳戶會與巢式自動總機或未指派電話號碼的通話佇列一起使用。 請參閱下列圖表以參考： 

![虛擬使用者授權](../media/resource-account.png)

## <a name="virtual-user-license-allocation"></a>虛擬使用者授權配置

貴組織已根據整體大小配置 Microsoft 365 Phone System – 虛擬使用者授權。 任何擁有至少一個授權的組織 ，包括電話系統或已新增電話系統，都提供 25 個虛擬使用者授權，且無需付費。 當您在貴組織中新增 10 個 Phone System 使用者授權時，再新增一個 Microsoft 365 Phone System - 虛擬使用者授權即可供使用。

> [!NOTE]
> Phone System 是 Microsoft 365 和 Office 365 E1 和 E3 提供的附加元件授權。 電話系統也包含在 Microsoft 365 E5、Office 365 E5 和 Microsoft 365 商務語音授權中。

如果貴組織在建立自動電話機或通話佇列節點時，已使用可用的免費 Microsoft 365 電話系統 - 虛擬使用者授權，您仍可使用付費電話系統授權與資源帳戶。 根據縮放比例方案，大部分組織都會擁有足夠的虛擬使用者授權。 

### <a name="license-allocation-example"></a>授權配置範例

Contoso， Inc. 已購買 600 個授權，每個員工 (一個包含電話系統) 。 Contoso 已分配初始 25 加 60 個 Microsoft 365 Phone System – 虛擬使用者授權，總計 85 個。 他們的組織有 90 個通話佇列和具有電話號碼的自動電話機。 他們需要指派所有 Microsoft 365 Phone System – 虛擬使用者授權，並取得五個固定價格的電話系統授權。

Contoso 應考慮重新設計自動電話機和通話佇列系統。 如果他們使用的電話號碼較少，且巢中節點更多，而不需要電話號碼，則能簡化實現並降低成本。

## <a name="how-to-buy-microsoft-365-phone-system--virtual-user-licenses"></a>如何購買 Microsoft 365 Phone System – 虛擬使用者授權

1. 請登錄 Microsoft 365 系統管理中心。
2. 前往 **帳單**  >  **購買服務**  >  **附加元件**
3. 卷起到最後尋找 **Microsoft 365 Phone System – 虛擬使用者** 授權。 選取 **立即購買**。

> [!NOTE]
> 請記住，您仍必須  **購買授權** ，即使其成本為零。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-365-phone-system--virtual-user-license"></a>變更現有的資源帳戶以使用 Microsoft 365 電話系統 – 虛擬使用者授權

如果您決定將資源帳戶上的授權從電話系統授權切換到 Microsoft 365 電話系統 – 虛擬使用者授權：

1. 取得新的 Microsoft 365 Phone System – 虛擬使用者授權。
2. 請遵循 Microsoft 365 系統管理中心的連結步驟，將 [使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 永遠移除完整的電話系統授權，並在同一個授權活動中指派 Microsoft 365 Phone System – 虛擬使用者授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能不再如預期運作。 如果發生這種情況，我們建議您為 Microsoft 365 Phone System - 虛擬使用者授權建立新資源帳戶，並移除中斷的資源帳戶。 

## <a name="related-information"></a>相關資訊

[自動電話機和通話佇列服務更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理資源帳戶](../manage-resource-accounts.md)