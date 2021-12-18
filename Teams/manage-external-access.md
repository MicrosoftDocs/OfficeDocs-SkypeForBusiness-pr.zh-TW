---
title: 管理外部存取 (同盟)
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-externalcollab
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
- seo-marvel-mar2020
description: 您的 Teams 或 IT 系統管理員可以設定其他網域 (同盟) 的外部存取權，讓來自這些網域的使用者尋找、通話、聊天，以及設定與使用者的會議。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 16a30b9e4ce9ed86516cfcf7fb0cbdb22e6c2141
ms.sourcegitcommit: b0bb7db41856ee377dbe4ca8c9dff56385bf120d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/17/2021
ms.locfileid: "61563560"
---
# <a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部存取

外部存取是一種讓組織外部的 Teams 使用者在 Teams 中尋找、通話、聊天及設定會議的方式。 您也可以使用外部存取，與來自其他組織、仍在使用商務用 Skype (線上或內部部署) 或 Skype (預覽版) 的人員通訊。

如果您希望其他組織的人能夠存取您的小組和頻道，請改為使用來賓存取。 如需外部存取和來賓存取之間差異的詳細資訊，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

使用外部存取的時機：
  
- 您的使用者位於外部網域，且需要共同作業。例如，Rob@contoso.com 和 Ann@northwindtraders.com 正與 contoso.com 和 northwindtraders.com 網域中的其他人一起共同合作一個專案。

- 您希望組織中的人員能夠使用 Teams 與組織外部特定公司的人員連絡。

- 您希望全球的任何其他 Teams 使用者能夠利用您的電子郵件地址找到您並與您連絡。 

## <a name="plan-for-external-access"></a>規劃外部存取

Teams 預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。 如果您新增封鎖網域，將允許所有其他網域；如果您新增允許網域，所有其他網域都會遭到封鎖。 此規則的例外為是否在會議中允許匿名參與者。 在 Teams 系統管理中心設定外部存取有三種案例 (**使用者** > **外部存取**)：

> [!NOTE]
> Teams 使用者可以在主持會議或與其他組織人員聊天時新增應用程式。 當他們加入由其他組織主持的會議或聊天時，他們也可以使用由其他組織人員共用的應用程式。 將會套用託管使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。

> [!NOTE]
> 如果您關閉組織中的外部存取，外部使用者仍然可以透過匿名加入來加入會議。 若要深入了解，請參閱[在 Teams 中管理會議設定](meeting-settings-in-teams.md)。

- **允許所有外部網域**：這是 Teams 中的預設設定，可讓貴組織人員尋找、通話、聊天，以及設定與貴組織外部人員在任何網域中的會議。

    在此案例中，您的使用者可以與執行 Teams 或商務用 Skype 的所有外部網域通訊，前提是這些網域是使用 Teams 或商務用 Skype，或是允許所有外部網域，或已將您的網域新增至其允許清單。

- **只允許特定外部網域**：將網域新增至 **允許** 清單中，可限制外部存取只能存取允許的網域。 一旦您設定了允許網域的清單，所有其他網域都會遭到封鎖。 若要允許特定網域，按一下 [新增網域]，新增網域的名稱，按一下 [對這個網域採取的動作]，然後選取 [允許]。

- **封鎖特定網域** - 透過將網域新增至 [封鎖] 清單，您可以與封鎖網域「以外」的所有外部網域通訊。 若要封鎖特定網域，按一下 [新增網域]，新增網域的名稱，按一下 [對這個網域採取的動作]，然後選取 [封鎖]。 一旦您設定了封鎖網域的清單，就會允許所有其他網域。

- **封鎖所有外部網域** - 防止貴組織內部人員在任何網域中尋找、通話、聊天及設定與組織外部人員的會議。

> [!NOTE]
> 允許或封鎖的網域僅適用於對會議的匿名存取為「關閉」的會議。

## <a name="allow-or-block-domains"></a>允許或封鎖網域

  **使用 Microsoft Teams 系統管理中心**

允許特定網域

1. 在 Teams 系統管理中心中，前往 **[使用者]** > **[外部存取]**。

2. 在 **[選擇您的使用者可以存取的網域]** 下，選擇 **[僅允許特定的外部網域]**。

3. 選取 **[允許網域]**。

4. 在 **[網域]** 方塊中，輸入您想要允許的網域，然後按一下 **[完成]**。

5. 如果您想要允許另一個網域，請按一下 **[加入網域]**。

6. 按一下 [儲存]。

封鎖特定網域

1. 在 Teams 系統管理中心中，前往 **[使用者]** > **[外部存取]**。

2. 在 **[選擇您的使用者可以存取的網域]** 下，選擇 **[只封鎖特定外部網域]**。

3. 選取 **[封鎖網域]**。

4. 在 **[網域]** 方塊中，輸入您想要允許的網域，然後按一下 **[完成]**。

5. 如果您想要封鎖另一個網域，請按一下 **[加入網域]**。

6. 按一下 [儲存]。

