---
title: 管理會議設定
ms.author: mabond
author: mkbond007
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
- m365initiative-meetings
- highpri
description: 了解如何管理使用者在您組織中排程的 Teams 會議設定。
ms.openlocfilehash: 3faff1779830539470ae3d04cc73e58da65a637c
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2022
ms.locfileid: "68583874"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理會議設定

身為系統管理員，您可以使用 Teams 會議設定，來控制匿名使用者是否可以加入 Teams 會議、自訂會議邀請，以及如果您要啟用服務品質 (QoS)，則要針對即時流量設定連接範圍。 這些設定適用於使用者在貴組織中排程的所有 Teams 會議。 您可以在 Microsoft Teams 系統管理中心的 [會議]  >  [會議設定] 來管理這些設定。

透過每個召集人群組設定，系統管理員現在可以控制特定使用者或使用者群組是否可以允許匿名使用者加入他們召集的會議。 每個召集人和全組織原則設定都能控制匿名加入，且較具限制的設定會生效。

> [!Important]
 > **-DisableAnonymousJoin** 是全組織原則設定。 這個原則將會在未來遭到取代，接著每一召集人原則將是控制匿名加入的唯一方法。

## <a name="allow-anonymous-users-to-join-meetings"></a>允許匿名使用者加入會議

利用匿名加入，任何人都可以按一下會議邀請中的連結，以匿名使用者的身分加入會議。 若要深入了解，請參閱[在沒有 Teams 帳戶的情況下加入會議](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。 您可以不同的原則設定來控制匿名使用者加入會議的能力，無論是組織層級，還是每一會議召集人。

 ### <a name="using-the-microsoft-teams-admin-center-to-configure-organization-wide-policy"></a>使用 Microsoft Teams 系統管理中心來設定全組織原則。

您必須是 Teams 系統管理員才能進行這些變更。 請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

2. 在左側導覽中，移至 [會議]  >  [會議設定]。

3. 在 [參與者] 底下，開啟 [匿名使用者可加入會議]。

    ![系統管理中心中會議的參與者設定螢幕擷取畫面。](media/meeting-settings-participants.png "Microsoft Teams 系統管理中心中 Teams 會議的參與者設定螢幕擷取畫面")

> [!CAUTION]
> 如果您不想讓匿名使用者加入由組織中的使用者排程的會議，請關閉此設定。

### <a name="using-powershell-to-configure-per-organizer-policy"></a>使用 PowerShell 設定每一召集人原則

系統管理員現在可以控制特定使用者或使用者群組是否允許匿名使用者加入他們組織的會議。 這個新的每一召集人原則是藉由使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 中的 **-AllowAnonymousUsersToJoinMeeting** 參數加以控制。 這個功能隨附於 Teams PowerShell 2.6.0 版和更新版本。

您可以使用全組織或每一召集人原則來管理匿名加入。 我們建議您實作每一召集人原則。 全組織原則設定將會在未來遭到取代，每一召集人原則將是控制匿名加入的唯一方法。

由於全組織和每一召集人原則都會控制匿名加入，因此較嚴格的設定將會生效。 例如，如果您不允許組織層級的匿名加入，無論您針對每一召集人原則的設定為何，這都是生效的原則。 因此，若要允許匿名使用者加入會議，您必須設定下列值，同時設定兩個原則以允許匿名加入：

- **-DisableAnonymousJoin** 設為 **$false**
- **-AllowAnonymousUsersToJoinMeeting** 設為 **$true**

任何其他值組合都會防止匿名使用者加入會議。
> [!NOTE]
> 若要深入了解管理會議原則，請參閱 [管理 Microsoft Teams 中的會議原則](/microsoftteams/meeting-policies-overview)。

### <a name="blocking-anonymous-join-for-specific-client-types"></a>封鎖特定用戶端類型的匿名加入

允許匿名使用者加入會議時，他們可以使用 Teams 用戶端或使用 [Azure 通訊服務](/azure/communication-services/) 建立的自訂用戶端。 系統管理員可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) 中的 **-BlockedAnonymousJoinClientTypes** 參數封鎖選取的用戶端類型。

可能的值為：
- Null (預設)。 允許所有用戶端類型。
- Acs。 封鎖使用 [Azure 通訊服務](/azure/communication-services/) 建立的自訂用戶端。
- Microsoft Teams。 封鎖 Teams 用戶端。

## <a name="allow-anonymous-users-to-interact-with-apps-in-meetings"></a>允許匿名使用者與會議中的應用程式互動

匿名使用者現在會繼承使用者層級的全域預設權限原則。 只要使用者層級權限原則已啟用應用程式，此控制項就會允許匿名使用者與 Teams 會議中的應用程式互動。 請注意，匿名使用者只能與已在會議提供的應用程式互動，且無法取得和/或管理這些應用程式。 

> [!IMPORTANT]
> 預設會啟用允許匿名使用者與會議中應用程式互動的設定。

 **使用 Microsoft Teams 系統管理中心**

您必須是 Teams 服務系統管理員才能存取此設定。 請參閱[使用 Teams 系統管理員角色來管理 Teams](./using-admin-roles.md)，以了解取得系統管理員角色和權限。

1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。

2. 在左側導覽中，移至 [會議]  >  [會議設定]。

3. 在 [參與者 **]** 中，可以變更 [匿名使用者可以在會議中使用應用程式進行互動 **]** 設定。

> [!CAUTION]
> 如果您不想讓匿名使用者與組織中使用者排程的會議中的應用程式互動，請關閉此設定。

## <a name="customize-meeting-invitations"></a>自訂會議邀請

