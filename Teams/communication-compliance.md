---
title: Microsoft 團隊的溝通合規性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 瞭解溝通合規性，從 Microsoft 小組角度來看「測試人員風險」方案解決方案集的一部分（這是 M365 通訊合規性功能的一部分）。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 01d9906044fe0ea8472cd8bb2ba8ccf247cdbeb9
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121693"
---
# <a name="communication-compliance-for-microsoft-teams"></a>Microsoft 團隊的溝通合規性

[溝通合規性] 是 Microsoft 365 中新的「測試人員-風險」方案集合的一部分，可協助您偵測、捕獲並修正組織中不適當的訊息，以協助將通訊風險降到最低。 在小組頻道或1:1 和群組聊天中，協助識別冒犯性語言與反騷擾。 您也可以設定原則，以查看是否有任何機密資訊是在小組通道或1:1 和群組聊天中共用。 如需不同類型的原則以及如何設定的詳細資訊，請參閱[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)。

## <a name="how-to-use-communication-compliance-in-teams"></a>如何在團隊中使用溝通合規性

### <a name="identify-inappropriate-messages"></a>找出不適當的訊息

如果您想要識別任何在 Microsoft 團隊（1:1、群組聊天或頻道交談）中傳送的訊息，包括冒犯性語言或反騷擾，您可以啟用原則來識別這項訊息，並採取必要步驟，例如傳送訓練資料或升級至正確的主管機構。

### <a name="identify-sensitive-or-regulatory-information"></a>找出機密或法規資訊

如果您想要掃描 Microsoft 團隊（1:1、群組聊天或頻道交談）中傳送的郵件，瞭解機密資訊或法規類型，您可以選擇支援預先定義的機密或法規類型的原則。

> [!NOTE]
> 通訊合規性不支援專用通道。

### <a name="custom-policy"></a>自訂原則

您可以使用此範本來設定特定通訊通道、個別偵測條件，以及在您的組織中監視及審查的內容量。

### <a name="custom-trainable-classifier"></a>自訂 Trainable 分類器

當某個現成的分類器不符合您的需求時，請使用 trainable 分類器。 Microsoft 365 分類器是一種工具，可讓您訓練來辨識各種類型的內容，方法是提供其範例來查看。 訓練分類器首先要提供人工挑選的範例，並正確符合類別。 然後，在處理完這些範例之後，請為其提供混合使用正和負樣本的方式來測試預測。 若要進一步瞭解此話題，請參閱[M365 文章](https://docs.microsoft.com/microsoft-365/compliance/classifier-creating-a-trainable-classifier)，以取得本主題的詳細資訊。

> [!NOTE]
> 溝通合規性現在支援 Exchange 混合式部署。

通訊合規性支援與原則相符之任何訊息的交談歷程記錄。 這會提供調查管理員的相關內容。

:::image type="content" source="media/communication-compliance-1.png" alt-text="Microsoft 團隊中的通訊合規性畫面。":::

## <a name="where-communication-policies-can-be-applied-in-teams"></a>可在團隊中套用通訊原則的位置

您可以針對在小組中傳送的訊息設定通訊合規性原則，其層級如下：

- 使用者層級：管理員可以在個別使用者層級設定原則，或將原則套用到租使用者上的所有使用者。 這只會涵蓋使用者在1:1 或群組聊天中傳送的訊息。
- 小組層次：管理員也可以在小組上設定原則。 這涵蓋該小組中該頻道所傳送的所有訊息（不支援專用通道訊息）。
