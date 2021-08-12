---
title: Teams政府政策套件
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用及管理Teams組織的政策套件。
ms.openlocfilehash: d9c229e9795a9e93caed37832baf0b03ef58c47305f41d2961420eea485bc608
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54316989"
---
# <a name="teams-policy-packages-for-government"></a>Teams政府政策套件

> [!NOTE]
> 在政府部署或 DoD 部署Microsoft 365提供GCC套件。

## <a name="overview"></a>概觀

Microsoft Teams 中的 [原則套件](manage-policy-packages.md) 是預先定義的原則和原則設定的集合，您可以將之指派給組織中具有類似角色的使用者。 原則套件可簡化原則管理，並有助於達到一致性。 您可以自訂套件中的原則之設定，以符合使用者的需求。 當您變更原則套件中的原則設定時，指派給該套件的所有使用者會取得更新的設定。 您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來管理原則套件。

以下項目的預先定義原則之原則套件，依套件而訂：

- 訊息傳送
- 會議
- 通話
- 應用程式設定
- 即時活動

Teams目前包含下列政府政策套件。

|Microsoft Teams 系統管理中心所列的套件名稱|最適合用於|描述 |
|---------|---------|---------|
|公共安全專員  |貴政府組織的公開安全人員  |建立一組套套用至貴組織的公開安全人員之原則與原則設定。 |
|前線管理員  |您政府組織的前線管理員 |建立一組原則，並套用這些設定給貴組織的前線管理員。|
|前線工作人員  |您政府組織的前線工作人員 |建立一組原則，並套用這些設定給貴組織的前線工作人員。|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

每個個別原則都會被賦予原則套件的名稱，以便輕鬆識別連結至原則套件的原則。 例如，當您將公用安全人員政策套件指派給貴組織的使用者時，會針對套件中的每個PublicSafety_Officer建立名為 PublicSafety_Officer 的策略。

![醫療保健臨床工作者套件中的原則螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>管理原則套件

### <a name="view"></a>檢視

在指派套件之前，請查看原則套件中每個原則的設定。 在 Microsoft Teams 系統管理中心的左側流覽中，選取 **[原則套件]**，選取套件名稱，然後選取原則名稱。

决定預先定義的值是否適合貴組織，或者您是否需要根據組織的需求將它們自訂為更嚴格或更寬鬆的值。

### <a name="customize"></a>自訂

視需要自訂原則套件中的原則設定，以符合貴組織的需求。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。 要編輯原則套件中原則的設定，請在 Microsoft Teams 系統管理中心，選取該原則套件，選取要編輯的原則名稱，然後選取 **[編輯]**。

請記住，您可以在指派原則套件之後變更套件中的原則設定。 若要深入了解，請參閱 [自訂原則套件中的原則](manage-policy-packages.md#customize-policies-in-a-policy-package)。 

### <a name="assign"></a>指派

將原則套件指派給使用者。如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。

> [!NOTE]
> 每位使用者都需要 [進階通訊] 附加元件，才能接收自訂原則套件指派。 如需詳細資訊，請參閱 [Microsoft Teams 的進階通訊附加元件](/microsoftteams/teams-add-on-licensing/advanced-communications) (部分機器翻譯)。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>將原則套件指派給一或多個使用者

若要將原則套件指派給一或多個使用者，請在 Microsoft Teams 系統管理中心的左側流覽窗格中，移至 **原則套件**，然後選取 **管理使用者**。  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

若要深入了解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。

如果使用者已獲指派原則，後來您指派不同的原則，則會優先處理最新的指派。

#### <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

**這項功能在私人預覽中**

透過向群組指派原則套件，可以將多個原則指派給一組使用者，例如安全性群組或通訊群組。 原則指派將根據優先順序規則傳播到群組成員。 在群組中新增或移除成員時，系統會相應地更新其繼承的原則指派。 此方法推薦用於最多 50000 個使用者的群組，但也適用於較大的群組。

若要深入了解，請參閱 [將原則套件指派到群組](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>為一大組 (批) 使用者指派原則套件

使用批次原則套件指派，將原則套件一次性指派給大組使用者組。 您可以使用 [CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 系統會將工作處理為背景作業，並為每個批次產生作業識別碼。

批次最多可包含 5000 個使用者。 您可以使用使用者的物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。 若要深入了解，請參閱 [將原則套件指派到一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="related-topics"></a>相關主題

[在 Teams 中管理原則套件](manage-policy-packages.md)

[指派策略套件給使用者和群組](assign-policy-packages.md)
