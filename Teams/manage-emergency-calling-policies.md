---
title: 管理 Teams 中的緊急通話原則Microsoft
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
description: 瞭解如何在 Microsoft Teams 中使用和管理緊急通話原則，以定義當貴組織中的 Teams 使用者撥打緊急電話時會發生什麼情況。
ms.custom:
- seo-marvel-apr2020
- ms.teamsadmincenter.voice.emergencycallingpolicies.overview
ms.openlocfilehash: 4b5d293cbbd588a564ff1a0118ab4d56f96c17a2
ms.sourcegitcommit: 321de0e5d8846caaaab944826f6ca06394e707ef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/16/2022
ms.locfileid: "69414640"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a>管理 Teams 中的緊急通話原則Microsoft

如果您的組織使用Microsoft通話方案、運算子連線、Teams Phone Mobile 或直接路由做為[PSTN 連線選項](pstn-connectivity.md)，您可以在 Microsoft Teams 中使用緊急通話原則來定義當組織中的 Teams 使用者撥打緊急電話時會發生什麼情況。

您可以設定誰要通知，以及當獲指派原則的使用者撥打緊急服務時通知他們的方式。 例如，您可以設定原則設定，以自動通知貴組織的安全性中心，並讓他們在緊急電話中聆聽。  

您可以移至 Microsoft Teams 系統管理中心的 **語音**  >  **緊急電話原則**，或使用Windows PowerShell來管理緊急通話原則。 原則可以指派給使用者和 [網路網站](cloud-voice-network-settings.md)。

對於使用者，您可以使用全域 (組織的預設) 原則，或建立及指派自訂原則。 除非您建立並指派自訂原則，否則使用者會自動取得全域原則。 請記住，您可以編輯全域原則中的設定，但無法重新命名或刪除設定。 針對網路網站，您可以建立並指派自訂原則。

如果您將緊急通話原則指派給網路網站和使用者，而且該使用者位於該網路網站，則指派給該網路網站的原則會覆寫指派給使用者的原則。

## <a name="create-a-custom-emergency-calling-policy"></a>建立自訂緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **[語音**  >  **緊急] 原則**，然後按一下 [**通話原則] 索** 引標籤。

2. 按一下 [新增 **]**。

3. 輸入原則的名稱和描述。

4. 將 **[外部位置查閱] 模式** 設為開啟，讓使用者在公司網路外部的網路位置工作時，可以設定他們的緊急位址。

5. 設定撥打緊急電話時，您要通知組織中人員的方式，通常是安全性服務台。 若要這麼做，請在 **[通知] 模式** 下，選取下列其中一項：

    - **僅傳送通知**：Teams 聊天訊息會傳送給您指定的使用者和群組。
    - **會議但設為靜音**：Teams 聊天訊息會傳送給您指定的使用者和群組，他們可以聆聽 (，但無法參與) 來電者與 PSAP 運算子之間的交談。
    - **會議並取消靜音**：Teams 聊天訊息會傳送給您指定的使用者和群組，他們可以取消靜音以聆聽和參與來電者與 PSAP 運算子之間的交談。

6.  將 **緊急服務免責聲明** 設定為顯示橫幅，以提醒您的使用者確認其緊急位置。

7.  如果您選取任一 **會議為靜音** 通知模式，在 **[撥打緊急電話通知的號碼] 方** 塊中，您可以輸入使用者或群組的 PSTN 電話號碼來撥打並加入緊急通話。 例如，輸入貴組織的安全性電話機號碼，誰會在撥打緊急電話時接聽電話，然後在通話中接聽電話。 即使將模式設定為靜音會議， **但可以取消靜音**，PSTN 手機也無法取消靜音。

8. 搜尋並選取一或多個使用者或群組，例如貴組織的安全性中心，以在撥打緊急電話時通知。  通知可以傳送至使用者、通訊群組和安全性群組的電子郵件地址。 最多可以通知 50 個使用者。

9. 按一下 [ **套用]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [New-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/new-csteamsemergencycallingpolicy)。

## <a name="edit-an-emergency-calling-policy"></a>編輯緊急通話原則

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以編輯全域原則或您建立的任何自訂原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽畫面中，移至 **[語音**  >  **緊急] 原則**，然後按一下 [**通話原則] 索** 引標籤。
2. 按一下原則名稱左側來選取原則，然後按一下 [編輯 **]**。
3. 進行您要的變更，然後按一下 [ **套用]**。

### <a name="using-powershell"></a>使用 PowerShell

請參閱 [Set-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/set-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a>指派自訂緊急通話原則給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

另請參閱 [Grant-CsTeamsEmergencyCallingPolicy](/powershell/module/skype/grant-csteamsemergencycallingpolicy)。

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a>指派自訂緊急通話原則給網路網站

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

您可以指派全域原則或您建立的任何自訂原則。

1. 在 Microsoft Teams 系統管理中心的左側導覽中，移至 [**位置**  >  **網路拓撲]**，然後按一下 [**網路網站]** 索引標籤。
2. 按一下名稱左側以選取網站，然後按一下 [ **編輯]**。
3. 在 **[緊急通話原則**] 底下，選取原則，然後按一下 [ **儲存]**。

### <a name="using-powershell"></a>使用 PowerShell
使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將緊急通話原則指派給網路網站。

下列範例示範如何將名為 Contoso 緊急通話原則 1 的原則指派給 Site1 網站。

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a>相關主題

[管理 Teams 中的緊急通話路由原則](manage-emergency-call-routing-policies.md)

[Teams PowerShell 概觀](teams-powershell-overview.md)

[在 Teams 中將原則指派給使用者](policy-assignment-overview.md)
