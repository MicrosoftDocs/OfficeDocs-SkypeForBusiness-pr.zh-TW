---
title: 管理 Microsoft Teams 中的原則套件
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
description: 瞭解如何在 Microsoft Teams 中使用和管理原則套件，以簡化、簡化及協助在管理使用者群組的原則時提供一致性。
ms.openlocfilehash: 2fd892bc440996c7c1f000402122ad268a402ebb6bf382672813efa296de819f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54341781"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a>管理 Microsoft Teams 中的原則套件

Microsoft Teams 中的原則套件是預先定義的原則及原則設定的集合，您可以將其指派給在組織中具有類似角色的使用者。 我們已建立原則套件，以簡化、簡化及協助為組織內的使用者群組管理原則時提供一致性。  

您可以使用[Teams 所包含的原則套件](#policy-packages-included-in-teams)，也可以[建立您自己的自訂原則套件](#custom-policy-packages)。

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="系統管理中心的 [原則套件] 頁面的螢幕擷取畫面":::

您可以自訂原則套件中原則的設定，以符合使用者的需求。 當您變更套件中原則的設定時，所有指派給該套件的使用者都會取得更新的設定。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 管理原則套件。

> [!NOTE]
> 每個使用者都需要「高級通訊」附加元件，才能接收自訂原則套件指派。 如需詳細資訊，請參閱[Microsoft Teams 的高級通訊附加](/microsoftteams/teams-add-on-licensing/advanced-communications)元件。

## <a name="what-is-a-policy-package"></a>什麼是原則套件？

原則套件可讓您控制要允許或限制組織內特定人員集合的 Teams 功能。 Teams 中的每個原則套件都是圍繞使用者角色所設計，其中包含的預先定義的原則和原則設定可支援該角色的常見共同作業和通訊活動。

原則套件支援下列 Teams 原則類型：

- 郵件原則
- 會議原則
- 應用程式安裝原則
- 通話原則
- Live 事件原則

## <a name="policy-packages-included-in-teams"></a>Teams 中包含的原則套件

Teams 目前包含下列原則套件。

| 套件名稱 | 描述 |
|---------|---------|
|教育版 (高等教育學生)     |會建立一組原則和原則設定，套用到高等教育的學生。|
|教育版 (主要的學校學生)    |會建立一組原則，並將原則設定套用至主要學生。|
|教育 (第二學校的學生)     |會建立一組套用至次要學生的原則和原則設定。         |
|教育版 (教師)     |會建立一組適用于教師的原則和原則設定。      |
|使用遠端教學的教育 (主要學校老師)     |會建立一組原則，以套用至主要教師，以在使用遠端教學時最大化學生的安全性和共同作業。      |
|使用遠端教學的教育 (主要學校學生)     |會建立一組原則，套用至主要學生，以在使用遠端教學時最大化學生的安全性和共同作業。      |
|Frontline 管理員 |會建立一組原則，並將這些設定套用至組織中的 Frontline 管理員。 |
|Frontline 工作者 |會建立一組原則，並將這些設定套用至您組織中的 Frontline 工作者。 |
|醫療保健臨床工作者  |會建立一組原則和原則設定，讓臨床工作者（如已註冊的醫護人員、費用醫護人員、醫生和社會工作者）可以完全存取聊天、通話、班次管理及會議。 |
|醫療保健資訊工作者  |會建立一組原則和原則設定，以提供資訊工作者，例如 IT 人員、informatics 人員、財務人員和合規性監察官、聊天、通話和會議的完整存取權。|
|保健病人室  |會建立一組原則及原則設定，套用至您的保健組織中的病人聊天室。|
|中小企業使用者 (商務語音)  |建立包含商務語音體驗應用程式的應用程式安裝原則。|
|沒有商務語音) 的中小企業使用者 ( |建立適用于中小型企業 Teams 使用者 (非商務語音體驗) 的應用程式安裝原則。
|公開安全官員   |會建立一組原則和原則設定，以套用到您組織中的公用安全官員。|

> [!NOTE]
> 在未來的 Teams 版本中，我們將新增更多原則套件，以查看最新資訊。  

每個個別原則都會獲得原則套件的名稱，這樣您就能輕鬆識別連結到原則套件的原則。
例如，當您將教育版 (教師) 原則套件指派給學校中的教師時，會為套件中的每個原則建立名為 Education_Teacher 的原則。

![教育版 (教師) 原則套件的螢幕擷取畫面](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a>自訂原則套件

**自訂原則套件尚未可用於政府社群雲端 (GCC)**

自訂原則套件可讓您為組織中具有類似角色的使用者捆綁您自己的原則集合。 新增您所需的原則類型和原則，以建立您自己的原則套件。

若要建立新的自訂原則套件：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 [**原則套件**]，然後按一下 [**新增**]。

    :::image type="content" source="media/policy-packages-add.png" alt-text="系統管理中心的 [原則套件] 頁面上的 [新增] 按鈕的螢幕擷取畫面":::

2. 輸入套件的名稱和描述。

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="新增自訂原則套件的螢幕擷取畫面":::

3. 選取要包含在套件中的原則類型和原則名稱。

4. 按一下 **儲存**。

## <a name="how-to-use-policy-packages"></a>如何使用原則套件

下列概要說明如何在組織中使用原則套件。

![如何使用原則套件的概述](media/manage-policy-packages-overview.png)

- **[View](#view-the-settings-of-a-policy-in-a-policy-package)**：查看原則套件中的原則。 然後，在指派套件之前，先查看套件中每個原則的設定。 請務必瞭解每個設定。 決定您的組織是否適合預先定義的值，或是否需要根據組織的需求將其變更為限制性或 lenient。

    若刪除原則，您仍然可以查看設定，但您將無法變更任何設定。 當您指派原則套件時，會使用預先定義的設定重新建立已刪除的原則。

- **[自訂](#customize-policies-in-a-policy-package)**：自訂原則套件中的原則設定，以符合組織的需求。

- **[指派](#assign-a-policy-package)**：將原則套件指派給使用者。  

> [!NOTE]
> 您也可以在指派套件之後，變更原則套件中的原則設定。 您對原則設定所做的任何變更都會自動套用至已指派此套件的使用者。

以下是如何在 Microsoft Teams 系統管理中心中查看、指派及自訂原則套件的步驟。

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a>在原則套件中查看原則的設定

1. 在 Microsoft Teams 系統管理中心的左側導覽中，選取 [**原則套件**]，然後按一下套件名稱左側以選取原則套件。

2. 按一下您要查看的原則。

### <a name="customize-policies-in-a-policy-package"></a>自訂原則套件中的原則

您可以透過 [**原則套件**] 頁面，或是直接前往 Microsoft Teams 系統管理中心的 [原則] 頁面，編輯原則的設定。

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，執行下列其中一項動作：
    - 按一下 [ **原則套件**]，然後按一下套件名稱左側以選取原則套件。
    - 按一下原則類型。  例如，按一下 [ **郵件原則**]。

2. 選取您想要編輯的原則。連結至原則套件的原則會與該原則套件具有相同名稱。

3. 進行所需的變更，然後按一下 [ **儲存**]。

### <a name="assign-a-policy-package"></a>指派原則套件

您可以將原則套件指派給個別使用者、群組或使用者批次。 如需如何指派原則套件的詳細資訊，請參閱 [將原則套件指派給使用者和群組](assign-policy-packages.md)。

## <a name="related-topics"></a>相關主題

- [指派原則套件](assign-policy-packages.md)
- [EDU 系統管理員的 Teams 原則套件](policy-packages-edu.md)
- [適用于醫療保健的 Teams 原則套件](policy-packages-healthcare.md)
- [Teams 政府的原則套件](policy-packages-gov.md)
