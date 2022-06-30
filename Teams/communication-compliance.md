---
title: Microsoft Teams 的通訊合規性
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: anwara
description: 從 Microsoft Teams 的觀點瞭解測試人員風險解決方案集的一部分，瞭解通訊合規性 (這是 M365 通訊合規性功能) 的一部分。
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b96108f3bf548475cd19822967ba4e484fb26703
ms.sourcegitcommit: b383b309dbdf9caac7ad7e4a94df8d89016dc485
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/29/2022
ms.locfileid: "66551200"
---
# <a name="communication-compliance-with-microsoft-teams"></a>Microsoft Teams 的通訊合規性

Microsoft Purview 通訊合規性是 Microsoft 365 中的測試人員風險解決方案，可協助您偵測、擷取及處理組織中的不當訊息，以協助將通訊風險降到最低。

對於 Microsoft Teams，通訊合規性可協助識別 Teams 頻道、私人 Teams 頻道或 1 對 1 和群組聊天中 [下列類型的](/microsoft-365/compliance/communication-compliance-feature-reference) 不當內容：

- 令人反感、不當和騷擾的語言
- 成人、活潑和 Gory 影像
- 共用機密資訊

如需有關通訊合規性以及如何為組織設定原則的詳細資訊，請參閱 [瞭解通訊合規性](/microsoft-365/compliance/communication-compliance)。

## <a name="how-to-use-communication-compliance-in-microsoft-teams"></a>如何在 Microsoft Teams 中使用通訊合規性

通訊合規性與 Microsoft Teams 緊密整合，有助於將貴組織中的通訊風險降到最低。 在您設定第一個通訊合規性原則之後，您可以主動管理不當的 Microsoft Teams 訊息和自動在警示中標幟的內容。

### <a name="getting-started"></a>快速入門

開始使用 Microsoft Teams 中的通訊合規性，從 [規劃](/microsoft-365/compliance/communication-compliance-plan) 並建立預先定義或自訂的原則開始著手，以識別 Teams 頻道或 1 對 1 和群組中的不當使用者活動。 請記住，您需要在設定程式中 [設定](/microsoft-365/compliance/communication-compliance-configure) 一些許可權和基本先決條件。

Teams 系統管理員可以在下列層級設定通訊合規性原則：

- **使用者層級**：此層級的原則適用于個別的 Teams 使用者，或可能套用至貴組織中的所有 Teams 使用者。 這些原則涵蓋這些使用者可能會在一對一或群組聊天中傳送的訊息。 使用者的聊天通訊會在使用者所屬的所有 Microsoft Teams 上自動受到監視。
- **Teams 層級**：此層級的原則適用于 Microsoft Teams 頻道，包括私人頻道。 這些原則僅涵蓋在 Teams 頻道中傳送的訊息。

### <a name="report-a-concern-in-microsoft-teams"></a>在 Microsoft Teams 中回報疑慮

>[!NOTE]
>適用于授權和使用 [通訊合規性](/microsoft-365/compliance/communication-compliance-configure#subscriptions-and-licensing) 與 Microsoft Teams 之組織的使用者回報訊息可用性，于 2022 年 5 月啟動。 此功能將于 2022 年 8 月 31 日之前提供給所有已授權且使用通訊合規性的組織使用，到 2022 年 7 月為止。 對於在 2022 年 7 月之後開始使用通訊合規性的組織，使用者回報的訊息原則可用性可能需要最多 30 天的時間，從您的授權日期起至首次使用通訊合規性。

Teams 個人和群組聊天訊息的 [ *回報關注* ] 選項預設為啟用，可透過 Teams 系統管理 [中心的 Teams](/microsoftteams/manage-teams-in-modern-portal)訊息原則加以控制。 這可讓貴組織中的使用者提交不適當的內部聊天訊息，供通訊合規性檢閱者檢閱原則。 如需有關通訊合規性中使用者回報訊息的詳細資訊，請參閱 [通訊合規性原則](/microsoft-365/compliance/communication-compliance-policies#user-reported-messages-policy)。

![回報疑慮功能表。](./media/communication-compliance-report-a-concern-full-menu.png)

提交訊息供檢閱後，使用者會在 Microsoft Teams 中收到提交者的確認。 聊天中的其他參與者不會看到此通知。

![回報疑慮確認。](./media/communication-compliance-report-a-concern.png)

除非您建立並指派自訂原則，否則貴組織中的使用者會自動取得全域原則。 編輯全域原則中的設定，或建立並指派一或多個自訂原則來開啟或關閉此功能。 如需詳細資訊，請參閱 [管理 Teams 中的訊息原則](/microsoftteams/messaging-policies-in-teams)。

### <a name="act-on-inappropriate-messages-in-microsoft-teams"></a>在 Microsoft Teams 中對不當訊息採取行動

在您設定原則並收到 Microsoft Teams 訊息的通訊合規性警示之後，組織中的合規性檢閱者就可以對這些訊息採取行動。 如果您的組織已啟用，這也會包含使用者回報的訊息。 檢閱者可檢閱 Microsoft Teams 中的通訊合規性警示，並從檢視中移除已標幟的訊息，協助保護貴組織安全。

![移除 Teams 中的訊息。](./media/communication-compliance-remove-teams-message.png)

已移除的郵件和內容會取代為檢視者的通知，以說明郵件或內容已移除，以及移除原則。 已移除郵件或內容的寄件者也會收到移除狀態的通知，並提供與其移除相關內容的原始郵件內容。 寄件者也可以檢視移除郵件時所適用的特定原則條件。

寄件者看到的原則提示範例：

![寄件者的原則提示。](./media/communication-compliance-warning-1.png)

寄件者看到的原則通知範例：

![寄件者的原則條件資訊。](./media/communication-compliance-warning-2.png)

收件者看到的原則提示範例：

![收件者的原則提示。](./media/communication-compliance-warning-3.png)