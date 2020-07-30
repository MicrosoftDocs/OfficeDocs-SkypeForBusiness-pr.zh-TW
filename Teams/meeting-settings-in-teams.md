---
title: 管理會議設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 了解如何管理使用者在您組織中排程的 Teams 會議設定。
ms.openlocfilehash: 559dcc8a2f5e38c4c35ba7794241e69402a092ef
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526709"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a>在 Microsoft Teams 中管理會議設定

身為系統管理員，您可以使用 Teams 會議設定，來控制匿名使用者是否可以加入 Teams 會議、自訂會議邀請，以及如果您要啟用服務品質 (QoS)，則要針對即時流量設定連接範圍。 這些設定適用於使用者在貴組織中排程的所有 Teams 會議。 您可以在 Microsoft Teams 系統管理中心的 [會議]****  >  [會議設定]**** 來管理這些設定。

## <a name="allow-anonymous-users-to-join-meetings"></a>允許匿名使用者加入會議

利用匿名加入，任何人都可以按一下會議邀請中的連結，以匿名使用者的身分加入會議。 若要深入了解，請參閱[在沒有 Teams 帳戶的情況下加入會議](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

您必須是團隊服務管理員，才能進行這些變更。 請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，瞭解如何取得管理員角色和許可權。

1. 移至系統管理中心。

2. 在左側導覽中，移至 [會議]****  >  [會議設定]****。

3. 在 [參與者]**** 底下，開啟 [匿名使用者可加入會議]****。

    ![系統管理中心中會議的參與者設定螢幕擷取畫面](media/meeting-settings-participants.png "Microsoft Teams 系統管理中心中 Teams 會議的參與者設定螢幕擷取畫面")

> [!CAUTION]
> 如果您不想讓匿名使用者加入由組織中的使用者排程的會議，請關閉此設定。

## <a name="customize-meeting-invitations"></a>自訂會議邀請

您可以自訂 Teams 會議邀請來滿足組織的需求。 您可以新增組織的標誌，並提供實用的資訊，例如支援網站和法律免責聲明的連結，以及純文字的頁尾。

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a>建立會議邀請標誌的秘訣  

1. 建立不超過寬度 188 像素 * 高度 30 像素 (相當小) 的影像。
2. 將影像儲存為 JPG 或 PNG 格式。
3. 將影像儲存在收到邀請的每個人都可以存取的位置，例如公用網站。

    現在您可以將它新增至會議邀請。 請參閱後續的步驟。

### <a name="customize-your-meeting-invitations"></a>自訂您的會議邀請

![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**

1. 移至系統管理中心。
2. 在左側導覽中，移至 [會議]****  >  [會議設定]****。
3. 在 [電子郵件邀請]**** 底下，執行下列動作：

    ![您可以自訂的會議邀請設定的螢幕擷取畫面](media/meeting-settings-invitation.png "您可以為 Teams 會議自訂的會議邀請設定的螢幕擷取畫面")

    - **標誌 URL**：輸入儲存標誌所在的 URL。
    - **法律聲明 URL**：如果您的組織有您想要讓其他人有任何法律方面的顧慮時前往的法律網站，請在此輸入其 URL。
    - **說明 URL**：如果您的組織有當其他人遇到問題時可前往的支援網站，請在這裡輸入其 URL。
    - **頁尾**：輸入要包含做為頁尾的文字。
4. 按一下 [預覽邀請]**** 以查看會議邀請的預覽。
5. 完成後，按一下 [儲存]****。
6. 等候一小時的時間，讓變更傳播。 然後排程 Teams 會議，以查看會議邀請的外觀。  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a>設定您想要如何處理 Teams 會議的即時媒體流量

<a name="bknetwork"> </a>

如果您使用的是服務品質（QoS）來設定網路流量的優先順序，您可以為每種媒體流量啟用 QoS 標記和設定埠範圍。 針對不同流量類型設定連接埠範圍，在處理即時媒體中只需一個步驟；如需更多詳細資訊，請參閱 [Teams 中的服務品質 (QoS)](qos-in-teams.md)。

> [!IMPORTANT]
> 如果您在 [團隊服務] 的 Microsoft [團隊管理中心] 啟用 [QoS] 或 [變更設定]，您也必須[將 [相符] 設定套用到所有的使用者裝置](QoS-in-Teams-clients.md)和所有內部網路裝置，才能完全實現團隊中的 QoS 變更。

 ![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**
1. 移至系統管理中心。
2. 在左側導覽中，移至 [會議]****  >  [會議設定]****。
3. 在 [網路]**** 底下，執行下列動作：

    ![系統管理中心中會議的會議設定螢幕擷取畫面](media/meeting-settings-network.png "Microsoft Teams 系統管理中心中 Teams 會議的網路設定螢幕擷取畫面")

    - 若要允許將 DSCP 標記用於 QoS，請開啟 [插入即時媒體流量的服務品質 (QoS) 標記]****。 您只能選擇是否使用標記；無法為每個流量類型設定自訂標記。 如需有關 DSCP 標記的詳細資訊，請參閱[選取 QoS 實作方法](QoS-in-Teams.md#select-a-qos-implementation-method)。
        > [!NOTE]
        > DSCP 標記通常是透過來源埠完成，而 UDP 流量預設會以3478的目的地埠路由到傳輸中繼。 如果您的公司需要在目的地埠上加上標記，請聯絡支援人員，以便使用 UDP 埠3479（音訊）、3480（影片）和3481（共用）來與傳輸中繼進行通訊。
    - 若要指定連接埠範圍，請在 [選取各即時媒體流量類型的連接埠範圍]**** 旁選取 [指定連接埠範圍]****，然後輸入音訊、視訊和螢幕共用的開始和結束連接埠。 若要實作 QoS，需要選取此選項。
        > [!IMPORTANT]
        > 如果您選取 [自動使用任何可用的連接埠]****，則會使用 1024 和 65535 之間的可用連接埠。 只有在不實作 QoS 時才使用此選項。
        >
        > 選取太窄的連接埠範圍會導致通話中斷和通話品質不佳。 以下應視為最基本的建議。

如果您不確定要在環境中使用的連接埠範圍，使用下列設定應該是良好的起點。 若要深入了解，請參閱[在 Microsoft Teams 中實作服務品質 (QoS)](QoS-in-Teams.md)。 以下是 Teams 和 ExpressRoute 所使用的必要 DSCP 標記，以及建議的對應媒體連接埠範圍。

### <a name="port-ranges-and-dscp-markings"></a>連接埠範圍和 DSCP 標記

媒體流量類型| 用戶端來源連接埠範圍 \* |通訊協定|DSCP 值|DSCP 類別|
|:---             |:---                         |:---    |:---      |:---      |
|音訊            | 50,000-50,019               |TCP/UDP |46        |快速式轉送 (EF)|
|影片            | 50,020-50,039               |TCP/UDP |34        |保證式轉送 (AF41)|
|應用程式/螢幕共用| 50,040-50,059      |TCP/UDP |滿        |保證式轉送 (AF21)|
| | | | |

\* 您指定的連接埠範圍不能重疊，且必須彼此相接。

在使用 QoS 一段時間後，您將會獲得這三個工作負載相關需求的使用資訊，而且您可以根據自己的特定需求來選擇要進行的變更。 [通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)對此應該有幫助。
