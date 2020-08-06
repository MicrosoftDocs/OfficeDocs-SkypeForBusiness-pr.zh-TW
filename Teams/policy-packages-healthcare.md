---
title: 醫療保健的團隊原則套件
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
description: 瞭解如何使用及管理您的保健組織的小組原則套件。
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578188"
---
# <a name="teams-policy-packages-for-healthcare"></a>醫療保健的團隊原則套件

## <a name="overview"></a>概觀

Microsoft 團隊中的[原則套件](manage-policy-packages.md)是預先定義的原則與原則設定的集合，您可以指派給在組織中擁有相似角色的使用者。 原則套件可簡化原則管理，並有助於達到一致性。 您可以自訂套件中原則的設定，以符合您的使用者需求。 當您變更原則套件中的原則設定時，指派給該套件的所有使用者都會取得更新的設定。 您可以使用 Microsoft [團隊系統管理中心] 或 [PowerShell] 管理 [原則套件]。

原則套件根據套件預先定義下列各項原則：

- 會議
- 即時活動
- 通話
- 傳訊
- Teams
- App 設定

團隊目前包含下列醫療保健原則封裝。

|Microsoft 團隊系統管理中心中的套件名稱|最適合用於|描述 |
|---------|---------|---------|
|醫療保健臨床工人  |您的保健組織中的臨床工作者  |建立一組原則與原則設定，提供臨床工人（例如註冊的護士、充電護士、醫生和社會員工）完整存取聊天、通話、值班管理和會議。 |
|醫療保健資訊工作者  |您的保健組織中的資訊工作者 |建立一組原則與原則設定，以提供資訊工作者，例如 IT 人員、informatics 員工、財務人員及合規性監察官，完整存取聊天、通話及會議。|
|醫療保健患者機房  |患者房間裝置|建立一組原則與原則設定，適用于您的保健組織中的患者會議室。|

![醫療保健原則套件的螢幕擷取畫面](media/policy-packages-healthcare.png)

系統會為每個個別原則指定原則套件的名稱，以便您輕鬆識別連結到原則套件的原則。 例如，當您將醫療保健臨床工人原則套件指派給您組織中的臨床醫師時，會針對套件中的每個原則，建立一個名為 Healthcare_ClinicalWorker 的原則。

![醫療保健臨床工人套件中的原則的螢幕擷取畫面](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a>管理原則套件

### <a name="view"></a>檢視

在指派套件前，請先查看原則套件中每個原則的設定。 在 Microsoft [團隊管理中心] 的左導覽中，選取 [**原則套件**]，選取套件名稱，然後選取原則名稱。

決定預先定義的值是否適合您的組織，或是否需要根據貴組織的需求將其自訂為更具限制性或 lenient。

### <a name="customize"></a>自訂

根據需要自訂原則套件中的原則設定，以符合貴組織的需求。 您對原則設定所做的任何變更都會自動套用到已指派套件的使用者。 若要編輯原則套件中原則的設定，請在 Microsoft [團隊管理中心] 中，選取原則套件，選取您要編輯的原則名稱，然後選取 [**編輯**]。

請記住，在指派原則套件之後，您也可以變更套件中的原則設定。 若要深入瞭解，請參閱[在原則套件中自訂](manage-policy-packages.md#customize-policies-in-a-policy-package)原則。 

### <a name="assign"></a>為

將原則套件指派給使用者。 若要將原則套件指派給一或多個使用者，請按一下 [**管理使用者**]。 您也可以使用 PowerShell 將原則套件指派給大量的使用者。 如需如何指派原則套件的步驟，請參閱[指派原則套件](manage-policy-packages.md#assign-a-policy-package)。

![如何在系統管理中心指派原則套件的螢幕擷取畫面](media/policy-packages-healthcare-assign.png)

如果使用者已指派策略，且稍後您指派其他原則，則最近指派的優先順序會較高。

## <a name="related-topics"></a>相關主題

[在 Teams 中管理原則套件](manage-policy-packages.md)

[指派策略給小組中的使用者](assign-policies.md)
