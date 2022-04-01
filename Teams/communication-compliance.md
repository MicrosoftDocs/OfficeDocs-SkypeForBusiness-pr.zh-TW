---
title: 通訊合規性Microsoft Teams
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: Learning，這是測試人員風險解決方案集的一部分，從 Microsoft Teams 的觀點 (這是 M365 通訊合規性功能的一) 。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 33a2f72307b82fa4264f264e0f98a4d0aed45ae4
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592838"
---
# <a name="communication-compliance-with-microsoft-teams"></a>通訊合規性Microsoft Teams

通訊合規性是公司內部的一Microsoft 365風險解決方案，可協助偵測、捕獲及處理貴組織中不當的郵件，協助將通訊風險降到最低。

針對 Microsoft Teams，通訊合規性可協助識別 Teams 頻道、私人[](/microsoft-365/compliance/communication-compliance-feature-reference) Teams 頻道或 1：1 和群組聊天中的下列不當內容類型：

- 令人反感、褻褻和騷擾的語言
- 成人、狂犬和 Gory 影像
- 共用敏感性資訊

有關通訊合規性以及如何為貴組織設定策略[Microsoft 365。](/microsoft-365/compliance/communication-compliance) 有關包含Microsoft 365合規性之訂閱的資訊，請參閱[內部人員風險解決方案](/microsoft-365/compliance/insider-risk-solution-overview#communication-compliance)。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>如何使用通訊合規性Microsoft Teams

通訊合規性Microsoft Teams緊密整合，有助於將貴組織的通訊風險降到最低。 在您建立第一個通訊合規性政策之後，您可以主動管理Microsoft Teams自動在通知中標記的郵件和內容。

### <a name="getting-started"></a>快速入門

在 Microsoft Teams 中開始使用通訊合規性，首先規劃及建立預先定義的[](/microsoft-365/compliance/communication-compliance-plan)或自訂的政策，以識別 Teams 頻道或 1：1 和群組中的不當使用者活動。 請記住，您必須在設定過程中設定一些[](/microsoft-365/compliance/communication-compliance-configure)許可權和基本先決條件。

Teams系統管理員可以在下列層級設定通訊合規性政策：

- **使用者層級**：此層級原則適用于個別Teams使用者，或可能適用于Teams使用者。 這些策略涵蓋這些使用者可能會以 1：1 或群組聊天傳送的郵件。 使用者聊天通訊會自動監控使用者Microsoft Teams使用者的所有位置。
- **Teams層級**：此層級原則適用于 Microsoft Teams頻道，包括私人頻道。 這些方針僅涵蓋在頻道Teams的郵件。

### <a name="report-a-concern-in-microsoft-teams"></a>在中報告Microsoft Teams

系統 *預設會* 啟用 Teams訊息中的報告關注問題選項，且可透過 Teams 系統管理中心的訊息Teams [控制](/microsoftteams/manage-teams-in-modern-portal)。 這可讓貴組織中使用者提交不當的郵件，供該政策通訊合規性審查者審查。 有關通訊合規性中使用者報告的郵件詳細資訊，請參閱 [通訊合規性政策](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy)。

![報告問題功能表。](./media/communication-compliance-report-a-concern-full-menu.png)

提交郵件供審查後，使用者會收到在 Microsoft Teams 中提交的確認。 聊天中的其他參與者不會看到此通知。

![報告問題確認。](./media/communication-compliance-report-a-concern.png)

除非您建立並指派自訂策略，否則貴組織中使用者會自動取得全域原則。 編輯全域原則中的設定，或建立並指派一或多個自訂策略來開啟或關閉此功能。 詳細資訊，請參閱[在 Teams 中管理Teams](/microsoftteams/messaging-policies-in-teams)。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>在郵件中處理不當Microsoft Teams

在您針對這些郵件已配置好您的Microsoft Teams收到通訊合規性通知之後，組織中的合規性審查者就該處理這些郵件了。 如果貴組織已啟用此功能，這也會包含使用者報告的郵件。 校閱者可以檢查通訊合規性通知，並移除已標有標Microsoft Teams。

![移除郵件中的Teams。](./media/communication-compliance-remove-teams-message.png)

移除的郵件和內容會以通知取代，讓檢視器瞭解郵件或內容已移除，以及哪些政策適用于移除。 已移除郵件或內容的寄件者也會收到移除狀態的通知，並且提供原始郵件內容，以瞭解其移除相關內容。 寄件者也可以查看適用于郵件移除的特定原則條件。

寄件者看到之策略提示範例：

![寄件者的策略提示。](./media/communication-compliance-warning-1.png)

寄件者看到之策略通知範例：

![寄件者的策略條件資訊。](./media/communication-compliance-warning-2.png)

收件者看到之策略提示範例：

![收件者的政策提示。](./media/communication-compliance-warning-3.png)