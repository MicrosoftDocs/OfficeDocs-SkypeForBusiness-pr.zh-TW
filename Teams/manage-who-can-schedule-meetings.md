---
title: 管理誰可以召開立即會議及排程會議
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 瞭解如何使用 Teams 會議原則設定來控制誰可以召開即時會議及排程會議。
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466285"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>管理誰可以召開立即會議及排程會議

身為系統管理員，您可以限制哪些使用者可以在 Teams 中召開即時會議和排程會議。 基於隱私權和安全性考慮，您可能不希望特定使用者設定會議，因此此功能特別有用。

會議原則設定預設為開啟。 您可以在 Teams 系統管理中心[**會議**  >  **會議** 原則] 底下找到這些設定。

- **在頻道中立即開會**：控制使用者是否可以在頻道中啟動立即會議。
- **頻道會議排程**：控制使用者是否可以在頻道中排程會議。
- **私人會議排程**：控制使用者是否可以在 Teams 中排程私人會議。 當會議未發佈到小組中的頻道時，會議是私人的。
- **Outlook 載入** 宏：控制使用者是否可以從 Outlook 排程私人會議。 當會議未發佈到小組中的頻道時，會議是私人的。
- **立即在私人會議中開會**：控制使用者是否可以立即召開私人會議。

> [!NOTE]
> 如果會議是由代理人傳送，且代理人獲授與許可權代表另一位人員，例如主管傳送會議邀請，則會議原則設定會套用至授予主管 (許可權) 的人員。

## <a name="channel-meetings"></a>頻道會議

如果您有僅授權特定人員召開即時頻道會議和排程頻道會議的合規性要求，則您可以建立或更新會議原則來限制這些設定。 接著，您可以建立個別的原則，將原則歸結給您想要召開立即頻道會議和排程頻道會議的使用者。

1. 從 Teams 系統管理中心移至 **會議**  >  **會議原則**，然後選擇您要更新的原則。 若要建立新原則，請按一下 [ **新增]**。
1. 在 [ **一般**] 底下，切換下列專案：
    1. 如果您想要限制誰可以在頻道中召開立即會議，請將 **頻道中的 [立即開會** ] 切換為 **[關閉]**。
    1. 如果您想要限制誰可以在頻道中排程會議，請將 **[頻道會議排程** ] 切換為 **[關閉]**。
1. **按頁面** 底部的 [儲存]。

## <a name="private-meetings"></a>私人會議

如果您有僅授權特定人員召開立即私人會議和排程私人會議的合規性要求，則您可以建立或更新會議原則來限制這些設定。 接著，您可以建立個別的原則，將原則建立給您想要召開立即會議及排程私人會議的使用者。

1. 從 Teams 系統管理中心移至 **會議**  >  **會議原則**，然後選擇您要更新的原則。 若要建立新原則，請按一下 [ **新增]**。
1. 在 [ **一般**] 底下，切換下列專案：
    1. 如果您想要限制可以啟動即時私人會議的人員，請將 **[立即在私人會議中開會** ] 切換為 **[關閉]**。
    1. 如果您想要限制誰可以在頻道中排程私人會議，請將 **[私人會議排程** ] 和 **[Outlook 增益集** ] 切換為 **[關閉]**。
1. **按頁面** 底部的 [儲存]。

## <a name="turning-off-meeting-policy-settings"></a>關閉會議原則設定

關閉任一會議原則設定之後，指派給該原則的任何使用者將無法啟動或排程這類會議。 使用者先前已啟動或排程之所有現有會議的會議加入連結和會議識別碼將無法運作。  (系統會保留交談、檔案、白板、錄製、文字記錄，以及與會議相關的其他內容，使用者仍可存取這些內容。) 

如果會議原則設定已關閉，然後使用者再次開啟，則使用者先前召集的所有會議都會變成使用中，而人員可以使用會議加入連結或透過電話加入會議。

## <a name="related-topics"></a>相關主題

[變更會議到期日 - 使用者控制項](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[管理 Teams 中的會議原則](meeting-policies-overview.md)

[在 Teams 中將原則指派給使用者](policy-assignment-overview.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[Microsoft Teams 的限制和規格](/microsoftteams/limits-specifications-teams)
