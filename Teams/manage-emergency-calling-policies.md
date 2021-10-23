---
title: 在 Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 瞭解如何在 Microsoft Teams 中使用和管理緊急電話Teams使用者撥打緊急電話時會發生什麼情況。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 842fa95be2c9aecaa14b1902ed5b3feb4ca0da7a
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536544"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>在 Microsoft Teams

如果貴組織使用 Microsoft 通話方案、運算子 連線 或直接路由做為[PSTN](pstn-connectivity.md)連接選項，您可以使用 Microsoft Teams 中的緊急通話政策來定義當貴組織的 Teams 使用者撥打緊急電話時會發生什麼情況。

您可以設定指派策略的使用者撥打緊急服務時要通知哪些人，以及通知他們什麼情況。 例如，您可以設定策略設定，以自動通知貴組織的安全電話台，讓他們聆聽緊急電話。  

您可以到系統管理中心中的語音緊急Microsoft Teams，或使用語音  >  **** Windows PowerShell。 可以將策略指派給使用者和網路 [網站](cloud-voice-network-settings.md)。

對於使用者，您可以使用全域 (全組織的預設) ，或建立及指派自訂策略。 除非您建立並指派自訂策略，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除。 針對網路網站，您可以建立並指派自訂策略。

如果您將緊急通話策略指派給網路網站和使用者，且該使用者位於該網路網站，則指派給網路網站的策略會重寫指派給使用者的策略。

## <a name="create-a-custom-emergency-calling-policy"></a>建立自訂緊急通話政策

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在系統管理中心的左側導Microsoft Teams，請前往 **[語音** 緊急處理政策>，然後按一下 [  >  ******通話政策>** 定位點。
2. 按一下 [新增 **]**。
3. 輸入原則的名稱和描述。
4. 設定當您撥打緊急電話時，您希望如何通知貴組織人員 ，通常是安全電話機。 若要這麼做，請在通知 **模式** 下，選取下列其中一項：
    - **僅傳送通知**：Teams聊天訊息會傳送至您指定的使用者和群組。
    - 以 **靜音** 方式會議且無法取消靜音：Teams 聊天訊息會寄給您指定的使用者和群組，他們可以聆聽 (但無法參與) 來電者與 PSAP 運算子之間的交談。
    - 以 **靜音** 方式會議，但可以取消靜音：Teams 聊天訊息會寄給您指定的使用者和群組，他們可以取消靜音，以聆聽並參與來電者與 PSAP 運算子之間的交談。
5.  如果您在靜音通知模式中選取了其中一個會議，您可以在 [撥打緊急電話通知的號碼> 方塊中，輸入使用者或群組的 PSTN 電話號碼，以撥打並加入緊急通話。 例如，輸入貴組織安全電話台的號碼，該號碼在撥打緊急電話時會接到來電，然後可以聆聽通話。 PSTN 電話無法取消靜音，即使模式設定為 [以靜音方式會議，但 **可以取消靜音**。
6. 搜尋並選取一或多個使用者或群組 ，例如貴組織的安全電話台，以在緊急電話撥打時通知。  通知可以寄到使用者、通訊群組和安全性群組的電子郵件地址。 最多可以通知 50 個使用者。
7. 按一下 **[Apply.**

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>編輯緊急通話政策

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或任何您建立的任何自訂策略。

1. 在系統管理中心的左側導Microsoft Teams，請前往 **[語音** 緊急處理政策>，然後按一下 [  >  ******通話政策>** 定位點。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 進行您想要的變更，然後按一下 **[Apply.**

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>指派自訂緊急電話策略給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>將自訂緊急通話策略指派給網路網站

使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話策略指派給網路網站。

下列範例顯示如何將稱為 Contoso 緊急電話策略 1 的策略指派給 Site1 網站。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相關主題

[在 Teams](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[將原則指派給 Teams 中的使用者](assign-policies.md)