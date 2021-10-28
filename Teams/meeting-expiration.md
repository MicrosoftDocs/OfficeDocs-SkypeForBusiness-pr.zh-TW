---
title: 會議政策與會議到期Microsoft Teams
author: cichur
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej
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
description: 瞭解如何使用會議策略設定來控制會議Microsoft Teams。
ms.openlocfilehash: 578fbefc6b3321be0b7397019172d3ddd40c3d0d
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605419"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>會議政策與會議到期Microsoft Teams

[會議Microsoft Teams](meeting-policies-overview.md)用來控制貴組織中使用者是否可以開始和排程會議，以及會議參與者對於使用者排程的會議可用的功能。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 您可以在系統管理中心Microsoft Teams使用 Get、New、Set、Remove、Grant [ ](/powershell/module/skype/new-csteamsmeetingpolicy)-CsTeamsMeetingPolicy PowerShell Cmdlet 來管理會議政策。 [](/powershell/module/skype/get-csteamsmeetingpolicy) [](/powershell/module/skype/set-csteamsmeetingpolicy) [](/powershell/module/skype/remove-csteamsmeetingpolicy) [](/powershell/module/skype/grant-csteamsmeetingpolicy)

控制使用者是否可以開始和排程會議，以及控制使用者排程的會議到期的會議策略設定。 當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 下列會議策略設定會決定使用者是否可以在 Teams 中開始和排程Teams。 本文討論會議設定。

- [允許現在在頻道中開會](meeting-policies-in-teams-general.md#allow-meet-now-in-channels)：控制使用者是否可以在頻道中啟動即席會議。
- [允許頻道會議排程](meeting-policies-in-teams-general.md#allow-channel-meeting-scheduling)：控制使用者是否可以在頻道中排程會議。
- [允許排程私人會議](meeting-policies-in-teams-general.md#allow-scheduling-private-meetings)：控制使用者是否可以在 Teams。 當會議未發佈到小組中的頻道時，會議是私人的。
- [允許Outlook](meeting-policies-in-teams-general.md#allow-the-outlook-add-in)：控制使用者是否可以從 Outlook 排程私人Outlook。 當會議未發佈到小組中的頻道時，會議是私人的。
- [允許現在在私人會議中開會](meeting-policies-in-teams-general.md#allow-meet-now-in-private-meetings)：控制使用者是否能啟動即席私人會議。

根據預設，這些設定為啟用狀態。 當其中任一設定關閉時，指派該策略的任何使用者無法開始或排程該類型的新會議。 同時，會議會加入使用者先前啟動或排定到期之所有類型之所有現有會議的連結和會議 ID。

例如，如果使用者已指派會議策略，其中這些會議策略設定設定為 **開啟**，然後您關閉頻道中的立即開會設定，該使用者就無法再在頻道中啟動即席會議，而使用者先前建立的會議現在加入連結的頻道已過期。 使用者仍然可以開始和排程其他會議類型，並加入由其他人組織的會議。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>當會議加入連結和會議 ID 到期時，會發生什麼情況？

當會議加入連結和會議 ID 到期時，沒有人可以加入會議。 當使用者嘗試透過連結或電話加入會議時，會收到一則訊息，指出會議已不再提供。 交談、檔案、白板、錄製、文字記錄及其他與會議相關的內容會保留，使用者仍然可以存取這些內容。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>當您開啟並關閉會議策略設定時，會發生什麼情況？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>將會議策略設定從開啟切換為關閉

當會議策略設定設為 **On** 時，指派該策略的使用者可以開始或排程該類型的會議，而且每個人都可以加入。 當您將會議策略設定切換為 **關閉** 時，指派該策略的使用者無法開始或排程該類型的新會議，而且使用者先前排定的現有會議的會議加入連結和會議 ID 已過期。

請記住，使用者仍然可以加入由其他人組織的會議。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>將會議策略設定從關閉切換到開啟

當您將會議策略設定從 **關閉** 切換到 **開啟** 時，指派該策略的使用者可以開始或排程該類型的會議。 如果會議策略設定已關閉，然後使用者再次開啟，則使用者組織的所有先前排定的 (和過期的) 會議都變成使用中，而人員可以使用會議加入連結或電話加入會議。  

## <a name="meeting-expiration-scenarios"></a>會議到期案例

以下是本文中討論之每一個會議策略設定的會議到期運作方式摘要。

|如果您想要...&nbsp;&nbsp; |執行此&nbsp;&nbsp;&nbsp;&nbsp;  |會議加入行為&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|到期私人會議現在由使用者啟動的會議&nbsp;&nbsp;|關閉允許 **現在在私人會議中開會。**&nbsp;&nbsp;|現在沒有人可以 **加入由使用者** 啟動的私密會議。|
|將使用者排程的私人會議到期&nbsp;&nbsp;|關閉 允許 **排程私人會議**_，並_ 關閉 允許 **Outlook附加元件**。 &nbsp;&nbsp;|沒有人可以加入使用者排程的私人會議。 這可防止人員加入下列會議：<ul><li>過去發生的私人會議。</li><li>已排程為未來的私人會議，但尚未進行。</li><li>未來的週期性私人會議實例。</li></ul><br>允許 **排程私人會議** 與允許Outlook **必須** 關閉，使用者排程的私人會議必須關閉。 如果其中一個設定關閉，另一個設定為已啟用，則現有會議的會議加入連結和會議 ID 會維持為使用中狀態，且不會過期。|
|頻道到期 **開會現在** 由使用者開始的會議&nbsp;&nbsp;|關閉頻道 **中的允許會議**_，並關閉_ 允許 **頻道會議排程**。&nbsp;&nbsp;|沒有人可以加入頻道 **會議現在** 由使用者啟動的會議。|
|使用者排程的頻道會議到期&nbsp;&nbsp;|關閉 允許 **頻道會議排程**。&nbsp;&nbsp;|沒有人可以加入使用者排程的頻道會議。 這可防止人員加入下列會議：<ul><li>過去發生的頻道會議。</li><li>已排程為未來的頻道會議，但尚未進行。</li><li>未來週期性頻道會議的實例。</li></ul>|

如果您希望人員存取先前由特定使用者排程或啟動的會議，您可以：

- 開啟該使用者的會議策略設定。
- 關閉該使用者的會議策略設定，讓另一個已啟用該策略設定的使用者建立新會議以取代過期的會議。

> [!NOTE]
> 如果會議是由代理人傳送，而代理人獲派代表另一個人傳送會議邀請的許可權 ，例如主管，會議原則設定會適用于授予許可權 (主管) 。

## <a name="related-topics"></a>相關主題

[管理 Teams 中的會議原則](meeting-policies-overview.md)

[將原則指派給 Teams 中的使用者](policy-assignment-overview.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)
