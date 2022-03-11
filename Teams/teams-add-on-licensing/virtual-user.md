---
title: Microsoft Teams 電話標準 – 虛擬使用者授權
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
ms.localizationpriority: medium
ms.custom:
- Licensing
- LIL_Placement
- seo-marvel-apr2020
description: 瞭解如何為貴Teams 電話資源帳戶指派免費 Teams 電話虛擬使用者授權或付費標準使用者授權。
ms.openlocfilehash: 542d80a8cb463df01e6e232454b2454a939a457b
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435727"
---
# <a name="microsoft-teams-phone-standard--virtual-user-licenses"></a>Microsoft Teams 電話標準 – 虛擬使用者授權

具有 Teams 電話 標準版Teams 電話或具有通話方案授權使用者的組織，可以將免費的 *Microsoft Teams 電話 標準 –* 虛擬使用者授權或付費 *Teams 電話* 標準使用者授權指派給資源帳戶。 Microsoft 通話方案不一定一定 (請參閱規劃 Teams[自動](../plan-auto-attendant-call-queue.md#prerequisites)話務員和通話佇列，瞭解將通話轉接至外部電話號碼時的先決條件) 。

所有自動電話機和通話佇列都需要相關聯的資源帳戶。 需要電話號碼的資源帳戶需要免費 *Microsoft Teams 電話 標準 –* 虛擬使用者授權或付費 *Teams 電話 標準* 使用者授權，才能將電話號碼用於資源帳戶。

> [!TIP]
> 資源帳戶不需要授權，而資源帳戶會與巢式自動總機或未指派電話號碼的通話佇列一起使用。 請參閱下列圖表以參考。

:::image type="content" alt-text="虛擬使用者授權。" source="../media/resource-account.png":::

## <a name="virtual-user-license-allocation"></a>虛擬使用者授權配置

貴組織會根據Microsoft Teams 電話 *標準 – 虛擬使用者* 授權來配置。 任何擁有至少一個授權Teams 電話系統的組織，Teams 電話標準版Teams 電話通話方案授權Teams 電話有 25 個虛擬使用者授權，且無需付費。 當您在組織中新增 10 Teams 電話或 Teams 電話通話方案使用者授權時，系統就會Microsoft Teams 電話標準 *– 虛擬使用者* 授權。

> [!NOTE]
> Teams 電話通話方案Teams 電話標準版和通話方案，所有訂閱者都Microsoft 365附加Microsoft 365授權。 Teams 電話標準授權也會包含在計畫Microsoft 365 E5一部分。

如果貴組織在建立自動Microsoft Teams 電話或通話佇列節點時，已使用免費的 Microsoft Teams 電話 標準 – 虛擬使用者授權，您仍可在資源帳戶使用付費 *Teams 電話 標準* 授權。 根據縮放比例方案，大部分組織都會擁有足夠的虛擬使用者授權。

### <a name="license-allocation-example"></a>授權配置範例

Contoso， Inc. 已購買 600 個授權，電話系統 (每個員工和) 。 Contoso 會獲得初始 25+ 60 Microsoft Teams 電話 *標準 – 虛擬使用者* 授權，總計 85 個。 他們的組織有 90 個通話佇列和具有電話號碼的自動電話機。 他們需要指派所有標準 *– Microsoft Teams 電話使用者* 授權，並取得五個標準Teams 電話 *授權*。

Contoso 應考慮重新設計自動電話機和通話佇列系統。 如果他們使用的電話號碼較少，且巢中節點更多，而不需要電話號碼，則能簡化實現並降低成本。

## <a name="how-to-buy-microsoft-teams-phone-standard--virtual-user-licenses"></a>如何購買Microsoft Teams 電話標準 – 虛擬使用者授權

1. 請登錄Microsoft 365 系統管理中心。
2. 前往 **BillingPurchase** ****  >  **servicesAdd-ons**  >  。
3. 卷起到結尾，尋找 Microsoft Teams 電話 **標準 – 虛擬使用者** 授權。 選取 **立即購買**。

   > [!NOTE]
   > 請記住，您仍必須 **購買授權** ，即使其成本為零。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-standard--virtual-user-license"></a>變更現有的資源帳戶，以使用 Microsoft Teams 電話標準 – 虛擬使用者授權

如果您決定將資源帳戶上的授權從標準Teams 電話切換到 Microsoft Teams 電話 *– 虛擬使用者* 授權：**

1. 取得新的 Microsoft Teams 電話 標準 – 虛擬使用者授權。
2. 請遵循中心中的Microsoft 365 系統管理[步驟，將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 永遠 *移除標準Teams 電話* 的完整授權，並在同一個Microsoft Teams 電話活動中指派標準 *–* 虛擬使用者授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能不再如預期運作。 如果發生這種情況，建議您為標準版 *–* 虛擬使用者授權Microsoft Teams 電話新資源帳戶，並移除中斷的資源帳戶。

## <a name="related-information"></a>相關資訊

[自動電話機和通話佇列服務更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理資源帳戶](../manage-resource-accounts.md)
