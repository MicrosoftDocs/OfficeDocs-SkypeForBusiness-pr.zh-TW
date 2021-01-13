---
title: Microsoft 團隊中的會議原則與會議到期日
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
description: 瞭解如何使用會議原則設定來控制 Microsoft 團隊中的會議到期日。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e1efb8ac21cbe669bcea3569a5e231469685a249
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827523"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>Microsoft 團隊中的會議原則與會議到期日

[!INCLUDE [preview-feature](includes/preview-feature.md)]

## <a name="overview"></a>概觀

Microsoft 團隊中的[會議原則](meeting-policies-in-teams.md)可用來控制貴組織中的使用者是否能開始並排程會議，以及由使用者排程的會議參與者可使用的功能。 您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。 您可以在 Microsoft 團隊系統管理中心中管理會議原則，或是使用 [ [取得](https://docs.microsoft.com/powershell/module/skype/get-csteamsmeetingpolicy)]、[ [新增](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy)]、[ [設定](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)]、[ [移除](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmeetingpolicy)]、 [[](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) CsTeamsMeetingPolicy] PowerShell Cmdlet。

控制使用者是否可以啟動及排程會議的會議原則設定也會控制使用者排程的會議的到期時間。 會議的會議加入連結和會議 ID 到期時，任何人都無法加入會議。 下列會議原則設定決定使用者是否可以在小組中開始和排程會議，我們會在本文中參考。

- [允許頻道](meeting-policies-in-teams.md#allow-meet-now-in-channels)中的 [立即開會]：控制使用者是否可以在頻道中啟動臨時會議。
- [[允許頻道會議排程](meeting-policies-in-teams.md#allow-channel-meeting-scheduling)]：控制使用者是否可以在頻道中排程會議。
- [允許排程私人會議](meeting-policies-in-teams.md#allow-scheduling-private-meetings)：控制使用者是否可在團隊中排程私人會議。 如果會議不是發佈至小組中的頻道，就是私人的。
- [[允許 outlook 載入于](meeting-policies-in-teams.md#allow-the-outlook-add-in)]：控制使用者是否可以從 Outlook 排程私人會議。 如果會議不是發佈至小組中的頻道，就是私人的。
- [[允許在私人會議中立即開會](meeting-policies-in-teams.md#allow-meet-now-in-private-meetings)]：控制使用者是否可以啟動臨時私人會議。

根據預設，這些設定為 [開啟]。 當這些設定都關閉時，任何指派了原則的使用者都無法啟動或排程該類型的新會議。 同時，會議會針對該類型的所有現有會議加入連結及會議 Id，該使用者先前開始或排程的到期時間。

例如，如果使用者指派了將這些會議原則設定設為 [ **開啟**] 的會議原則，然後關閉 [ **在頻道中允許立即開會** ] 設定，該使用者就不能再在頻道中開始臨時會議，也不能讓使用者先前建立的通道立即加入連結到期。 使用者仍可開始並排程其他會議類型，並加入由其他人組織的會議。

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>會議加入連結與會議 ID 到期時，會發生什麼情況？

當會議的會議加入連結和會議 ID 過期時，任何人都無法加入會議。 當使用者嘗試透過連結或手機加入會議時，他們會收到一則訊息，告訴您會議已不再提供。 您仍可保留交談、檔案、白板、錄製、記錄及其他與會議相關的內容，而且使用者仍然可以存取。

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>當您開啟並關閉會議原則設定時，會發生什麼情況？

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>將會議原則設定從 [開啟] 切換為 [關閉]

當會議原則設定設為 [ **開啟**] 時，指派原則的使用者可以開始或排程該類型的會議，而且所有人都可以加入。 當您將會議原則設定切換為 [ **關閉**] 時，指派該原則的使用者將無法啟動或排程該類型的新會議，以及該使用者先前排程之現有會議的會議加入連結及會議 id 已過期。

請記住，使用者仍然可以加入由其他人組織的會議。

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>將會議原則設定從 [關閉] 切換為 [開啟]

當您將會議原則設定從 [ **關閉** ] 切換為 [ **開啟**] 時，指派該原則的使用者可以開始或排程該類型的會議。 如果您已關閉會議原則設定，然後為使用者再次開啟會議原則設定，所有先前排定的 (及到期的) 會議都會成為使用中的會議，且使用者可以使用會議加入連結或電話加入他們。  

## <a name="meeting-expiration-scenarios"></a>會議到期案例

以下摘要說明在本文所討論的每個會議原則設定中，會議到期的運作方式。 

|如果您想要 .。。 |請這麼做  |會議加入行為  |
|---------|---------|---------|
|過期的頻道立即開會會議開始的使用者  |關閉 **頻道中的 [允許立即開會**]。|任何人都無法加入頻道 [立即開會] 由使用者開始的會議。         |
|使使用者排程的頻道會議過期   |關閉 [ **允許頻道會議排程**]。         |沒有人可以加入由使用者排程的頻道會議。 這可防止其他人加入下列專案：<ul><li>過去發生的頻道會議。</li> <li>已排程未來且尚未發生的頻道會議。</li><li>週期性頻道會議的未來實例。</li></ul>       |
|使使用者排程的私人會議過期    |關閉 [ **允許排程私人會議**] *，然後* 關閉 [ **允許 Outlook 增益集**]。          |沒有人可以加入由使用者排程的私人會議。 這可防止其他人加入下列專案： <ul><li>過去發生的私人會議。</li> <li>已排程未來且尚未發生的私人會議。</li><li>週期性私人會議的未來實例。</li></ul> 兩者都 **允許排程私人會議** ，並 **允許 Outlook 增益集** 必須關閉，才能讓使用者排程私人會議過期。 如果其中一個設定為 [關閉]，而另一個設定為 [開啟]，現有會議的會議加入連結和會議 Id 仍保持作用，且不會過期。      |
|使使用者開始的私人立即開會會議到期  |關閉 **私人會議中的 [允許立即開會**]。          |沒有人可以加入從使用者開始的私人 [立即開會] 會議。         |

如果您想要讓其他人存取先前由特定使用者排程或開始的會議，您可以：

- 開啟該使用者的會議原則設定。
- 關閉該使用者的會議原則設定，並讓已啟用原則設定的另一個使用者建立新的會議來取代過期的會議。

> [!NOTE]
> 如果您是由代理人傳送會議，誰被獲代表其他人（例如管理員）傳送會議邀請的許可權，則該會議原則設定會套用至授與管理員)  (的人員。

## <a name="related-topics"></a>相關主題

[在團隊中管理會議原則](meeting-policies-in-teams.md)

[指派策略給小組中的使用者](assign-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)