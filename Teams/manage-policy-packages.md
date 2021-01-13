---
title: 管理 Microsoft 團隊中的原則套件
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
description: 瞭解如何使用及管理 Microsoft 團隊中的原則套件，以簡化、簡化及協助在管理使用者群組原則時提供一致性。
ms.openlocfilehash: 62250644d29f65a9c650db0e80477eec6baf4f3d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49839459"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理 Microsoft 團隊中的原則套件

> [!NOTE]
> 此文章中所討論的其中一個功能（ [自訂原則套件](#custom-policy-packages)）目前是私人預覽。

Microsoft 團隊中的原則套件是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。 我們建立了原則套件，以簡化、簡化，並在管理組織中的使用者群組原則時提供一致性。  

您可以使用 [ [小組] 中所包含的原則套件](#policy-packages-included-in-teams) ，或 [建立您自己的自訂原則套件](#custom-policy-packages) (在私人預覽) 中。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心 [原則套件] 頁面的螢幕擷取畫面":::

您可以自訂原則套件中原則的設定，以符合您的使用者需求。 當您變更套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。 您可以使用 Microsoft 團隊系統管理中心或 PowerShell 來管理原則套件。

## <a name="what-is-a-policy-package"></a>什麼是原則套件？

[原則套件] 可讓您控制您想要允許或限制整個組織中特定人員組的小組功能。 團隊中的每個原則套件都是圍繞使用者角色來設計，包含預先定義的原則與原則設定，可支援該角色的共同作業及通訊活動。

原則套件支援下列團隊原則類型：

- 訊息原則
- 會議原則
- App 設定原則
- 通話原則
- 即時活動原則

## <a name="policy-packages-included-in-teams"></a>團隊中包含的原則套件

團隊目前包含下列原則套件。

|**套件名稱**  |**描述** |
|---------|---------|
|教育版 (高等教育學生)     |建立一組可套用至較高教育學生的原則與原則設定。|
|教育 (主要學校學生)    |建立適用于主要學生的一組原則與原則設定。|
|課程 (副學校學生)     |建立一組可套用至副學生的原則與原則設定。         |
|教育版 (教師)     |建立適用于教師的一組原則與原則設定。      |
|使用遠端學習 (主要學校老師的教育版)     |建立適用於小學教師的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|使用遠端學習) 的主要學校學生 (教育版    |建立適用於學生的一組原則，以便在使用遠端學習時將學生安全性和共同作業最大化。      |
|第一線員工管理員 |建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。 |
|第一線員工 worker |建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。 |
|醫療保健臨床工人  |建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。 |
|醫療保健資訊工作者  |建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。|
|醫療保健患者機房  |建立一組原則與原則設定，適用于您的保健組織中的患者會議室。|
|中小型企業使用者 (商務語音)  |建立應用程式設定原則，其中包含商務語音體驗的 app。|
|中小型企業使用者 (沒有商務用語音)  |建立與中小型企業團隊使用者 (非商務語音體驗) 相關的 app 設定原則。
|公開安全官員   |建立一組原則與原則設定，適用于貴組織中的公用安全主管。|

> [!NOTE]
> 我們會在未來的團隊版本中新增更多原則套件，請返回最新資訊。  

系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。
例如，當您將「教育 (教師) 原則套件指派給學校中的教師時，會針對套件中的每個原則建立名為 Education_Teacher 的原則。

![教育版 (教師) 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自訂原則套件

**這項功能在私人預覽中**

自訂原則套件可讓您將自己的一組原則與組織中相似角色的使用者捆綁。 新增您所需的原則類型和原則，建立您自己的原則套件。

若要建立新的自訂策略套件：

1. 在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，然後按一下 [ **新增**]。
    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心 [原則套件] 頁面上的 [新增] 按鈕的螢幕擷取畫面":::
2. 輸入套件的名稱和描述。
    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂策略套件的螢幕擷取畫面":::
3. 選取要包含在套件中的原則類型和原則名稱。
4. 按一下 **[儲存]**。

## <a name="how-to-use-policy-packages"></a>如何使用原則套件

下列概要說明如何在您的組織中使用原則套件。

![使用原則套件的概覽](media/manage-policy-packages-overview.png)

- [**[查看](#view-the-settings-of-a-policy-in-a-policy-package)**]：在原則套件中查看原則。 然後，在指派套件之前，先查看套件中每個原則的設定。 請務必瞭解每個設定。 決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其變更為更具限制或 lenient。

    如果刪除策略，您仍然可以查看設定，但無法變更任何設定。 當您指派原則套件時，會使用預先定義的設定來重新建立已刪除的原則。

- **[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合貴組織的需求。

- **[指派](#assign-a-policy-package)**：將原則套件指派給使用者。  

> [!NOTE]
> 您也可以在指派套件後，變更原則套件中的原則設定。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。

以下是如何在 Microsoft 團隊系統管理中心中查看、指派及自訂策略套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在原則套件中查看原則的設定

1. 在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件**]，然後按一下套件名稱左邊的，選取 [原則套件]。
2. 按一下您要查看的原則。

### <a name="customize-policies-in-a-policy-package"></a>在原則套件中自訂策略

您可以透過 [ **原則套件** ] 頁面編輯原則設定，或是直接移至 Microsoft [小組管理中心] 中的 [原則] 頁面。

1. 在 Microsoft [團隊管理中心] 的左導覽中，執行下列其中一項操作：
    - 按一下 [ **原則套件**]，然後按一下套件名稱左方，選取 [原則套件]。
    - 按一下原則類型。  例如，按一下 [ **訊息原則**]。
2. 選取您要編輯的原則。 連結至原則套件的原則與原則套件的名稱相同。
3. 進行您想要的變更，然後按一下 [ **儲存**]。

### <a name="assign-a-policy-package"></a>指派原則套件 

#### <a name="assign-a-policy-package-to-one-user"></a>指派原則套件給一個使用者

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]，然後按一下該使用者。
2. 在使用者的頁面上，按一下 [ **原則**]，然後按一下 [ **原則封裝**] 旁的 [ **編輯**]。
3. 在 [ **指派原則套件** ] 窗格中，選取您要指派的套件，然後按一下 [ **儲存**]。

#### <a name="assign-a-policy-package-to-multiple-users"></a>指派原則套件給多位使用者

1. 在 Microsoft 團隊系統管理中心的左導覽中，移至 [ **原則套件**]，然後按一下套件名稱左邊的 [原則]，選取您要指派的原則套件。
2. 按一下 [ **管理使用者**]。
3. 在 [管理使用者] 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後按一下 [新增]。 針對要新增的每一個使用者重複此步驟。
4. 完成新增使用者後，請按一下 [ **儲存**]。

#### <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

**這項功能在私人預覽中**

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。 此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。

若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>為一大組 (批) 使用者指派原則套件

使用批次原則套件指派，將原則套件一次性指派給大組使用者組。 您可以使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。

批次最多可包含 5000 個使用者。 您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。 若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="troubleshooting"></a>疑難排解

**當您指派原則套件時，收到錯誤訊息**

如果套件中的一個或多個原則未成功建立或套用，可能會發生這種情況。 將原則套件重新指派給您的使用者。 重試此操作通常會修正此問題。

## <a name="related-topics"></a>相關主題

[指派策略給小組中的使用者](assign-policies.md)

[EDU 管理員的團隊原則套件](policy-packages-edu.md)

[醫療保健的團隊原則套件](policy-packages-healthcare.md)

[政府團隊原則套件](policy-packages-gov.md)
