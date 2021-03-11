---
title: 在 Microsoft Teams 中管理政策套件
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用及管理原則套件，以簡化、簡化及協助在管理使用者群組之策略時提供一致性。
ms.openlocfilehash: 07e2712db52d79e8db66789fe062c8ab46854e5b
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/09/2021
ms.locfileid: "50585689"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>在 Microsoft Teams 中管理政策套件

> [!NOTE]
> 本文探討的其中一項功能，自訂 [策略套件](#custom-policy-packages)目前處於私人預覽。

Microsoft Teams 中的一個策略套件是預先定義之策略和策略設定的集合，您可以指派給組織中具有類似角色的使用者。 我們建建了簡化、簡化及協助管理貴組織使用者群組之策略時一致性的套件。  

您可以使用 Teams[中包含的政策](#policy-packages-included-in-teams)套件，或在私人[](#custom-policy-packages)預覽版中 (自訂) 。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心中之政策套件頁面的螢幕擷取畫面":::

您可以自訂策略套件中之策略的設定，以滿足您的需求。 當您變更套件中之策略的設定時，指派給該套件的所有使用者會取得更新的設定。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理政策套件。

## <a name="what-is-a-policy-package"></a>什麼是政策套件？

策略套件讓您控制您想要允許或限制貴組織特定人員集合的 Teams 功能。 Teams 中每個策略套件都是以使用者角色為設計基礎，並包含預先定義且支援該角色一般共同合作和通訊活動之政策設定。

策略套件支援下列 Teams 策略類型：

- 訊息原則
- 會議原則
- 應用程式設定政策
- 通話原則
- 即時活動原則

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的政策套件

Teams 目前包含下列政策套件。

|**套件名稱**  |**描述** |
|---------|---------|
|教育 (學生)     |建立套用至高教學生一組原則與原則設定。|
|教育 (中學生)    |建立套用至主要學生的一組原則與原則設定。|
|教育 (中學生)     |建立套用至中學生的一組原則與原則設定。         |
|教育 (教師)     |建立套用至教師的一組原則與原則設定。      |
|使用 (學習工具)     |建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|使用 (學習課程的中學生)     |建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|前線管理員 |建立一組原則，並套用這些設定給貴組織的前線管理員。 |
|第一線員工 |建立一組原則，並套用這些設定給貴組織的前線工作人員。 |
|醫療保健專業人員  |建立一組政策與政策設定，讓醫療工作者 ，例如註冊的護士、護士、醫師和社交工作者，能完全存取聊天、通話、輪班管理和會議。 |
|醫療保健資訊工作者  |建立一組政策與政策設定，讓資訊工作者 ，例如 IT 人員、資訊人員、財務人員和法規遵循人員，以及完整的聊天、通話和會議存取權。|
|醫療保健病患室  |建立一組套用至醫療保健組織中病患室的一組原則與原則設定。|
|中小型企業使用者 (商務語音)  |建立包含商務語音體驗應用程式的應用程式設定政策。|
|沒有 Business Voice (的中小型企業)  |建立與中小型企業 Teams 使用者相關的應用程式設定 (非商務語音體驗) 。
|公共安全人員   |建立一組套用至貴組織中公共安全人員的政策與原則設定。|

> [!NOTE]
> 我們會在未來 Teams 版本中新增更多政策套件，因此請返回查看最新資訊。  

每一個個別策略會提供一個策略套件的名稱，好方便您識別連結至該政策套件的政策。
例如，當您將教育 (教師) 政策套件指派給學校中的教師時，會針對套件中的每個政策建立名為 Education_Teacher 的一個策略。

![教育與教師 (政策套件) 螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自訂策略套件

**這項功能在私人預覽中**

自訂策略套件可針對組織中具有類似角色的使用者，將您自己的一群組原則組合在一起。 新增所需的策略類型與策略，以建立您自己的策略套件。

若要建立新的自訂策略套件：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取 [政策 **套件**，然後按一下 [ **新增**。
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心之政策套件頁面上的新增按鈕螢幕擷取畫面":::
2. 輸入套件的名稱和描述。
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. 選取要納入套件中的策略類型和策略名稱。
4. 按一下 [儲存 **]**。

## <a name="how-to-use-policy-packages"></a>如何使用政策套件

以下概述如何在貴組織中使用政策套件。

![如何使用政策套件概觀](media/manage-policy-packages-overview.png)

- **[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在策略套件中查看策略。 然後，在指派套件之前，先查看套件中每個策略的設定。 請確定您瞭解每個設定。 決定預先定義的值是否適合貴組織，或是否需要根據貴組織的需求，將它們變更為更具限制性或寬限性。

    如果已刪除某個政策，您仍然可以查看設定，但無法變更任何設定。 當您指派該策略套件時，會使用預先定義的設定重新建立已刪除的策略。

- **[自訂](#customize-policies-in-a-policy-package)**：自訂策略套件中之策略的設定，以配合貴組織的需求。

- **[指派](#assign-a-policy-package)**：指派策略套件給使用者。  

> [!NOTE]
> 您也可以在指派套件之後，變更策略套件中之策略的設定。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。

以下是如何在 Microsoft Teams 系統管理中心中查看、指派及自訂政策套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在策略套件中查看策略的設定

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取政策 **套件**，然後按一下套件名稱左側以選取一個策略套件。
2. 按一下您想要查看的策略。

### <a name="customize-policies-in-a-policy-package"></a>自訂策略套件中的策略

您可以透過政策套件頁面或直接進入 Microsoft  Teams 系統管理中心中的政策頁面，編輯該政策設定。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，執行下列其中一項操作：
    - 按一下 **[策略套件**，然後按一下套件名稱左側以選取該策略套件。
    - 按一下該策略類型。  例如，按一下 **[傳訊策略**。
2. 選取您想要編輯的策略。 連結至策略套件之策略與策略套件的名稱相同。
3. 進行您想要的變更，然後按一下 **[儲存**。

### <a name="assign-a-policy-package"></a>指派策略套件 

#### <a name="assign-a-policy-package-to-one-user"></a>指派一個策略套件給一個使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 在使用者的頁面上，按一下 **[政策**」，然後按一下 [政策套件旁的編輯 **。**
3. 在 [ **指派策略套件窗格** > 中，選取要指派的套件，然後按一下 **[儲存**。

#### <a name="assign-a-policy-package-to-multiple-users"></a>指派一個策略套件給多個使用者

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往政策套件，然後按一下套件名稱左側，選取您想要指派的套件。
2. 按一下 **[管理使用者**。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 完成新增使用者後，請按一下 **[儲存**。

#### <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。 此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。

若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>為一大組 (批) 使用者指派原則套件

使用批次原則套件指派，將原則套件一次性指派給大組使用者組。 您可以使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。

批次最多可包含 5000 個使用者。 您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。 若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="troubleshooting"></a>疑難排解

**當您指派策略套件時收到錯誤**

如果未成功建立或套用套件中的一或多個原則，就可能會發生此情況。 將策略套件重新指派給使用者。 重試作業通常會修正此問題。

## <a name="related-topics"></a>相關主題

[在 Teams 中將原則指派給使用者](assign-policies.md)

[適用于 EDU 系統管理員的 Teams 政策套件](policy-packages-edu.md)

[醫療保健的 Teams 政策套件](policy-packages-healthcare.md)

[政府用 Teams 政策套件](policy-packages-gov.md)
