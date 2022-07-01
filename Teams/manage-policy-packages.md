---
title: 在 Microsoft Teams 中管理原則套件
ms.author: mabond
author: mkbond007
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用和管理原則套件，以簡化、簡化並協助在管理使用者群組的原則時提供一致性。
ms.openlocfilehash: 7ba8f21014f892d2170684a8a4cccdfce21cee91
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2022
ms.locfileid: "66572186"
---
# <a name="manage-policy-packages-for-microsoft-teams"></a>管理 Microsoft Teams 的原則套件

Microsoft Teams 中的 原則套件 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。 我們已建置原則套件以簡化、簡化，並協助在管理貴組織中使用者群組的原則時提供一致性。  

您可以使用 [Teams 中包含的原則套件](#policy-packages-included-in-teams) ，或 [建立您自己的自訂原則套件](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心中 [原則套件] 頁面的螢幕擷取畫面。":::

您可以自訂原則套件中的原則設定，以符合使用者的需求。 當您變更套件中的原則設定時，所有獲指派該套件的使用者都會取得更新的設定。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理原則套件。

> [!NOTE]
> 這項功能暫時在公開預覽中提供給所有 Microsoft Teams 客戶使用。 若要在預覽之後取得此功能，每個使用者都需要進階通訊附加元件授權。 如需詳細資訊，請參閱 [Microsoft Teams 的進階通訊附加元件](/microsoftteams/teams-add-on-licensing/advanced-communications) (部分機器翻譯)。

## <a name="what-is-a-policy-package"></a>什麼是原則套件？

原則套件可讓您控制想要允許或限制組織中特定一組人員的 Teams 功能。 Teams 中的每個原則套件都是針對使用者角色而設計，並包含預先定義的原則和原則設定，可支援該角色的一般共同作業和通訊活動。

原則套件支援下列 Teams 原則類型：

- 訊息原則
- 會議原則
- 應用程式設定原則
- 通話原則
- 即時活動原則

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的原則套件

Teams 目前包含下列原則套件。

| 套件名稱 | 描述 |
|---------|---------|
|教育 (教育版學生)     |建立一組適用于教育學生的原則和原則設定。|
|教育版 (的高中學生)    |建立套用至學生的一組原則和原則設定。|
|教育 (中學生)     |建立一組適用于次要學生的原則和原則設定。         |
|教育版 (教師)     |建立一組套套用至教師的原則和原則設定。      |
|使用遠端學習) 教育 (國學教師    |建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|使用遠端學習 (的教育) 的高中學生    |建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|第一線管理員 |建立一組原則，並將這些設定套用至您組織中的 [前線] 管理員。 |
|第一線工作人員 |建立一組原則，並將這些設定套用至貴組織中的一線工作人員。 |
|醫療保健臨床工作者  |建立一組原則與原則設定，讓臨床工作者 (例如註冊的護士、護士長、醫生和社會工作者) 能完整存取聊天、通話、班次管理和會議。 |
|醫療保健資訊工作者  |建立一組原則與原則設定，讓資訊工作者 (例如 IT 人員、資訊人員、財務人員及法規人員) 能夠完整存取聊天、通話和會議。|
|醫療保健病房  |建立一組原則與原則設定，適用於貴醫療保健組織的病房。|
| (Teams 電話系統與通話方案套件組合的中小型企業使用者)  |建立應用程式設定原則，其中包含具有通話方案搭售體驗之 Teams 電話系統的應用程式。|
|不含 [通話方案] 搭售方案之 Teams 電話系統的中小型企業使用者 ()  |建立與中小型企業 Teams 使用者相關的應用程式設定原則， (具有通話方案搭售方案的非 Teams 電話系統) 。
|公開安全人員   |建立一組原則設定，套用至貴組織中的公用安全人員。|

> [!NOTE]
> 我們會在未來的 Teams 版本中新增更多原則套件，因此請返回查看最新資訊。  

每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。
例如，當您將教育版 (教師) 原則套件指派給學校的教師時，系統會為套件中的每個原則建立一個名為Education_Teacher的原則。

![教育 (教師) 原則套件的螢幕擷取畫面。](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自訂原則套件

自訂原則套件可讓您為組織中具有類似角色的使用者，組合自己的一組原則。 新增所需的原則類型和原則，以建立您自己的原則套件。

若要建立新的自訂原則套件：

1. 在 Microsoft Teams 系統管理中心的左窗格中，選取 [ **原則套件**]，然後按一下 [ **新增]**。

    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心之 [原則套件] 頁面上的 [新增] 按鈕螢幕擷取畫面。":::

2. 輸入套件的名稱和描述。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂原則套件的螢幕擷取畫面。":::

3. 選取要包含在套件中的原則類型和原則名稱。

4. 選取 [儲存 **]**。

## <a name="how-to-use-policy-packages"></a>如何使用原則套件

下列概述如何在貴組織中使用原則套件。

![如何使用原則套件的概觀。](media/manage-policy-packages-overview.png)

- **[檢視](#view-the-settings-of-a-policy-in-a-policy-package)**：檢視原則套件中的原則。 然後，在指派套件之前，先檢視套件中每個原則的設定。 請確定您瞭解每個設定。 決定預先定義的值是否適合您的組織，或是您需要根據組織的需求，將它們變更為更嚴格或更寬限。

    如果刪除原則，您仍然可以檢視設定，但無法變更任何設定。 當您指派原則套件時，系統會使用預先定義的設定重新建立已刪除的原則。

- **[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。

- **[指派](#assign-a-policy-package)**：指派原則套件給使用者。  

> [!NOTE]
> 您也可以在指派套件之後，變更原則套件中的原則設定。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。

以下是如何在 Microsoft Teams 系統管理中心檢視、指派及自訂原則套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>檢視原則套件中的原則設定

1. 在 Microsoft Teams 系統管理中心的左窗格中，選取 [ **原則套件**]，然後按一下套件名稱左側以選取原則套件。

2. 選取您要檢視的原則。

### <a name="customize-policies-in-a-policy-package"></a>自訂原則套件中的原則

您可以透過 [原則 **套** 件] 頁面或直接移至 Microsoft Teams 系統管理中心的原則頁面來編輯原則設定。

1. 在 Microsoft Teams 系統管理中心的左窗格中，執行下列其中一項操作：
    - 選取 **[原則套件**]，然後按一下套件名稱左邊來選取原則套件。
    - 選取原則類型。  例如，按一下 [ **訊息中心原則]**。

2. 選取您要編輯的原則。 連結至原則套件的原則名稱與原則套件相同。

3. 進行您要的變更，然後按一下 [ **儲存]**。

### <a name="assign-a-policy-package"></a>指派原則套件

您可以將原則套件指派給個別使用者、群組或一批使用者。 如需有關如何指派原則套件的詳細資訊，請參閱 [指派原則套件給使用者和群組](assign-policy-packages.md)。

## <a name="related-topics"></a>相關主題

- [指派原則套件](assign-policy-packages.md)
- [適用于教育人員的 Teams 原則套件](policy-packages-edu.md)
- [適用於醫療保健的 Teams 原則套件](policy-packages-healthcare.md)
- [適用于政府機關的 Teams 原則套件](policy-packages-gov.md)
