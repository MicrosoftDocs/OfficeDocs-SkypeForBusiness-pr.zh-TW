---
title: 適用於教育界管理員的 Microsoft Teams 原則套件
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: prkuch
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用及管理原則套件。
ms.openlocfilehash: a06e32d72f4bd82b1db6b74e32312c113a1d7086
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837343"
---
# <a name="microsoft-teams-policy-packages-for-edu-admins"></a>適用於教育界管理員的 Microsoft Teams 原則套件

Microsoft 團隊中的原則套件會收集預先定義的原則與原則設定，您可以指派給擁有機構中相似角色的使用者。 原則套件可簡化、簡化及協助在管理原則時提供一致性。 在正常做法中，您會為每位使用者指派一個原則套件，並視需要重新定義每個套件中的原則，以符合該使用者群組的需求。 當您更新套件中的設定時，指派給該套件的所有使用者都會變更為大量更新。

一般的教育機構都有許多不同的使用者類型，視學生的年齡與成熟度而定。 例如，您可能會想要讓教職員和教職員擁有 Microsoft 團隊的完整存取權，但想要為學生限制 Microsoft 團隊功能，以鼓勵安全且專注的學習環境。 您可以使用 [原則套件]，根據學校群組中不同 cohorts 的需求來調整設定。

## <a name="what-is-a-policy-package"></a>什麼是原則套件？

[原則套件] 可讓您控制 Microsoft 團隊功能，以允許或限制 Microsoft 團隊針對貴組織中的特定人員組使用。 每個原則套件都是圍繞使用者角色來設計，其中包含支援該角色典型活動的預先定義原則與原則設定。

原則套件的預先定義原則：
- 傳訊
- 會議
- App 設定
- 通話
- 即時活動

Microsoft 團隊目前包含下列原則套件：

|[Microsoft 團隊系統管理中心] 中列出的套件名稱 |最適合用於  |說明 |
|:--- |:--- |:--- |
|Education_Teacher| 教育版與員工| 使用這組原則與原則設定，可讓您組織內的教師與員工在 Microsoft 團隊中授與聊天、通話和會議的完整存取權。 |
|Education_PrimaryStudent | 主要的學校老學生  | 較年輕、貴機構內主要的學校較舊學生可能需要 Microsoft 團隊中的更多限制。 使用這組原則與原則設定來限制會議建立與管理、聊天管理和私人通話等功能。 |
|Education_SecondaryStudent| 副學校過時學生 | 您機構中的次要學校過時學生可能需要 Microsoft 團隊中的更多限制。 使用這組原則與原則設定來限制會議建立與管理、聊天管理和私人通話等功能。 |
|Education_HigherEducationStudent | 高等教育學生 | 您 intuition 內的高等教育學生可能需要較少的學生限制，但可能建議您一些限制。 您可以使用這組原則與原則設定，授與您組織內的聊天、通話及會議的存取權，但要限制學生與外部參與者的搭配使用 Microsoft 團隊的方式。 |
|||

每個個別原則都會得到原則套件的名稱，這樣您就能輕鬆識別連結至原則套件的原則。 例如，當您將 Education_Teacher 原則套件指派給學校中的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。

![Education_Teacher 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

> [!NOTE]
> 如果您認為教師與管理支援人員需要不同的原則，您可以重新調整現有套件的用途：找出您目前沒有使用的套件，並將設定變更為適合該群組。 您可能必須向自己發出記事，讓哪個群組擁有哪個套件，但這只是重新調整套件用途的唯一障礙。

## <a name="why-use-policy-packages"></a>為什麼要使用原則套件

如果您的機構有成百上千個或甚至上千個的使用者，您可能會問自己：「為什麼要花時間指派一個套件或其他人給所有使用者？」

將套件指派給數百個使用者是管理時間的投資，不會有任何問題。 投資的重要事項是，他們會隨著時間而不是立即支付。

在教學環境中，有許多擁有相同或相似角色的使用者。 當您以相同的方式管理使用者體驗時，您可以花更少的時間進行工作。 套件會將機構中各種角色專用的一組原則組成群組。 擁有相同授權，但角色不同的使用者，可以根據其角色指派相關的原則，這比調整個別使用者的原則更有效率。

當您將機構中的所有使用者分成群組，並已套用套件時，只要針對指派給套件的所有使用者變更套件設定一次。 您可以在將使用者指派給套件之前或之後，選擇微調套件內的原則。

請參閱[在 Microsoft 團隊中管理原則套件](manage-policy-packages.md)，以取得指派單一使用者套件的逐步指導方針、將套件成批指派給多達20個使用者，以及管理和更新連結至每個套件的原則。
