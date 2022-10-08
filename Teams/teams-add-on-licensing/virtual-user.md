---
title: Microsoft Teams 電話資源帳戶授權
author: DaniEASmith
ms.author: danismith
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
- admindeeplinkMAC
description: 瞭解如何為貴組織中的自動語音應答和通話佇列指派Microsoft Teams 電話資源帳戶授權給資源帳戶。
ms.openlocfilehash: bba516249ec1b30e0361e2f9a6be003343f9c892
ms.sourcegitcommit: 6e85f3f70f8488ab827ac352c0f324b6dfd4b856
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/04/2022
ms.locfileid: "68377361"
---
# <a name="microsoft-teams-phone-resource-account-licenses"></a>Microsoft Teams 電話資源帳戶授權

在 Microsoft Teams 中，所有自動語音應答和通話佇列都需要相關聯的資源帳戶。 每個資源帳戶都必須指派 **Microsoft Teams 電話資源帳戶** 授權，以確保系統正確識別並正常運作，*不論是否要指派電話號碼給資源帳戶*。 訂閱包含 Teams Phone 的組織，會自動設定特定數量的 **Teams Phone 資源帳戶** 授權，且無需額外付費。  除非您想要能夠使用該資源帳戶撥出，否則不需要 Microsoft 通話方案。 如需詳細資訊，請參閱 [規劃 Teams 自動語音應答和通話佇列](../plan-auto-attendant-call-queue.md#prerequisites)。

> [!NOTE]
> 之前，只有在指派電話號碼給資源帳戶時，才需要 Teams **電話資源帳戶** 授權 (稱為 **虛擬使用者** 授權) 。 現在，所有資源帳戶都必須指派 **Teams 電話資源帳戶** 授權，不論是否獲指派電話號碼。 此外，請勿將 **Teams 電話標準方案** 授權指派給資源帳戶。 如果您目前已使用 **Teams 電話標準方案** 授權設定資源帳戶，您必須切換到 **Teams Phone 資源帳戶** 授權，如下所述。
 

## <a name="resource-account-license-allocation"></a>資源帳戶授權配置

貴組織會根據其整體大小配置 **Teams Phone 資源帳戶** 授權。 擁有電話系統功能訂閱的任何組織，例如 **Teams 電話標準方案** 和含 **通話方案授權的 Teams Phone**，皆可免費配置 25 個 **Teams 電話資源帳戶** 授權。 

針對貴組織中每 10 個 **Teams 電話標準方案** 或 **含通話方案的 Teams Phone** 使用者授權，還有一個 **Teams 電話資源帳戶** 授權可供使用。  根據此縮放比例計畫，大部分的組織都會擁有足夠的 **Teams 電話資源帳戶** 授權。 如果需要更多 **Teams 電話資源帳戶** 授權，您可以透過 Microsoft 客戶代表購買超出標準配置的更多 **Teams Phone 資源帳戶** 授權。

### <a name="license-allocation-example"></a>授權配置範例

Contoso， Inc. 已購買 600 個授權，其中包含電話系統 (每個員工) 一個授權。 Contoso 的初始 25 加上 60 個 **Teams 電話資源帳戶** 授權，總計 85 個。 其組織有 90 個通話佇列和自動語音應答。 他們需要指派所有 **Teams 電話資源帳戶** 授權，並購買五個額外的 **Teams 電話資源帳戶** 授權。 

## <a name="how-to-obtain-microsoft-teams-phone-resource-account-licenses"></a>如何取得Microsoft Teams 電話資源帳戶授權

1. 登入[Microsoft 365 系統管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)。
2. 移至 **帳單**  >  [**購買服務**](https://go.microsoft.com/fwlink/p/?linkid=868433)  >  **附加元件**。
3. 捲動以尋找 **Microsoft Teams 電話資源帳戶** 授權。 選取 **[立即購買]**。

   > [!NOTE]
   > 請記住，即使您在配置範圍內，即使授權的成本為零，您仍必須 **購買** 授權。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>將現有的資源帳戶變更為使用Microsoft Teams 電話資源帳戶授權

如果您有使用 **Teams 電話標準方案** 授權的現有資源帳戶，您必須切換到 **Teams Phone 資源帳戶** 授權：

1. 取得新的 **Teams Phone 資源帳戶** 授權。
2. 請依照Microsoft 365 系統管理中心中的連結步驟[，將使用者移至不同的訂閱](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)。

> [!WARNING]
> 一律移除 **Teams 電話標準方案** 授權，並在相同的授權活動中指派 **Teams 電話資源帳戶** 授權。 如果您移除舊授權、儲存帳戶變更、新增授權，然後再次儲存帳戶設定，資源帳戶可能無法如預期般運作，例如貴組織的自動語音應答和通話佇列無法運作。
>
> 如果發生這種情況，建議您使用 **Teams Phone 資源帳戶** 授權建立新的資源帳戶，並移除損毀的資源帳戶。

## <a name="related-information"></a>相關資訊

[自動語音應答和通話佇列服務更新](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Auto-Attendant-and-Call-Queues-Service-Update/ba-p/564521)

[在 Microsoft Teams 中管理資源帳戶](../manage-resource-accounts.md)
