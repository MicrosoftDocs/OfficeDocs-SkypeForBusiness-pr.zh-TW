---
title: 管理 Microsoft 團隊中的呼叫者識別碼原則
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark
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
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何在 Microsoft 團隊中使用和管理本機號碼原則，以變更或封鎖貴組織中的小組使用者本機號碼。
ms.openlocfilehash: c3eabc5a9e906fd514ce92864e08cad5015f6670
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255526"
---
# <a name="manage-caller-id-policies-in-microsoft-teams"></a>管理 Microsoft 團隊中的呼叫者識別碼原則

>[!INCLUDE [new-feature-teams-admin-center](includes/new-feature-teams-admin-center.md)]

做為管理員，您可以在 Microsoft 團隊中使用本機號碼原則來變更或封鎖本機號碼 (也稱為呼叫線路識別碼) 。 根據預設，當使用者撥打電話給 PSTN 手機時，可以看到他們的電話號碼，以及當他們呼叫團隊使用者時，可以看到 PSTN 呼叫者的電話號碼。 您可以使用本機號碼原則，為您組織中的小組使用者顯示備用電話號碼，或封鎖要顯示的傳入號碼。

例如，當使用者撥打電話時，您可以變更本機號碼，以顯示貴組織的主要電話號碼，而不是使用者的電話號碼。

您可以移至**Voice**  >  Microsoft 團隊系統管理中心的語音**本機號碼原則**來管理本機號碼原則。 您可以使用全域 (組織範圍的預設) 原則，或是建立並指派自訂原則。 除非您建立並指派自訂原則，否則貴組織中的使用者將會自動取得全域原則。

## <a name="create-a-custom-caller-id-policy"></a>建立自訂本機號碼原則

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。
2. 按一下 [ **新增**]。 <br>
![系統管理中心 [新增本機號碼原則] 頁面的螢幕擷取畫面](media/caller-id-policies-add-policy.png)
3. 輸入原則的名稱和描述。
4. 從這裡選擇您想要的設定：

    - **封鎖來電**的本機號碼：開啟此設定可封鎖來電的本機號碼。
    - 覆**寫本機號碼原則**：開啟此設定可讓使用者覆寫原則中的設定，以將他們的號碼顯示在 callees 中。 這表示使用者可以選擇是否要顯示其本機號碼。 如需詳細資訊，請參閱 [結束使用者對輸出來電者識別碼的控制](https://docs.microsoft.com/microsoftteams/how-can-caller-id-be-used-in-your-organization#end-user-control-of-outbound-caller-id)。
    - **使用本機號碼取代來電**顯示：若要為使用者設定本機號碼，請選取下列其中一項：

        - **使用者號碼**：顯示使用者的號碼。 
        - [**服務號碼**]：可讓您設定要顯示為本機號碼的服務電話號碼。
        - **匿名**：以匿名方式顯示本機號碼。

    - **以這個服務號碼取代本機號碼**：選擇服務號碼來取代使用者的本機號碼。 如果您在 [**取代本機號碼者識別碼**] 中選取了 [**服務號碼**]，就可以使用此選項。

5. 按一下 [儲存]****。

## <a name="edit-a-caller-id-policy"></a>編輯本機號碼原則

您可以編輯全域原則或您建立的任何自訂原則。 

1. 在 Microsoft [團隊管理中心] 的左導覽中，移至 [**語音**  >  **本機號碼原則**]。
2. 按一下原則名稱左邊的，然後按一下 [ **編輯**]，選取原則。
3. 變更您想要的設定，然後按一下 [ **儲存**]。

## <a name="assign-a-custom-caller-id-policy-to-users"></a>將自訂本機號碼原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>相關主題

[新-CsCallingLineIdentity](https://docs.microsoft.com/powershell/module/skype/new-cscallinglineidentity?view=skype-ps)

[指派策略給小組中的使用者](assign-policies.md)
