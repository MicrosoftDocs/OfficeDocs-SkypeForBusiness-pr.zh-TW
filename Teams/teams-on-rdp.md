---
title: 使用Teams遠端桌面服務
author: serdars
ms.author: v-mahoffman
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用遠端Microsoft Teams服務。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 063ded4b2e2963ab30126c5af967017bf4981cef
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774363"
---
# <a name="teams-in-remote-desktop-services"></a>Teams遠端桌面服務中的

本文將說明在遠端桌面服務Microsoft Teams RDS (使用) 限制。

## <a name="what-is-rds"></a>什麼是 RDS？

遠端桌面 (RDS) 是建立虛擬化解決方案以適合每個最終客戶需求的平臺。 RDS 可讓您提供個別的虛擬化應用程式、提供安全的行動和遠端桌面存取，以及提供使用者從雲端執行其應用程式和桌面的能力。

RDS 提供部署彈性、成本效益和擴充性。 RDS 會透過各種部署選項提供，包括Windows Server 2016部署、Microsoft Azure部署方案，以及強大的合作夥伴解決方案陣列。
視您的環境和喜好設定，您可以將會話型虛擬化的 RDS 解決方案設定為虛擬桌面基礎結構 (VDI) 

目前，Teams桌面服務環境中提供共同合作和聊天功能的支援。 若要確保最佳的使用者體驗，請遵循本文中的指引。

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams聊天和共同合作使用 RDS

如果貴組織只想在 Teams 中使用聊天和共同Teams，您可以設定使用者層級策略，以在 Teams 中關閉通話和Teams。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定關閉通話和會議功能的政策

您可以使用系統管理中心或 PowerShell Microsoft Teams設定策略。 可能需要幾個小時 (，) 策略變更才能傳播。 如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。

[**通話策略**](teams-calling-policy.md)：Teams包括內建的 DisallowCalling 通話政策，其中所有通話功能都已關閉。 將 DisallowCalling 政策指派給組織中在虛擬化環境中Teams使用者。

[**會議政策**](meeting-policies-overview.md)：Teams包含內建的 AllOff 會議政策，其中所有會議功能都已關閉。 將 AllOff 政策指派給組織中在虛擬化環境中Teams所有使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用系統管理中心Microsoft Teams指派政策

若要將 DisallowCalling 通話策略和 AllOff 會議策略指派給使用者：

1. 在系統管理中心的左側導Microsoft Teams，**請前往** 使用者 。
2. 選取使用者名稱左側的使用者，然後選取編輯 **設定**。
3. 執行下列步驟：

    a.  在 **通話政策** 下，選取 **取消允許Calling**。

    b.  在 **會議政策下**，選取 **AllOff**。

4. 選取 **Apply**。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請選取&#x2713; (表格) 上方的核取方塊。
3. 選取 **編輯設定**，進行您想要的變更， **然後選取** Apply 。

或者，您也可以執行下列步驟：

1. 在系統管理中心的左側導Microsoft Teams，前往您想要指派的政策。 例如：

    - 前往 **語音**  >  **通話政策**，然後選取 **DisallowCalling**。
    - 前往 **會議**  >  **會議政策**，然後選取 **AllOff**。

2. 選取 [管理使用者]。
3. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
4. 新增使用者完成後，請選取 **儲存**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派策略

下列範例顯示如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話策略指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理通話政策，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例顯示如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議策略指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解使用 PowerShell 管理會議政策，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。