確定其他 Teams 組織的系統管理員也完成這些步驟。例如，如果系統管理員要限制可與其使用者通訊的組織，則必須在其 **[允許的網域]** 清單中輸入您的企業網域。

## <a name="communicate-with-skype-users-preview"></a>與 Skype 使用者通訊 (預覽)

請按照這些步驟，讓貴組織的 Teams 使用者可以和 Skype 使用者聊天和通話。 Teams 使用者便可以搜尋 Skype 使用者，並開始一對一的純文字交談或進行音訊/視訊通話，反之亦然。

  **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 **[使用者]** > **[外部存取]**.

2. 開啟 **[允許組織中的使用者與 Skype 使用者通訊]** 設定。

若要深入瞭解 Teams 使用者和 Skype 使用者的通訊方式 (包括通訊的限制)，請參閱 [Teams 和 Skype 的互通性](teams-skype-interop.md)。

## <a name="block-unsolicited-contact-with-external-unmanaged-teams-users"></a>封鎖與外部未管理的 Teams 使用者主動聯繫

請遵循下列步驟，防止組織中的 Teams 用戶與帳戶不受組織管理的外部 Teams 使用者主動聯繫。

  **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 **[使用者]** > **[外部存取]**.

2. 請遵循下列其中一個步驟：

    - 若要封鎖組織的 Teams 使用者與帳戶未由組織管理的外部 Teams 使用者通訊，請關閉 **[我組織中的人員可以與帳戶不受組織管理的 Teams 使用者通訊]** 設定，並清除 **[具有不是由組織管理之 Teams 帳戶的外部使用者可以連絡我組織中的使用者]** 核取方塊。

    - 如果您的 Teams 使用者已展開聯繫，若要讓組織的 Teams 使用者與帳戶未由組織管理的外部 Teams 使用者通訊，請開啟 **[我組織中的人員可以與帳戶不受組織管理的 Teams 使用者通訊]** 設定，並清除 **[具有不是由組織管理之 Teams 帳戶的外部使用者可以連絡我組織中的使用者]** 核取方塊。

    - 若要讓組織的 Teams 使用者與帳戶未由組織管理的外部 Teams 使用者通訊，並收到與這些外部 Teams 使用者通訊的要求，請開啟 **[我組織中的人員可以與帳戶不受組織管理的 Teams 使用者通訊]** 設定，並清除 **[具有不是由組織管理之 Teams 帳戶的外部使用者可以連絡我組織中的使用者]** 核取方塊。

## <a name="test-access"></a>存取測試

若要測試您的設定，您需要不在防火牆後面的 Teams 使用者。
  
1. 當您和其他組織的系統管理員皆已變更 [外部存取] 設定後，您應該已準備就緒。

2. 在 Teams 應用程式中，依電子郵件地址搜尋人員，然後傳送聊天要求。

3. 請您的 Teams 連絡人傳送聊天要求給您。 如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。

4. 另一個測試問題是否為您的防火牆的方法，是前往不在您的防火牆後的 WiFi 地點。 例如咖啡店，然後使用 Teams 傳送聊天要求給您的連絡人。 如果在該 WiFi 地點要求可以成功送到，但在公司不行，您就知道問題是您的防火牆。

> [!NOTE]
> 如果您和另一位使用者都開啟外部存取並允許彼此的網域，應該就可以外部存取。 如果行不通，另一位使用者應確定其設定沒有封鎖您的網域。

## <a name="limit-external-access-to-specific-people"></a>將外部存取限制為特定人員

如果您已啟用 [我組織中的人員可以與帳戶不是由組織管理的 Teams 使用者通訊 **]**，您可以使用 PowerShell 將外部存取限制為特定人員。

您可以使用下列範例指令碼，將 *PolicyName* 以您想要提供該原則的名稱替代，以及將 *UserName* 以您想要能夠使用外部存取的每個使用者替代。

執行指令碼之前，請確定已安裝 [Microsoft Teams PowerShell 模組](/microsoftteams/teams-powershell-install)。

```PowerShell
Connect-MicrosoftTeams

# Disable external access globally
Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

# Create a new external access policy
New-CsExternalAccessPolicy -Identity <PolicyName> -EnableTeamsConsumerAccess $true

# Assign users to the policy
$users_ids = @("<UserName1>", "<UserName2>")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "<PolicyName>" -Identity $users_ids

```

例如：

```PowerShell
Connect-MicrosoftTeams

Set-CsExternalAccessPolicy -EnableTeamsConsumerAccess $false

New-CsExternalAccessPolicy -Identity ContosoExternalAccess -EnableTeamsConsumerAccess $true

$users_ids = @("MeganB@contoso.com", "AlexW@contoso.com")
New-CsBatchPolicyAssignmentOperation -PolicyType ExternalAccessPolicy -PolicyName "ContosoExternalAccess" -Identity $users_ids

```

如需如何編譯使用者清單的其他範例，請參閱 [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation)。

您可以執行 `Get-CsExternalAccessPolicy -Include All` 來查看新原則。


