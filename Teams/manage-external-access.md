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
description: 您的 Teams 或 IT 系統管理員可以設定其他網域的外部存取 (同盟)，讓這些網域的使用者參與 Teams。
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 2739f1b7f97e39617471ecf292ecf9424a7ac396
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726862"
---
# <a name="manage-external-access-in-microsoft-teams"></a>在 Microsoft Teams 中管理外部存取

外部存取是一種讓整個外部網域的 Teams 使用者可以在 Teams 中尋找、通話、聊天以及與您進行會議的方式。 您也可以使用外部存取，與來自其他組織、仍在使用商務用 Skype (線上或內部部署) 或 Skype (預覽版) 的人員通訊。

如果您想讓來自其他組織的人員存取小組和頻道，來賓存取可能是更好的作法。 如需外部存取和來賓存取之間差異的詳細資訊，請參閱[比較外部和來賓存取](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access)。 

使用外部存取的時機：
  
- 您的使用者位於不同網域，且需要共同作業。例如，Rob@contoso.com 和 Ann@northwindtraders.com 正與 contoso.com 和 northwindtraders.com 網域中的其他人一起共同合作一個專案。

- 您希望組織中的人員能夠使用 Teams 與組織外部特定公司的人員連絡。

- 您希望全球的任何其他 Teams 使用者能夠利用您的電子郵件地址找到您並與您連絡。 

> [!IMPORTANT]
> 若要使用 Teams 用戶端與外部使用者通訊 (無論該使用者使用 Teams 或商務用 Skype)，Teams 使用者必須位於商務用 Skype Online 中。

## <a name="plan-for-external-access"></a>規劃外部存取

Teams 預設會開啟外部存取，這表示您的組織可以與所有外部網域通訊。 如果您新增封鎖網域，將允許所有其他網域；如果您新增允許網域，所有其他網域都會遭到封鎖。 此規則的例外為是否在會議中允許匿名參與者。 在 Teams 系統管理中心設定外部存取有三種案例 ([全組織設定 **]**  >  [外部存取 **]**)：

> [!NOTE]
> Teams 使用者可以在主持會議或與其他組織人員聊天時新增應用程式。 當他們加入由其他組織主持的會議或聊天時，他們也可以使用由其他組織人員共用的應用程式。 將會套用託管使用者組織的資料原則，以及該使用者組織共用的任何協力廠商應用程式的資料共用做法。

> [!NOTE]
> 如果您關閉組織中的外部存取，外部使用者仍然可以透過匿名加入來加入會議。 若要深入了解，請參閱[在 Teams 中管理會議設定](./meeting-settings-in-teams.md)。

- **開放式同盟**：這是 Teams 的預設設定，可讓您組織中的人員尋找、通話、聊天、以及設定與任何網域中的組織外部人員進行會議。

    在此案例中，您的使用者可以與執行 Teams 或商務用 Skype 的所有外部網域通訊，「前提」是這些外部網域使用開放式同盟或是已將您的網域新增到允許清單。

- **允許特定網域**：透過將網域新增至 [允許] 清單中，可限制外部存取只能存取允許的網域。 一旦您設定了允許網域的清單，所有其他網域都會遭到封鎖。 若要允許特定網域，按一下 [新增網域]，新增網域的名稱，按一下 [對這個網域採取的動作]，然後選取 [允許]。

- **封鎖特定網域** - 透過將網域新增至 [封鎖] 清單，您可以與封鎖網域「以外」的所有外部網域通訊。 若要封鎖特定網域，按一下 [新增網域]，新增網域的名稱，按一下 [對這個網域採取的動作]，然後選取 [封鎖]。 一旦您設定了封鎖網域的清單，就會允許所有其他網域。

> [!NOTE]
> 允許或封鎖的網域僅適用於對會議的匿名存取為「關閉」的會議。

## <a name="allow-or-block-domains"></a>允許或封鎖網域

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-or-skype-for-business-organizations"></a>步驟 1 - 讓您的組織與其他 Teams 或商務用 Skype 組織通訊

