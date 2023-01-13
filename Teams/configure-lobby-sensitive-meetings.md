---
title: 針對敏感性會議設定 Microsoft Teams 會議大廳
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ''
audience: admin
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- m365solution-compliantmeetings
- m365initiative-meetings
- highpri
appliesto:
- Microsoft Teams
description: 瞭解如何使用系統管理原則、敏感度標籤和會議範本，設定 Teams 會議大廳來加強敏感性會議的安全性。
ms.openlocfilehash: 1905bc337f0260e86b2351da5015b8e1ba641bf4
ms.sourcegitcommit: ca4d1011f3d62af203145431f0b19065ad81601b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/13/2023
ms.locfileid: "69800147"
---
# <a name="configure-the-microsoft-teams-meeting-lobby-for-sensitive-meetings"></a>針對敏感性會議設定 Microsoft Teams 會議大廳

[!INCLUDE[Teams Premium ECM](includes/teams-premium-ecm.md)]

會議大廳是一項工具，您可以用來確保不適當的人員不會獲准參加會議。 會議召集人在大廳等候不同類型的參與者，可以檢查他們，並確定是否適合他們參加會議。

根據預設，貴組織中的人員和 [來賓](guest-access.md) 會直接獲准參加會議，而來自受信任網域和匿名參與者的參與者必須在大廳等候，會議召集人才能獲准參加。 會議召集人可以針對他們建立的每個會議變更此預設設定。

大廳和其他相關設定可以由 Teams 系統管理員控制，方法是使用會議原則、會議範本和敏感度標籤來自訂不同使用者和不同類型的會議體驗。

下表列出可協助您管理貴組織大廳體驗以及設定位置的功能。

|設定|管理員原則|敏感度標籤|範本|會議召集人|
|:------|:----------:|:---------------:|:------:|:---------------:|
|當撥入式來電者加入或離開時宣告|否|否|是|是|
|匿名使用者和撥入式來電者可以開始會議|是|否|否|否|
|匿名使用者可以加入會議|是|否|否|否|
|撥入人員可以略過大廳|是|是|是|是|
|誰可以略過大廳|是|是|是|是|

如需如何使用範本和敏感度標籤來設定會議設定的相關資訊，請參閱 [Microsoft Teams 中的自訂會議範本概觀](custom-meeting-templates-overview.md) 和 [使用敏感度標籤來保護行事曆專案、Teams 會議和聊天](/microsoft-365/compliance/sensitivity-labels-meetings)。

> [!Note]
> 敏感度標籤和自訂會議範本中的會議設定需要Teams 進階版。

## <a name="lobby-settings-for-different-types-of-meetings"></a>不同類型會議的大廳設定

下列設定適用于可以略過大廳的人員：

- 任何人
- 組織中的人員、信任的組織和來賓
- 組織中的人員和來賓
- 組織中的人員
- 人員受邀者
- 召集人和共同召集人

雖然會議召集人通常會選擇要用於每個會議的設定，但您可以使用會議範本或敏感度標籤強制執行特定設定。

如果貴組織要求組織外部人員不參加特定類型的會議，請考慮一個會議範本，該範本只允許貴組織中的人員略過大廳。 這可確保意外受邀或傳送會議連結的組織外部人員無法直接加入會議。

如果貴組織有共用高度機密資訊的會議，而且您必須確定只有特定人員出席，請考慮使用會議範本或敏感度標籤，只允許會議召集人略過大廳。 這可確保召集人可以檢查每位內送參與者，以確保他們應該參與會議。 這也可防止會議開始，直到召集人加入為止。

對於一般機密會議，請考慮使用 **人員受邀者** 選項。 這可確保沒有會議邀請的人員 (包含轉寄的邀請，) 進入大廳。  (會議召集人也可以在建立會議時防止轉寄。) 

如需一起使用會議範本和敏感度標籤的相關資訊，請參閱 [搭配使用 Teams 會議範本、敏感度標籤和系統管理原則來進行敏感性會議](meeting-templates-sensitivity-labels-policies.md)。

### <a name="attendees-calling-in-by-phone"></a>出席者透過電話撥入

根據預設，使用電話撥入的出席者會進入大廳。 系統管理員可以變更此預設值， **讓撥入式使用者可以略過大廳** 系統管理員會議原則。 若要強制開啟或關閉此設定，您必須使用會議範本或敏感度標籤。

如果您想要允許來電者略過大廳，會議召集人可以控制此設定，或者您可以透過會議範本或敏感度標籤強制執行這項設定。

#### <a name="join-and-leave-notifications"></a>加入和離開通知

會議召集人可以選擇讓出席者加入或離開會議時，透過電話宣佈撥入。 如果您想要確保特定類型的會議會念出電話出席者，您可以使用會議範本強制執行此設定。

## <a name="meeting-with-anonymous-participants"></a>與匿名參與者開會

除非您允許所有人略過大廳，否則匿名參與者必須經過大廳才能參加會議。 然後，會議召集人就可以決定是否允許這些參與者參加。

如果貴組織完全不允許匿名參與者加入會議，您可以關閉 **匿名使用者可以在** Teams 系統管理中心加入會議設定。 如需詳細資訊，請參閱 [管理 Microsoft Teams 中的會議設定](/microsoftteams/meeting-settings-in-teams)。

如果您的組織中有特定群組，例如行銷，需要與匿名參與者組織會議，而研究等其他群組則不應該組織會議，您可以使用 Teams 會議原則來設定不同群組的匿名會議加入。  (您必須開啟 **匿名使用者可以加入** 上述的會議設定，此功能才能正常運作。) 如需詳細資料，請參閱 [會議原則設定 - 參與者&來賓](/microsoftteams/meeting-policies-participants-and-guests)。

## <a name="related-topics"></a>相關主題

[設定具有三層保護層級的 Teams 會議](configure-meetings-three-tiers-protection.md)

[在 Microsoft Teams 中管理外部會議和聊天](/microsoftteams/manage-external-access)
