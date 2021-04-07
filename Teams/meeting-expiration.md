---
title: Microsoft Teams 中的會議政策與會議到期
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: 瞭解如何使用會議策略設定來控制 Microsoft Teams 中的會議到期時間。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6e8821781eab70696c9b24c8df18cc8dd0b46870
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598612"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft Teams 中的會議政策與會議到期

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概觀

[Microsoft](meeting-policies-in-teams.md) Teams 中的會議政策可用來控制貴組織中使用者是否可以開始和排程會議，以及會議參與者可針對使用者排程的會議提供的功能。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 您可以在 Microsoft Teams 系統管理中心管理會議政策，[](/powershell/module/skype/get-csteamsmeetingpolicy)或是使用 Get、New、Set、Remove、Grant -CsTeamsMeetingPolicy PowerShell Cmdlet。 [](/powershell/module/skype/new-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/remove-csteamsmeetingpolicy) [](/powershell/module/skype/grant-csteamsmeetingpolicy)

控制使用者是否可以開始和排程會議的會議策略設定也會控制使用者排程的會議到期。 當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 下列會議策略設定會決定使用者是否可以在 Teams 中開始和排程會議，本文中我們會參考這些設定。

- [允許現在在頻道中開會](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)：控制使用者是否可以在頻道中啟動即席會議。
- [允許頻道會議排程](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)：控制使用者是否可以在頻道中排程會議。
- [允許排程私人會議](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)：控制使用者是否可以在 Teams 中排程私人會議。 當會議未發佈到團隊中的頻道時，會議是私人的。
- [允許 Outlook 新增：](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)控制使用者是否能從 Outlook 排程私人會議。 當會議未發佈到團隊中的頻道時，會議是私人的。
- [允許現在在私人會議中開會](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)：控制使用者是否能啟動即席私人會議。

根據預設，這些設定為啟用狀態。 當其中任一設定關閉時，指派該策略的任何使用者都無法開始或排程該類型的新會議。 同時，會議會加入使用者先前啟動或排定到期之所有類型之所有現有會議的連結和會議 ID。

例如，如果使用者已指派會議策略，其中這些會議策略設定設定為 **開啟**，然後您關閉頻道中的立即開會設定，該使用者便無法再在頻道中啟動即席會議，而使用者先前建立之頻道的立即開會連接連結已過期。 使用者仍然可以開始和排程其他會議類型，並加入由其他人組織的會議。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>當會議加入連結和會議 ID 到期時，會發生什麼情況？

當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 當使用者嘗試透過連結或電話加入會議時，會收到一則訊息，指出會議已不再提供。 交談、檔案、白板、錄製、文字記錄及其他與會議相關的內容會保留，使用者仍可存取這些內容。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>當您開啟並關閉會議策略設定時，會發生什麼情況？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>將會議策略設定從開啟切換為關閉

當會議策略設定設為 **On** 時，指派該策略的使用者可以開始或排程該類型的會議，而且每個人都可以加入。 當您將會議策略設定切換為 **關閉** 時，指派該策略的使用者無法開始或排程該類型的新會議，而且使用者先前排程的現有會議的會議加入連結和會議 ID 已過期。

請記住，使用者仍然可以加入由其他人組織的會議。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>將會議策略設定從關閉切換到開啟

當您將會議策略設定從 **關閉** 切換到 **開啟** 時，指派該策略的使用者可以開始或排程該類型的會議。 如果會議策略設定已關閉，然後再次為使用者開啟，則使用者組織的所有先前排定的 (和過期的) 會議都變成使用中，而使用者可以使用會議加入連結或電話加入會議。  

## <a name="meeting-expiration-scenarios"></a>會議到期案例

以下摘要說明會議到期對於本文中討論之每一個會議政策設定如何運作。 

|如果您想要... |執行此  |會議加入行為  |
|---------|---------|---------|
|頻道到期會議現在由使用者啟動的會議  |在頻道 **中關閉允許開會**。|沒有人可以加入頻道會議現在由使用者啟動的會議。         |
|使用者排程的頻道會議到期   |關閉 允許 **頻道會議排程**。         |沒有人可以加入使用者排程的頻道會議。 這可防止人員加入下列專案：<ul><li>過去發生的頻道會議。</li> <li>已排程為未來的頻道會議，但尚未進行。</li><li>未來週期性頻道會議的實例。</li></ul>       |
|將使用者排程的私人會議到期    |關閉 允許 **排程私人會議**， *並* 關閉 允許 Outlook **附加元件**。          |沒有人可以加入使用者排程的私人會議。 這可防止人員加入下列專案： <ul><li>過去發生的私人會議。</li> <li>已排程為未來的私人會議，但尚未進行。</li><li>未來週期性私人會議的實例。</li></ul> 允許 **排程私人會議與** 允許 **Outlook 附加** 元件都必須關閉，使用者排程的私人會議必須到期。 如果其中一個設定關閉，另一個設定為已啟用，則現有會議的會議加入連結和會議 ID 會維持為使用中狀態，且不會過期。      |
|到期私人會議現在由使用者啟動的會議  |關閉允許 **現在在私人會議中開會。**          |現在沒有人可以加入由使用者啟動的私密會議。         |

如果您希望人員存取先前由特定使用者排程或啟動的會議，您可以：

- 開啟該使用者的會議策略設定。
- 關閉該使用者的會議策略設定，讓另一個已啟用該策略設定的使用者建立新會議以取代過期的會議。

> [!NOTE]
> 如果會議是由代理人傳送，而代理人獲授予代表另一個人傳送會議邀請的許可權 ，例如主管，會議原則設定會適用于授予許可權 (主管) 。

## <a name="related-topics"></a>相關主題

[管理 Teams 中的會議原則](meeting-policies-in-teams.md)

[將原則指派給 Teams 中的使用者](assign-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)