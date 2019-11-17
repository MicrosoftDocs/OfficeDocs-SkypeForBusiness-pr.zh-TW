---
title: 管理 Microsoft 團隊中的原則套件
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用及管理原則套件。
ms.openlocfilehash: ecfc6ae6fb1bb4d9632b8cd04b35dcee6d63359d
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/16/2019
ms.locfileid: "38679822"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理 Microsoft 團隊中的原則套件

Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。 我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。  

當您將原則套件指派給使用者時，會建立套件中的原則，然後您就可以自訂套件中原則的設定，以符合貴組織的需求。

## <a name="what-is-a-policy-package"></a>什麼是原則套件？

[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。 團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。

團隊目前包含下列原則套件。

|**套件名稱**  |**描述** |
|---------|---------|
|Education_Teacher 套件     |建立適用于教師的一組原則與原則設定。      |
|Education_PrimaryStudent 套件    |建立適用于主要學生的一組原則與原則設定。|
|Education_SecondaryStudent 套件    |建立一組可套用至副學生的原則與原則設定。         |
|Education_HigherEducationStudent 套件    |建立一組可套用至較高教育學生的原則與原則設定。|
|SmallMediumBusiness_BusinessVoice 套件    |建立應用程式設定原則，其中包含商務語音體驗的 app。|

> [!NOTE]
> 我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。  

系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。
例如，當您將 Education_Teacher 原則套件指派給學校中的教師時，會針對套件中的每個原則，建立一個名為 Education_Teacher 的原則。

![Education_Teacher 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a>如何使用原則套件

下列概要說明如何在您的組織中使用原則套件。

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- [**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在指派套件前，請先查看原則套件中每個原則的設定。 請確定您已瞭解每個設定，然後決定預先定義的值是否適合您的組織，或者您是否需要根據貴組織的需求將它們變更為更具限制性或 lenient。

    如果刪除策略，您仍然可以查看設定，但無法變更任何設定。 當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。

- **[指派](#assign-a-policy-package)**：將原則套件指派給使用者。 請記住，在您指派套件前，不會建立原則套件中的原則，在您指派套件之前，您可以變更套件中個別原則的設定。  

- **[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。

以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在原則套件中查看原則的設定

1. 在 Microsoft [團隊管理中心] 的左導覽中，按一下 [**原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。
2. 按一下您要查看的原則。

### <a name="assign-a-policy-package"></a>指派原則套件

#### <a name="assign-a-policy-package-to-one-user"></a>指派原則套件給一個使用者

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**使用者**]，然後按一下使用者。
2. 在使用者的頁面上，按一下 [**原則**]，然後按一下 [**原則封裝**] 旁的 [**編輯**]。
3. 在 [**指派原則套件**] 窗格中，選取您要指派的套件，然後按一下 [**儲存**]。

#### <a name="assign-a-policy-package-to-multiple-users"></a>指派原則套件給多位使用者

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [**原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。
2. 按一下 [**管理使用者**]。
3. 在 [**管理使用者**] 窗格中，依 [顯示名稱] 或 [使用者名稱] 搜尋使用者，選取名稱，然後按一下 [**新增**]。 針對您要新增的每個使用者重複此步驟。
4. 完成新增使用者後，請按一下 [**儲存**]。

### <a name="customize-policies-in-a-policy-package"></a>在原則套件中自訂策略

您可以透過 [**原則套件**] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。

1. 在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：
    - 按一下 [**原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。
    - 按一下原則類型。  例如，按一下 [**訊息原則**]。
2. 按一下您要編輯的原則。 連結至原則套件的原則與原則套件的名稱相同。
3. 進行您想要的變更，然後按一下 [**儲存**]。

## <a name="troubleshooting"></a>疑難排解

**當您指派原則套件時，收到錯誤訊息**

如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。 將原則套件重新指派給您的使用者。 重試此操作通常會修正此問題。

## <a name="related-topics"></a>相關主題

[EDU 系統管理員適用的 Microsoft 團隊原則套件](policy-packages-edu.md)
