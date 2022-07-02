---
title: 搭配遠端桌面服務使用 Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何搭配遠端桌面服務使用 Microsoft Teams。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606092"
---
# <a name="teams-in-remote-desktop-services"></a>遠端桌面服務中的 Teams

本文將說明在遠端桌面服務 (RDS) 環境中使用 Microsoft Teams 的需求與限制。

## <a name="what-is-rds"></a>什麼是 RDS？

遠端桌面服務 (RDS) 是針對每個客戶需求建立虛擬化解決方案的平臺。 RDS 可讓您提供個別的虛擬化應用程式、提供安全的行動和遠端桌面存取，並讓使用者能夠從雲端執行其應用程式和桌面。

RDS 提供部署彈性、成本效率和擴增性。 RDS 透過各種不同的部署選項提供，包括內部部署Windows Server 2016、雲端部署用 Microsoft Azure，以及強大的合作夥伴解決方案陣列。
根據您的環境和喜好設定，您可以將會話型虛擬化的 RDS 解決方案設定為虛擬桌面基礎結構， (VDI) 

目前，遠端桌面服務環境中的 Teams 支援共同作業和聊天功能。 若要確保使用者獲得最佳體驗，請依照本文中的指引進行。

## <a name="teams-on-rds-with-chat-and-collaboration"></a>具有聊天和共同作業的 Teams RDS

如果貴組織只想要使用 Teams 中的聊天和共同作業功能，您可以設定使用者層級原則，關閉 Teams 中的通話和會議功能。

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>設定原則以關閉通話和會議功能

您可以使用 Microsoft Teams 系統管理中心或 PowerShell 來設定原則。 可能需要幾個小時 () 原則變更才會散播。 如果您沒有立即看到指定帳戶的變更，請在幾個小時後再試一次。

[**通話原則**](teams-calling-policy.md)：Teams 包含內建的 [不允許通話] 通話原則，其中所有通話功能都已關閉。 將不允許縮放原則指派給在虛擬環境中使用 Teams 的所有組織使用者。

[**會議原則**](meeting-policies-overview.md)：Teams 包含內建的 AllOff 會議原則，其中會關閉所有會議功能。 將 AllOff 原則指派給在虛擬環境中使用 Teams 的組織中的所有使用者。

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心指派原則

若要將 DisallowCalling 通話原則和 AllOff 會議原則指派給使用者：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 **[使用者]**。
2. 選取使用者名稱左側以選取使用者，然後選取 **[編輯設定]**。
3. 執行下列步驟：

    a.  在 **[通話原則]** 底下，選 **取 [不允許縮放]**。

    b.  在 **[會議原則]** 底下，選取 **[AllOff]**。

4. 選取 [ **套用]**。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;] (核取方塊) 欄中，選取使用者。 若要選取所有使用者，請選取表格頂端) &#x2713; (核取記號。
3. 選取 **[編輯設定**]，進行您要的變更，然後選取 [ **套用]**。

或者，您也可以執行下列步驟：

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至您要指派的原則。 例如：

    - 移至 **[語音**  >  **通話原則**]，然後選取 **[不允許縮放]**。
    - 移至 **[會議**  >  **會議原則**]，然後選取 **[AllOff]**。

2. 選取 [管理使用者]。
3. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
4. 當您完成新增使用者時，請選取 [ **儲存]**。

#### <a name="assign-policies-using-powershell"></a>使用 PowerShell 指派原則

下列範例示範如何使用 [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) 將 DisallowCalling 通話原則指派給使用者。

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理通話原則，請參閱 [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)。

下列範例示範如何使用 [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) 將 AllOff 會議原則指派給使用者。

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

若要深入瞭解如何使用 PowerShell 管理會議原則，請參閱 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)。