You can customize Teams meeting invitations to meet your organization's needs. You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>建立會議邀請標誌的秘訣  

1. 建立不超過寬度 188 像素 * 高度 30 像素 (相當小) 的影像。
2. 將影像儲存為 JPG 或 PNG 格式。
3. 將影像儲存在收到邀請的每個人都可以存取的位置，例如公用網站。

    Now you can add it to your meeting invitations. See the next steps.

### <a name="customize-your-meeting-invitations"></a>自訂您的會議邀請

 **使用 Microsoft Teams 系統管理中心**

1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。
2. 在左側導覽中，移至 [會議]  >  [會議設定]。
3. 在 [電子郵件邀請] 底下，執行下列動作：

    ![您可以自訂會議邀請設定的螢幕擷取畫面。](media/meeting-settings-invitation.png "您可以為 Teams 會議自訂的會議邀請設定的螢幕擷取畫面")

    - **標誌 URL**：輸入儲存標誌所在的 URL。
    - **法律聲明 URL**：如果您的組織有您想要讓其他人有任何法律方面的顧慮時前往的法律網站，請在此輸入其 URL。
    - **說明 URL**：如果您的組織有當其他人遇到問題時可前往的支援網站，請在這裡輸入其 URL。
    - **頁尾**：輸入要包含做為頁尾的文字。
4. 按一下 [預覽邀請] 以查看會議邀請的預覽。
5. 完成後，按一下 [儲存]。
6. 等候一小時的時間，讓變更傳播。 然後排程 Teams 會議，以查看會議邀請的外觀。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>設定您想要如何處理 Teams 會議的即時媒體流量

<a name="bknetwork"> </a>

如果您使用服務品質 (QoS) 優先順序網路流量，您可以針對每種媒體流量類型啟用 QoS 標記並設定連接埠範圍。 針對不同流量類型設定連接埠範圍，在處理即時媒體中只需一個步驟；如需更多詳細資訊，請參閱 [Teams 中的服務品質 (QoS)](qos-in-teams.md)。

> [!IMPORTANT]
> Apple 型系統: 只有在符合下列所有條件時，我們才能知道 Apple 型裝置實際設定 DSCP 值的執行個體：
> - iOS。
> - WiFi 網路。
> - Cisco 切換。
> - 網路系統管理員已新增應用程式至核准的清單。
>
> Android 型系統：沒有任何已知的限制。
>
> 如果您在 Microsoft Teams 系統管理中心針對 Teams 服務啟用 QoS 或變更設定，您也必須[將相符設定套用到所有使用者裝置](QoS-in-Teams-clients.md)和所有內部網路裝置，以便對 Teams 中的 QoS 完整實作變更。

  **使用 Microsoft Teams 系統管理中心**
1. 移至 [Teams 系統管理中心](https://admin.teams.microsoft.com)。
2. 在左側導覽中，移至 [會議]  >  [會議設定]。
3. 在 [網路] 底下，執行下列動作：

    ![系統管理中心會議網路設定的螢幕擷取畫面。](media/meeting-settings-network.png "Microsoft Teams 系統管理中心中 Teams 會議的網路設定螢幕擷取畫面")

    - 若要允許將 DSCP 標記用於 QoS，請開啟 **[即時媒體流量的服務品質 (QoS) 標記]**。 您只能選擇是否使用標記；無法為每個流量類型設定自訂標記。 如需有關 DSCP 標記的詳細資訊，請參閱[選取 QoS 實作方法](QoS-in-Teams.md#select-a-qos-implementation-method)。

        > [!IMPORTANT]
        > 請注意，啟用 QoS 只會在端點上執行，以標記離開用戶端的封包。 我們仍然建議在所有內部網路裝置上套用符合的 QoS 規則來接收流量。
        
        > [!NOTE]
        > DSCP 標記通常是透過來源連接埠完成，且 UDP 流量預設會路由至目的地連接埠為 3478 的傳輸轉送。 如果您的公司需要標記目的地連接埠，請連絡支援人員，以啟用使用 UDP 連接埠 3479 (音訊)、3480 (視訊) 和 3481 (共用) 對傳輸轉送的通訊。
    - To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing. Selecting this option is required to implement QoS. 
        > [!Note]
        > If **Quality of Service (QoS) markers for real-time media traffic** is on, then you have to manage your port settings. They aren't managed automatically.
        
        > [!IMPORTANT]
        > 如果您選取 [自動使用任何可用的連接埠]，則會使用 1024 和 65535 之間的可用連接埠。 只有在不實作 QoS 時才使用此選項。
        >
        > 選取太窄的連接埠範圍會導致通話中斷和通話品質不佳。 以下應視為最基本的建議。

如果您不確定要在環境中使用的連接埠範圍，使用下列設定應該是良好的起點。 若要深入了解，請參閱[在 Microsoft Teams 中實作服務品質 (QoS)](QoS-in-Teams.md)。 以下是 Teams 和 ExpressRoute 所使用的必要 DSCP 標記，以及建議的對應媒體連接埠範圍。

### <a name="port-ranges-and-dscp-markings"></a>連接埠範圍和 DSCP 標記

媒體流量類型| 用戶端來源連接埠範圍 \* |通訊協定|DSCP 值|DSCP 類別|
|:---             |:---                         |:---    |:---      |:---      |
|音訊            | 50,000-50,019               |TCP/UDP |46        |快速式轉送 (EF)|
|影片            | 50,020-50,039               |TCP/UDP |34        |保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059      |TCP/UDP |18        |保證式轉送 (AF21)|
| | | | |

\* 您指派的連接埠範圍不能重疊，且應該彼此相鄰。

After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs. [Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.
