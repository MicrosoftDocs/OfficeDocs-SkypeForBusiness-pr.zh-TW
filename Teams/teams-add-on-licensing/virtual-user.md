---
title: Microsoft Teams 電話資源帳戶授權
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
description: 瞭解如何將免費的 Teams Phone 資源帳戶授權或付費Teams 電話標準方案使用者授權指派給貴組織中的資源帳戶。
ms.openlocfilehash: f8aaf7480fc228fc78879ed5905aaaf7092777ab
ms.sourcegitcommit: 6e677c7d0dfe9e380d70adaca748eea88ca95705
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/09/2022
ms.locfileid: "67298293"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話資源帳戶授權

擁有Teams 電話標準方案或具有通話方案之 Teams Phone 授權使用者的組織可以將免費 *Microsoft Teams 電話資源帳戶* 授權或付費 *Teams 電話標準方案* 使用者授權指派給資源帳戶。 不一定需要 Microsoft 通話方案 (請參閱 [規劃 Teams 自動語音應答和呼叫佇列](../plan-auto-attendant-call-queue.md#prerequisites) ，瞭解將通話移轉到外部電話號碼) 的必要條件。

所有自動語音應答和通話佇列都需要相關聯的資源帳戶。 需要電話號碼的資源帳戶需要免費 *Microsoft Teams 電話資源帳戶* 授權或付費 *Teams 電話標準方案* 使用者授權，才能將電話號碼套用至資源帳戶。

> [!TIP]
> 沒有指派電話號碼的巢狀自動語音應答或通話佇列使用的資源帳戶不需要授權。

## <a name="resource-account-license-allocation"></a>資源帳戶授權配置

您的組織Microsoft Teams 電話 *資源帳戶* 授權會根據其整體大小而配置。 擁有至少一個授權且具備 Teams 電話系統功能的任何組織，包括Teams 電話標準方案和具有通話方案授權的 Teams Phone，都有 25 個資源帳戶授權可供免費使用。 當您在貴組織中新增 10 個Teams 電話標準方案或含通話方案使用者授權的 Teams Phone 時，還有一 *個Microsoft Teams 電話資源帳戶* 授權可供使用。

> [!NOTE]
> Teams 電話標準方案和含通話方案的 Teams Phone 都是可供所有 Microsoft 365 訂閱者使用的附加元件授權。 Teams 電話標準方案授權也會包含在Microsoft 365 E5方案中。

如果貴組織在建立自動語音應答或通話佇列節點時使用免費 *Microsoft Teams 電話資源帳戶* 授權，您仍然可以使用付費 *Teams 電話標準方案* 授權搭配資源帳戶。 大部分的組織會根據縮放比例計畫擁有足夠的資源帳戶授權。

### <a name="license-allocation-example"></a>授權配置範例

Contoso， Inc. 已購買 600 個授權，其中包含電話系統 (每個員工) 一個授權。 Contoso 的初始 25 加上 60 *Microsoft Teams 電話資源帳戶* 授權，總計為 85 個。 其組織有 90 個有電話號碼的通話佇列和自動語音應答。 他們需要指派所有 *Microsoft Teams 電話資源帳戶* 授權，並取得五個一般定價 *Teams 電話標準方案* 授權。

Contoso 應該考慮重新設計自動語音應答和通話佇列系統。 如果他們使用較少的電話號碼和更不需要電話號碼的巢狀節點，則會簡化實作並降低成本。

## <a name="how-to-buy-microsoft-teams-phone-resource-account-licenses"></a>如何購買Microsoft Teams 電話資源帳戶授權

1. 登入Microsoft 365 系統管理中心。
2. 移至 **帳單**  >  **購買服務**  >  **附加元件**。
3. 捲動以尋找 **Microsoft Teams 電話資源帳戶** 授權。 選取 **[立即購買]**。

   > [!NOTE]
   > 請記住，即使授權的成本為零，您仍必須 **購買** 授權。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>將現有的資源帳戶變更為使用Microsoft Teams 電話資源帳戶授權

如果您決定將資源帳戶的授權從 *Teams 電話標準方案* 授權切換為 *Microsoft Teams 電話資源帳戶* 授權：

1. 取得新的 *Microsoft Teams 電話資源帳戶* 授權。
2. 請依照Microsoft 365 系統管理中心中的連結步驟[，將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 一律移除完整 *Teams 電話標準方案* 授權，並在相同的授權活動中指派 *Microsoft Teams 電話資源帳戶* 授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法再如預期般運作。 如果發生這種情況，建議您為 *Microsoft Teams 電話資源* 帳戶授權建立新的資源帳戶，並移除損毀的資源帳戶。

## <a name="related-information"></a>相關資訊

[自動語音應答和通話佇列服務更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理資源帳戶](../manage-resource-accounts.md)
