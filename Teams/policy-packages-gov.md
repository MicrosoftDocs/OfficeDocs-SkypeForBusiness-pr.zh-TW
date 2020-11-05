---
title: 政府團隊原則套件
author: lanachin
ms.author: v-lanac
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
description: 瞭解如何使用及管理您的政府組織的小組原則套件。
ms.openlocfilehash: 8ef632689cb52180e8fd18cf4047fb9a25150885
ms.sourcegitcommit: ee217e1d7188842c7becd19387fd421b485c3575
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2020
ms.locfileid: "48908592"
---
# <a name="teams-policy-packages-for-government"></a>政府團隊原則套件

> [!NOTE]
> 原則套件目前無法在 Microsoft 365 政府版 GCC 或 DoD 部署中使用。

## <a name="overview"></a>概觀

Microsoft 團隊中的 [原則套件](manage-policy-packages.md) 是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。 原則套件可簡化原則管理，並有助於達到一致性。 您可以自訂套件中原則的設定，以符合您的使用者需求。 當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。 您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。

原則套件根據套件預先定義下列各項原則：

- 訊息傳送
- 會議
- 通話
- App 設定
- 即時活動

團隊目前包含適用于政府的下列原則套件。

|Microsoft 團隊系統管理中心中的套件名稱|最適合用於|描述 |
|---------|---------|---------|
|公開安全官員  |政府組織中的公用安全官員  |建立一組原則與原則設定，適用于貴組織中的公用安全主管。 |
|第一線員工管理員  |第一線員工政府組織中的經理 |建立一組原則，並將這些設定套用到貴組織中的第一線員工管理員。|
|第一線員工 worker  |在您的政府組織中第一線員工工人 |建立一組原則，並將這些設定套用到貴組織中的第一線員工工作人員。|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-gov.png)

系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。 例如，當您將公用安全專員原則套件指派給貴組織中的使用者時，會針對套件中的每個原則，建立一個名為 PublicSafety_Officer 的原則。

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a>管理原則套件

### <a name="view"></a>檢視

在指派套件前，請先查看原則套件中每個原則的設定。 在 Microsoft [團隊管理中心] 的左導覽中，選取 [ **原則套件** ]，選取套件名稱，然後選取原則名稱。

決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。

### <a name="customize"></a>自訂

根據需要自訂原則套件中的原則設定，以符合貴組織的需求。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。 若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [ **編輯** ]。

請記住，在指派原則套件之後，您也可以變更套件中的原則設定。 若要深入瞭解，請參閱 [在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。 

### <a name="assign"></a>為

將原則套件指派給使用者。 如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。

#### <a name="assign-a-policy-package-to-one-or-several-users"></a>指派原則套件給一或多個使用者

若要將原則套件指派給一或多個使用者，請在 [Microsoft 團隊管理中心] 的左導覽中，移至 [ **原則套件** ]，然後選取 [ **管理使用者** ]。  

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

若要深入瞭解，請參閱 [指派原則套件](manage-policy-packages.md#assign-a-policy-package)。

如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。

#### <a name="assign-a-policy-package-to-a-group"></a>將原則套件指派給群組

**此功能是私人預覽**

[原則套件指派給群組] 可讓您將多個原則指派給使用者群組，例如安全群組或通訊群組清單。 原則指派會根據優先順序規則傳播到群組的成員。 在群組中新增或移除成員時，系統會據此更新其繼承的原則分派。 建議將此方法用於最多50000個使用者的群組，但也會搭配較大的群組使用。

若要深入瞭解，請參閱 [將原則套件指派給群組](assign-policies.md#assign-a-policy-package-to-a-group)。

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a>將原則套件指派給大型集 (批次) 使用者

使用批次原則套件指派來一次將原則套件指派給大型的使用者組。 您使用 [CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) Cmdlet 來提交一批使用者和您要指派的原則套件。 作業會處理為背景作業，並會針對每個批次產生操作 ID。

批次最多可包含5000個使用者。 您可以依物件識別碼、UPN、SIP 位址或電子郵件地址來指定使用者。 若要深入瞭解，請參閱 [將原則套件指派給一批使用者](assign-policies.md#assign-a-policy-package-to-a-batch-of-users)。

## <a name="related-topics"></a>相關主題

[在 Teams 中管理原則套件](manage-policy-packages.md)

[指派策略給小組中的使用者](assign-policies.md) 
