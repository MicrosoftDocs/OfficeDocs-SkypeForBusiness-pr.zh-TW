---
title: 使用 Teams 與遠端桌面服務
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何使用 Microsoft Teams 與遠端桌面服務。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7090aac3c5e7ff724a079e7f9d9ffe9d712cd447
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119092"
---
# <a name="teams-in-remote-desktop-services"></a>遠端桌面服務中的 Teams

本文將說明在 RDS 和 RDS 環境遠端桌面服務 (Microsoft Teams) 限制。

## <a name="what-is-rds"></a>什麼是 RDS？

遠端桌面 (RDS) 是建立虛擬化解決方案以適合每個最終客戶需求的平臺。 RDS 可讓您提供個別的虛擬化應用程式、提供安全的行動和遠端桌面存取，以及提供使用者從雲端執行其應用程式和桌面的能力。

RDS 提供部署彈性、成本效益和擴充性。 RDS 會透過各種部署選項提供，包括適用于內部部署的 Windows Server 2016、適用于雲端部署的 Microsoft Azure，以及強大的合作夥伴解決方案陣列。
視您的環境和喜好設定，您可以將 RDS 解決方案設定為會話型虛擬化，做為虛擬桌面基礎結構 (VDI) 

目前，遠端桌面服務環境中的 Teams 支援共同合作和聊天功能。 若要確保最佳的使用者體驗，請遵循本文中的指引。

## <a name="teams-on-rds-with-chat-and-collaboration"></a>RDS 上的團隊與聊天和共同合作

如果貴組織只想在 Teams 中使用聊天和共同合作功能，您可以設定使用者層級策略以關閉 Teams 中的通話和會議功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定關閉通話和會議功能的政策

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定策略。 可能需要幾個小時 (，) 策略變更才能傳播。 如果您沒立即看到給定帳戶的變更，請在幾個小時後再試一次。

[**通話策略**](teams-calling-policy.md)：Teams 包含內建的 DisallowCalling 通話政策，其中會關閉所有通話功能。 將 DisallowCalling 政策指派給組織中在虛擬化環境中使用 Teams 的所有使用者。

[**會議政策**](meeting-policies-in-teams.md)：Teams 包含內建的 AllOff 會議政策，其中所有會議功能都已關閉。 將 AllOff 政策指派給組織中在虛擬化環境中使用 Teams 的所有使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心指派策略

若要將 DisallowCalling 通話策略和 AllOff 會議策略指派給使用者：

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **使用者**。
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

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往您想要指派的政策。 例如：

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