![顯示 Microsoft Teams 標誌的圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [全組織設定]  >  [外部存取]。

2. 開啟 [使用者可以與其他商務用 Skype 和 Teams 使用者通訊] 設定。

     ![已開啟 [使用者可以與其他商務用 Skype 與 Teams 使用者通訊] 設定的螢幕擷取畫面。](media/manage-external-access-2.png).

3. 如果您想要讓所有 Teams 組織都能與貴組織中的使用者通訊，請直接跳至步驟 5。

4. 如果您想要限制能夠與貴組織使用者通訊的組織，可以允許部分網域以外的所有網域，或只允許特定網域。 

    - 若要允許部分網域以外的所有網域，按一下 [新增網域]，新增您要封鎖的網域。 在 [新增網域] 窗格中，輸入網域的名稱，按一下 [封鎖]，然後按一下 [完成]。 
    - 若要限制特定組織的通訊，將這些網域新增至 [允許] 狀態的清單中。 一旦在 [允許] 清單中新增任何網域，與其他組織的通訊將限於只能與其網域在 [允許] 清單中的組織通訊。 

5. 按一下 [儲存]。

6. 確定其他 Teams 組織的系統管理員也完成這些步驟。 例如，如果系統管理員要限制可與其使用者通訊的組織，則必須在其 [允許的網域] 清單中輸入您的企業網域。

### <a name="step-2---test-it"></a>步驟 2 - 測試

若要測試您的設定，您需要不在防火牆後面的 Teams 使用者。
  
1. 當您和其他組織的系統管理員皆已變更 [外部存取] 設定後，您應該已準備就緒。

2. 在 Teams 應用程式中，依電子郵件地址搜尋人員，然後傳送聊天要求。

3. 請您的 Teams 連絡人傳送聊天要求給您。 如果您沒有收到其要求，就表示您的防火牆設定有問題 (假設他們已確認其防火牆設定正確)。

4. 另一個測試問題是否為您的防火牆的方法，是前往不在您的防火牆後的 WiFi 地點。 例如咖啡店，然後使用 Teams 傳送聊天要求給您的連絡人。 如果在該 WiFi 地點要求可以成功送到，但在公司不行，您就知道問題是您的防火牆。

> [!NOTE]
> 如果您和另一位使用者都開啟外部存取並允許彼此的網域，應該就可以外部存取。 如果行不通，另一位使用者應確定其設定沒有封鎖您的網域。


## <a name="communicate-with-skype-users-in-preview"></a>與 Skype 使用者通訊 (預覽)

請按照這些步驟，讓貴組織的 Teams 使用者可以和 Skype 使用者聊天和通話。 Teams 使用者便可以搜尋 Skype 使用者，並開始一對一的純文字交談或進行音訊/視訊通話，反之亦然。

![顯示 Microsoft Teams 標誌的圖示。](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 在左側導覽中，移至 [全組織設定]  >  [外部存取]。

2. 開啟 [使用者可以與 Skype 使用者通訊] 設定。

    ![已開啟 [使用者可以與 Skype 通訊] 設定的螢幕擷取畫面。](media/manage-external-access-5.png).

若要深入瞭解 Teams 使用者和 Skype 使用者的通訊方式 (包括通訊的限制)，請參閱 [Teams 和 Skype 的互通性](teams-skype-interop.md)。

## <a name="common-external-access-scenarios"></a>常見的外部存取案例

下列各節說明如何針對常見的外部存取案例啟用同盟，以及 TeamsUpgradePolicy 如何決定傳入聊天和通話的傳遞。

### <a name="enable-federation"></a>啟用同盟

若要讓組織的使用者與另一個組織的使用者通訊，這兩個組織都必須啟用同盟。 為指定組織啟用同盟的步驟取決於組織是純線上、混合式或純內部部署。

| 如果您的組織為 | 如下所示啟用同盟 |
|:---------|:-----------------------|
|線上，沒有商務用 Skype 內部部署。 這包括具有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。| 如果使用 Teams 系統管理中心： <br>- 確定已在 [外部存取] 中啟用 [使用者可以與其他商務用 Skype 及 Teams 使用者通訊 **]** 設定。<br>- 如果您未使用開放式同盟 (其會允許與任何其他網域同盟)，請新增外部網域至 [已允許] 清單。<br><br>如果使用 PowerShell：<br>- 確保租用戶已啟用同盟：`Get-CsTenantFederationConfiguration` 必須顯示 `AllowFederatedUsers=true`。 <br>- 確保使用者的有效值 `CsExternalAccessPolicy` 具有 `EnableFederationAccess=true`。<br>- 如果您未使用開放式同盟，請確定目標網域已列在 `CsTenantFederationConfiguration` 的 `AllowedDomains` 中。 |
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
| 純線上，沒有商務用 Skype 內部部署。  這包括具有 TeamsOnly 使用者和/或商務用 Skype Online 使用者的組織。 | 如果使用 Teams 系統管理中心： <br>- 確定已在 [外部存取] 中啟用 [使用者可以與 Skype 使用者通訊 **]**。<br><br>如果使用 PowerShell： <br>- 確保租用戶已啟用同盟：`Get-CsTenantFederationConfiguration` 必須顯示 `AllowPublicUsers=true`。 <br> - 確保使用者的有效值 `CsExternalAccessPolicy` 具有 `EnablePublicCloudAccess=true`。 |
| 純內部部署 | 在內部部署工具中： <br> - 確保 Skype 已啟用為同盟合作夥伴。 <br> - 確保使用者的 `EnablePublicCloudAccess=true` 透過 `ExternalAccessPolicy` (透過全域原則、網站原則或使用者指派的原則)。|
| 混合式，部分使用者在線上 (在商務用 Skype 或 Teams 中) 和部分使用者在內部部署。| 針對線上和內部部署組織遵循上述步驟。


> [!IMPORTANT]
> 您不需要將任何 **Skype 網域** 新增為允許網域，就能讓 Teams 或商務用 Skype Online 的使用者與組織內部或外部的 Skype 使用者通訊。 允許所有 **Skype 網域**。

## <a name="how-does-external-access-compare-with-guest-access"></a>外部存取與來賓存取的比較？

若要瞭解外部存取和來賓存取之間的差異，請參閱[與其他組織的使用者通訊](communicate-with-users-from-other-organizations.md)。

## <a name="related-topics"></a>相關主題

- [外部 (同盟) 使用者的原生聊天體驗](native-chat-for-external-users.md)
