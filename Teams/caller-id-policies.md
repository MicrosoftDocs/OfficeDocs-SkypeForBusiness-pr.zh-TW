---
title: 管理 Microsoft Teams 中的來電顯示原則。
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: roykuntz; jens
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.voice.callinglineid.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在組織中使用及管理本機號碼Microsoft Teams變更或封鎖組織中Teams使用者的本機號碼。
ms.openlocfilehash: a511e86efcaba8ec5dd81718bf768cc45fbf2ad0
ms.sourcegitcommit: 3a8bec0445cee5cd776fb1991f093a0ec4351852
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/28/2021
ms.locfileid: "60605429"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft Teams 中的來電顯示原則。

> [!NOTE]
> 若要將本機號碼設為資源帳戶電話號碼，並設定通話方名稱，請使用 Teams PowerShell 模組 2.3.1 或更高版本中的 PowerShell Cmdlet New-CsCallingLineIdentity 或 Set-CsCallingLineIdentity。  (系統管理中心目前Microsoft Teams這些選項)  

根據預設，當Teams使用者撥打 PSTN 電話時，系統Teams使用者的電話號碼。 同樣地，當 PSTN 來電者撥打Teams，PSTN 來電者的電話號碼即會顯示。

作為系統管理員，您可以使用本機號碼策略來變更或封鎖本機號碼 (也稱為電話線識別碼) 。 您可以使用本機號碼政策來顯示組織中 Teams 使用者的備用電話號碼、封鎖外發電話號碼、封鎖本機號碼，或設定通話方名稱 (CNAM) 。 例如，當使用者進行通話時，您可以變更本機號碼號碼，以顯示貴組織的主要電話號碼和公司名稱，而不是使用者的電話號碼。

您可以到系統管理中心中的 **語音** 本機號碼Microsoft Teams  >  管理本機號碼政策。 您可以使用全域 (全組織預設值) 原則，或建立並指派自訂原則。 除非您建立並指派自訂原則，否則組織中的使用者將會自動取得全域原則。

## <a name="create-a-custom-caller-id-policy"></a>建立自訂本機號碼策略

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **本機號碼政策**。
2. 按一下 [新增 **]**。 <br>
![系統管理中心中新本機號碼政策頁面的螢幕擷取畫面。](media/caller-id-policies-add-policy.png)
3. 輸入原則的名稱和描述。
4. 從這裡選擇您想要的設定：

    - **封鎖本機號碼**：開啟此設定以封鎖來電的本機號碼。
    - **重寫本機號碼規則**：開啟此設定，讓使用者在顯示號碼給來電者或不要來電者時，重寫該政策中的設定。 這表示使用者可以選擇是否要顯示本機號碼。 詳細資訊，請參閱 [使用者對外發本機號碼識別碼的控制項](./how-can-caller-id-be-used-in-your-organization.md#end-user-control-of-outbound-caller-id)。
    - **將本機號碼取代為**：選取下列其中一項，設定要顯示給使用者的本機號碼：

        - **使用者編號**：顯示使用者的號碼。 
        - **服務號碼**：可讓您將服務電話號碼設為顯示為本機號碼。
        - **匿名**：將本機號碼為匿名。

    - **以這個服務號碼取代來電** 顯示：選擇服務號碼以取代使用者的本機號碼。 如果您在 取代本機號碼中選取了 **服務號碼** ， **可以使用這個選項**。

5. 按一下 [儲存]。

## <a name="edit-a-caller-id-policy"></a>編輯本機號碼策略

您可以編輯全域原則或任何您建立的任何自訂策略。 

1. 在系統管理中心的左側導Microsoft Teams，請前往 **語音**  >  **本機號碼政策**。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 變更您想要的設定，然後按一下 [ **儲存**。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>指派自訂本機號碼策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相關主題

[New-CsCallingLineIdentity](/powershell/module/skype/new-cscallinglineidentity)

[Set-CsCallingLineIdentity](/powershell/module/skype/set-cscallinglineidentity)

[在 Teams 中將原則指派給使用者](policy-assignment-overview.md)