另請參閱 [New-CsExternalAccessPolicy](/powershell/module/skype/new-csexternalaccesspolicy) 和 [Set-CsExternalAccessPolicy](/powershell/module/skype/set-csexternalaccesspolicy)。

## <a name="common-external-access-scenarios"></a>常見的外部存取案例

下列各節說明如何針對常見的外部存取案例啟用同盟，以及 TeamsUpgradePolicy 如何決定傳入聊天和通話的傳遞。

### <a name="enable-federation"></a>啟用同盟

若要讓組織的使用者與另一個組織的使用者通訊，這兩個組織都必須啟用同盟。 為指定組織啟用同盟的步驟取決於組織是純線上、混合式或純內部部署。

| 如果您的組織為 | 如下所示啟用同盟 |
|:---------|:-----------------------|
|線上，沒有商務用 Skype 內部部署。 這包括具有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。| 如果使用 Teams 系統管理中心： <br>- 確定外部存取中允許您想要通訊的網域。<br><br>如果使用 PowerShell：<br>- 確保租用戶已啟用同盟：`Get-CsTenantFederationConfiguration` 必須顯示 `AllowFederatedUsers=true`。 <br>- 確保使用者的有效值 `CsExternalAccessPolicy` 具有 `EnableFederationAccess=true`。<br>- 如果您未使用開放式同盟，請確定目標網域已列在 `CsTenantFederationConfiguration` 的 `AllowedDomains` 中。 |
|純內部部署 | 在內部部署工具中： <br>- 確保已在 `CsAccessEdgeConfiguration` 中啟用同盟。<br>- 確保已透過 `ExternalAccessPolicy` 啟用使用者的同盟 (透過全域原則、網站原則或使用者指派的原則)。 <br> - 如果您未使用開放式同盟，請確定目標網域已列在 `AllowedDomains`。 |
|混合式，部分使用者在線上 (在商務用 Skype 或 Teams 中) 和部分使用者在內部部署。 | 針對線上和內部部署組織遵循上述步驟。 |

### <a name="delivery-of-incoming-chats-and-calls"></a>傳入聊天和通話的傳遞 

根據收件者使用者在 TeamsUpgradePolicy 中的模式，來自同盟組織的傳入聊天和通話會抵達使用者的 Teams 或商務用 Skype 用戶端。

| 如果您想要 | 執行此動作： |
|:---------|:-----------------------|
| 確保傳入的同盟聊天和通話抵達使用者的 Teams 用戶端： | 將使用者設定為 TeamsOnly。
| 確保傳入的同盟聊天和通話抵達使用者的商務用 Skype 用戶端 | 將使用者設定為 TeamsOnly 外的任何模式。 |


### <a name="enable-federation-between-users-in-your-organization-and-consumer-users-of-skype"></a>在您的組織中的使用者與 Skype 消費者使用者之間啟用同盟

若要在您的組織中的使用者與 Skype 消費者使用者之間啟用同盟：

| 如果您的組織為 | 如下所示啟用消費者同盟 |
|:---------|:-----------------------|
| 純線上，沒有商務用 Skype 內部部署。  這包括具有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。 | 如果使用 Teams 系統管理中心： <br>-確定 **[允許我組織的使用者與 Skype 使用者通訊]** 在外部存取中啟用。<br><br>如果使用 PowerShell： <br>- 確保租用戶已啟用同盟：`Get-CsTenantFederationConfiguration` 必須顯示 `AllowPublicUsers=true`。 <br> - 確保使用者的有效值 `CsExternalAccessPolicy` 具有 `EnablePublicCloudAccess=true`。 |
| 純內部部署 | 在內部部署工具中： <br> - 確保 Skype 已啟用為同盟合作夥伴。 <br> - 確保使用者的 `EnablePublicCloudAccess=true` 透過 `ExternalAccessPolicy` (透過全域原則、網站原則或使用者指派的原則)。|
| 混合式，部分使用者在線上 (在商務用 Skype 或 Teams 中) 和部分使用者在內部部署。| 針對線上和內部部署組織遵循上述步驟。


> [!IMPORTANT]
> 您不需要將任何 **Skype 網域** 新增為允許網域，就能讓 Teams 或商務用 Skype Online 的使用者與組織內部或外部的 Skype 使用者通訊。允許所有 **Skype 網域**。

## <a name="federation-diagnostic-tool"></a>同盟診斷工具

如果您是系統管理員，可以使用下列診斷工具驗證可與同盟 Teams 使用者進行通訊的 Teams 使用者：

1. 選取 [執行測試]**** 以在 Microsoft 365 系統管理中心填入診斷。 

   > [!div class="nextstepaction"]
   > [執行測試: Teams 同盟](https://aka.ms/TeamsFederationDiag)

2. 在執行診斷窗格中，輸入 **工作階段初始化通訊協定 (SIP) 位址** 和 **同盟租用戶的網域名稱**，然後選取 [執行測試 **]**。

3. 測試會傳回解決任何防止與同盟使用者通訊之租用戶或原則設定的最佳下一個步驟。


## <a name="related-topics"></a>相關主題

- [外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)
