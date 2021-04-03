---
title: 在 Microsoft Teams 中管理原則套件
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
ms.openlocfilehash: 125c89505727e4fd4e6c18419b32dc1b99dfb67b
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/02/2021
ms.locfileid: "51583109"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>在 Microsoft Teams 中管理原則套件

> [!NOTE]
> 本文探討的其中一項功能 ， [自訂策略套件](#custom-policy-packages)，目前為私人預覽版。

Microsoft Teams 中的 原則套件 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。 我們已建立策略套件，以簡化、簡化及協助在管理貴組織使用者群組之策略時提供一致性。  

您可以使用 Teams[中包含的政策](#policy-packages-included-in-teams)套件，或在[](#custom-policy-packages)私人預覽版中 (自訂) 。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心中策略套件頁面的螢幕擷取畫面":::

您可以自訂策略套件中之策略的設定，以適合您的使用者需求。 當您變更套件中之策略的設定時，指派給該套件的所有使用者會取得更新的設定。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理原則套件。

## <a name="what-is-a-policy-package"></a>什麼是策略套件？

策略套件讓您控制您想要允許或限制貴組織特定人員集合的 Teams 功能。 Teams 中的每個策略套件都是圍繞使用者角色所設計，並包含預先定義的策略和策略設定，可支援該角色常見的共同合作與通訊活動。

策略套件支援下列 Teams 策略類型：

- 訊息原則
- 會議原則
- 應用程式設定政策
- 通話原則
- 即時活動原則

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的策略套件

Teams 目前包含下列策略套件。

|**套件名稱**  |**描述** |
|---------|---------|
|教育 (高教學生)     |建立套用至高教學生的一組原則與原則設定。|
|教育 (中學生)    |建立套用至主要學生的一組原則與原則設定。|
|教育 (中學生)     |建立套用至中學生的一組原則與原則設定。         |
|教育 (教師)     |建立套用至教師的一組原則與原則設定。      |
|使用 (遠端學習工具的小學教師)     |建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|使用 (遠端學習的中學生)     |建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|前線管理員 |建立一組原則，並套用這些設定給貴組織的前線管理員。 |
|前線工作人員 |建立一組原則，並套用這些設定給貴組織的前線員工。 |
|醫療保健臨床工作者  |建立一組原則與原則設定，讓臨床工作者 (例如註冊的護士、護士長、醫生和社會工作者) 能完整存取聊天、通話、班次管理和會議。 |
|醫療保健資訊工作者  |建立一組原則與原則設定，讓資訊工作者 (例如 IT 人員、資訊人員、財務人員及法規人員) 能夠完整存取聊天、通話和會議。|
|醫療保健病房  |建立一組原則與原則設定，適用於貴醫療保健組織的病房。|
|中小企業使用者 (商務語音)  |建立包含商務語音體驗應用程式的應用程式設定策略。|
|中小企業使用者無需商務 (語音)  |建立適用于中小型企業的應用程式設定策略 Teams 使用者 (商務語音體驗) 。
|公共安全專員   |建立一組套套用至貴組織的公安人員之原則與原則設定。|

> [!NOTE]
> 我們會在未來 Teams 版本中新增更多策略套件，因此請回來查看最新資訊。  

每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。
例如，當您將教育 (教師) 政策套件指派給學校中的教師時，會針對套件中每個策略建立名為 Education_Teacher 的策略。

![教育與教師 (政策套件) 螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自訂策略套件

**這項功能在私人預覽中**

自訂策略套件讓您針對組織中具有類似角色的使用者，將您自己的一群組原則組合在一起。 新增您所需的策略類型與策略，以建立您自己的策略套件。

若要建立新的自訂策略套件：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，選取 [ **政策套件**，然後按一下 [ **新增**。
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心之策略套件頁面上的新增按鈕螢幕擷取畫面":::
2. 輸入套件的名稱和描述。
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. 選取要納入套件中的策略類型和策略名稱。
4. 按一下 [儲存]。

## <a name="how-to-use-policy-packages"></a>如何使用策略套件

以下概述如何在貴組織中使用策略套件。

![如何使用策略套件概觀](media/manage-policy-packages-overview.png)

- **[查看](#view-the-settings-of-a-policy-in-a-policy-package)**：在策略套件中查看策略。 接著，在指派套件之前，先查看套件中每個策略的設定。 請確定您瞭解每個設定。 根據貴組織的需求，決定預先定義的值是否適合貴組織，或是否需要將它們變更為較嚴格或寬鬆。

    如果刪除一個策略，您仍然可以查看設定，但無法變更任何設定。 當您指派策略套件時，會使用預先定義的設定重新建立已刪除的策略。

- **[自訂](#customize-policies-in-a-policy-package)**：自訂策略套件中的策略設定，以配合貴組織的需求。

- **[指派](#assign-a-policy-package)**：將策略套件指派給使用者。  

> [!NOTE]
> 您也可以在指派套件之後，變更策略套件中的策略設定。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。

以下是如何在 Microsoft Teams 系統管理中心中查看、指派及自訂策略套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在策略套件中查看策略設定

1. 在 Microsoft Teams 系統管理中心的左側導航中，選取策略套件，然後按一下套件名稱左側以選取策略套件。
2. 按一下您想要查看的政策。

### <a name="customize-policies-in-a-policy-package"></a>自訂策略套件中的策略

您可以透過策略套件頁面或直接進入 Microsoft  Teams 系統管理中心中的策略頁面來編輯策略的設定。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，執行下列其中一項操作：
    - 按一下 **[策略套件**，然後按一下套件名稱左側以選取該策略套件。
    - 按一下策略類型。  例如，按一下 **[訊息策略**> 。
2. 選取您想要編輯的政策。 連結至策略套件的策略與策略套件的名稱相同。
3. 進行您想要的變更，然後按一下 [ **儲存**。

### <a name="assign-a-policy-package"></a>指派策略套件

#### <a name="assign-a-policy-package-to-one-user"></a>將策略套件指派給一個使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 在使用者頁面上，按一下 **[政策**」，然後按一下 [政策套件的 **旁邊**， **編輯>**。
3. 在 [ **指派策略套件>** 窗格中，選取您想要指派的套件，然後按一下 [ **儲存**。

#### <a name="assign-a-policy-package-to-multiple-users"></a>指派策略套件給多個使用者

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往策略套件，然後按一下套件名稱左側，選取您想要指派的政策套件。
2. 按一下 **[管理使用者**。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 新增使用者完成後，請按一下 [**儲存。**

#### <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。 此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。

若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>為一大組 (批) 使用者指派原則套件

使用批次原則套件指派，將原則套件一次性指派給大組使用者組。 您可以使用 [CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。

批次最多可包含 5000 個使用者。 您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。 若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="troubleshooting"></a>疑難排解

**當您指派策略套件時收到錯誤**

如果套件中的一或多個原則未成功建立或套用，可能會發生此情況。 將策略套件重新指派給使用者。 重試作業通常會修正此問題。

## <a name="related-topics"></a>相關主題

[指派策略套件](assign-policy-packages.md)

[適用于 EDU 系統管理員的 Teams 策略套件](policy-packages-edu.md)

[適用於醫療保健的 Teams 原則套件](policy-packages-healthcare.md)

[政府用 Teams 政策套件](policy-packages-gov.md)