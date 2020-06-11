---
title: 管理會議原則
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
- seo-marvel-apr2020
description: 瞭解如何在團隊中管理會議原則設定，並使用他們來控制會議參與者針對使用者排程會議所提供的功能。
ms.openlocfilehash: ae1b73c2aefecb64dfe18e0fda0aa880f3962aa7
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690939"
---
# <a name="manage-meeting-policies-in-teams"></a>在團隊中管理會議原則

::: zone target="docs"
會議原則是針對由您組織中的使用者所排程的會議，控制會議參與者可用於會議的功能。 建立原則並進行變更之後，您可以將使用者指派給該原則。 您可以在 Microsoft 團隊系統管理中心或使用[PowerShell](teams-powershell-overview.md)管理會議原則。

> [!NOTE]
> 如需使用角色來管理會議簡報者與出席者權限的相關資訊，請參閱[小組會議中的角色](https://support.microsoft.com/en-us/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以透過下列方式來實施原則，這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。

|實現類型  |說明  |
|---------|---------|
|每個召集人    |當您實施每個召集人原則時，所有會議參與者都會繼承召集人的原則。 例如，**自動承認人員**是每個召集人原則，並控制使用者是否要直接加入會議，或在會議廳中等待指派原則的使用者所排程的會議。          |
|每位使用者    |當您執行每個使用者的原則時，只會套用每個使用者的原則，以限制召集人和/或會議參與者的特定功能。 例如，[**允許在頻道中立即開會**] 是每個使用者的原則。     |
|每個召集人和每位使用者     |當您實現每個召集人與每個使用者的原則組合時，某些功能會根據其原則和召集人原則，限制會議參與者。 例如，[**允許雲端錄製**] 是每個召集人和每個使用者的原則。 開啟此設定可讓會議召集人與參與者開始並停止錄製。

根據預設，會建立名為 [全域] （組織範圍預設值）的原則。 貴組織中的所有使用者預設都會獲指派 [全域會議原則]。 您可以對其進行變更或建立一或多個自訂原則，並將使用者指派給他們。 除非您建立並指派自訂原則，否則使用者會取得全域原則。 當您建立自訂原則時，您可以允許或防止您的使用者使用某些功能，然後將其指派給將設定套用至其中的一或多個使用者。

> [!NOTE]
> 如果使用者已啟用音訊會議授權，或使用者允許音訊會議，則 [會議詳細資料] 按鈕就會提供，會議詳細資料將無法使用。

## <a name="change-or-create-a-meeting-policy"></a>變更或建立會議原則

若要變更或建立會議原則，請移至 [Microsoft Teams 系統管理中心] > **[會議] ** > ** [會議原則]**。 從清單中選取原則，或選取 **[新增]**。 如果您要建立新原則，請新增原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。 選擇您的設定，然後選取 [**儲存**]。

例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：

在 [音訊與視訊]**** 下：
- 關閉 [允許雲端錄製]。
- 關閉 [允許 IP 視訊]。

在 [內容共用]**** 下：
- 停用 [螢幕畫面分享模式]。
- 關閉 [允許白板]。
- 關閉 [允許共用記事]。

然後，將原則指派給使用者。

> [!NOTE]
> 一次只能為使用者指派一個會議原則。

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

若要指派會議原則給一位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽窗格中，移至 [使用者]****，然後按一下該使用者。
2. 按一下使用者名稱左方以選取使用者，然後按一下 [編輯設定]****。
3. 在 [會議原則]**** 下，選取要指派的原則，然後按一下 [套用]****。

若要一次將原則指派給多位使用者：

1. 在 Microsoft Teams 系統管理中心的左側瀏覽中，移至 [使用者]****，然後搜尋使用者或篩選檢視畫面，以顯示您想要的使用者。
2. 在 [&#x2713;]**** (核取方塊) 欄中，選取使用者。 若要選取 [所有使用者]，請按一下表格頂端的 [&#x2713;] (核取方塊)。
3. 按一下 [編輯設定]****，進行所需的變更，然後按一下 [套用]****。  

或者，您也可以執行下列動作：

1. 在 Microsoft 團隊系統管理中心的左導覽中，前往 [**會議**  >  **會議原則**]。
2. 按一下原則名稱的左側來選取原則。
3. 選取 [管理使用者]****。
4. 在 **[管理使用者]** 窗格中，依顯示名稱或使用者名稱搜尋使用者，選取名稱，然後選取 **[新增]**。 針對要新增的每一個使用者重複此步驟。
5. 完成新增使用者之後，請選取 [**儲存**]。

> [!NOTE]
> 如果使用者已獲指派，您就無法刪除原則。 您必須先將其他原則指派給所有受影響的使用者，然後才能刪除原始原則。

## <a name="meeting-policy-settings"></a>會議原則設定

當您在 [**會議原則**] 頁面上選取現有的原則，或選取 [**新增**] 以新增原則時，您可以設定下列各項的設定。

- [一般](#meeting-policy-settings---general)
- [音訊 & 影片](#meeting-policy-settings---audio--video)
- [內容共用](#meeting-policy-settings---content-sharing)
- [參與者 & 來賓](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>會議原則設定-一般

- [允許頻道中的 [立即開會]](#allow-meet-now-in-channels)
- [允許 Outlook 增益集](#allow-the-outlook-add-in)
- [允許頻道會議排程](#allow-channel-meeting-scheduling)
- [允許排程私人會議](#allow-scheduling-private-meetings)
- [在私人會議中允許立即開會](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>允許頻道中的 [立即開會]

這是針對每個使用者的原則，在會議開始之前就會套用。 此設定控制使用者是否可在團隊頻道中啟動零星會議。 如果您開啟此選項，當使用者在團隊頻道中張貼訊息時，使用者可以按一下撰寫方塊下的 [**立即開會**]，以在頻道中啟動零星會議。 預設值為 True。

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>允許 Outlook 增益集

這是針對每個使用者的原則，在會議開始之前就會套用。 此設定控制團隊會議是否可在 Outlook 中排程（Windows、Mac、web 及行動裝置）。

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

如果您關閉此功能，使用者在 Outlook 中建立新會議時，將無法排程團隊會議。 例如，在 Windows 版 Outlook 中，新的 [**小組會議**] 選項不會顯示在功能區中。

### <a name="allow-channel-meeting-scheduling"></a>允許頻道會議排程

這是針對每個使用者的原則，在會議開始之前就會套用。 此設定控制使用者是否可在團隊頻道中排程會議。  如果您關閉此功能，當使用者在團隊頻道中開始會議，且團隊中的使用者停用 [**新增頻道**] 選項時，系統將無法使用 [**排程會議**] 選項。 預設值為 True。

![顯示團隊中的 [排程會議] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>允許排程私人會議

這是針對每個使用者的原則，在會議開始之前就會套用。 此設定可控制使用者是否可以在小組中排程私人會議。 如果會議不是發佈至小組中的頻道，就是私人的。

請注意，如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**]，就會針對小組中的使用者停用 [**新增必要的出席**者] 和 [**新增頻道**] 選項。 預設值為 True。

### <a name="allow-meet-now-in-private-meetings"></a>在私人會議中允許立即開會

這是針對每個使用者的原則，在會議開始之前就會套用。 此設定可控制使用者是否能開始即席私人會議。  預設值為 True。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>會議原則設定-音訊 & 影片

- [允許進行文字](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [允許 IP 視訊](#allow-ip-video)
- [媒體位元速率（Kbs）](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>允許進行文字

這是每個組織單位和每個使用者原則的組合。 此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。 如果您關閉此功能，則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。 開始錄製需要已開啟此設定的人員，才能讓錄製也包含操作。 

請注意，目前只有將團隊中的語言設定為英文，且在會議中朗讀英文的使用者，才支援會議記錄會議。

![螢幕擷取畫面顯示會議中的 [會議] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>允許雲端錄製

這是每個組織單位和每個使用者原則的組合。 此設定控制是否可以錄製此使用者的會議。 如果參與者已開啟該原則設定，且是來自同一個組織的經過驗證的使用者，則錄製可以由會議召集人或其他會議參與者啟動。

貴組織外部人員（例如同盟與匿名使用者）無法啟動錄製。 來賓使用者無法啟動或停止錄製。 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

我們來看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 虛假 |
|Amanda | Location1MeetingPolicy | 滿足|
|約翰（外部使用者） | 不適用 | 不適用|

依 Daniela 組織的會議無法錄製，且 Amanda 已啟用原則設定的使用者，無法錄製由 Daniela 組織的會議。 您可以錄製由 Amanda 組織的會議，但 Daniela，誰已停用原則設定，而誰是外部使用者，就無法錄製由 Amanda 組織的會議。

若要深入瞭解雲端會議錄製，請參閱[小組雲端會議錄製](cloud-recording.md)。

### <a name="allow-ip-video"></a>允許 IP 視訊

這是每個組織單位和每個使用者原則的組合。 影片是會議的關鍵元件。 在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。 此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。 在已啟用此原則的使用者組織的會議中，如果會議參與者也已啟用原則，則允許會議參與者在會議中進行影片共用。 沒有指派任何原則的會議參與者（例如匿名及同盟參與者）會繼承會議召集人的原則。

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

我們來看看下列範例。

|使用者 |會議原則  |允許 IP 影片 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足        |
|Amanda    | Location1MeetingPolicy        | 虛假      |

由 Daniela 託管的會議允許開啟影片。 Daniela 可以加入會議，然後開啟 [影片]。 Amanda 無法在 Daniela 的會議中開啟影片，因為 Amanda 的原則設定為 [不允許視頻]。 Amanda 可以查看會議中其他參與者所共用的影片。

在由 Amanda 託管的會議中，任何人都無法開啟影片，不論指派的是何種影片原則。 這表示 Daniela 無法在 Amanda 的會議中開啟影片。  

如果 Daniela 呼叫 Amanda 的 [影片]，Amanda 只能以音訊接聽通話。  通話連線時，Amanda 可以看到 Daniela 的影片，但無法開啟影片。 如果 Amanda 呼叫 Daniela，Daniela 可以使用影片和音訊接聽通話。 當通話連線時，Daniela 可以視需要開啟或關閉她的影片。

### <a name="media-bit-rate-kbs"></a>媒體位元速率（Kbs）

這是每個使用者的原則。 此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸，決定媒體位元速率。 它適用于通話或會議中的使用者的上行與下行媒體遍歷。 此設定可讓您精細控制貴組織中的頻寬管理。 根據使用者所需的會議案例，我們建議您有足夠的頻寬來提供良好的品質體驗。 最小值為 30 Kbps，而最大值則視會議案例而定。 若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。

如果沒有足夠的頻寬可供會議使用，參與者會看到指出網路品質不佳的訊息。

如果會議需要最高品質的影片體驗，例如 CEO 董事會會議和小組現場活動，我們建議您將頻寬設定為 10 Mbps。 即使已設定最大的體驗，小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況（視情況而定）。 

## <a name="meeting-policy-settings---content-sharing"></a>會議原則設定-內容共用

- [螢幕畫面分享模式](#screen-sharing-mode)
- [允許參與者授與要求控制](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者授與或要求控制](#allow-an-external-participant-to-give-or-request-control)
- [允許 PowerPoint 共用](#allow-powerpoint-sharing)
- [允許白板](#allow-whiteboard)
- [允許共用筆記](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>螢幕畫面分享模式

這是每個組織單位和每個使用者原則的組合。 此設定控制使用者的會議是否允許桌面和/或視窗共用。 沒有指派任何原則的會議參與者（例如，匿名、來賓、B2B 及同盟參與者）會繼承會議召集人的原則。

|設定值 |行為  |
|---------|---------|
|**整個畫面**    | 在會議中允許進行完整的桌面共用和應用程式共用 |
|**單一應用程式**   | 允許在會議中共用應用程式        |
|**禁止**     |在會議中關閉螢幕共用和應用程式共用。       |

我們來看看下列範例。

|使用者 |會議原則 |螢幕畫面分享模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個畫面 |
|Amanda   | Location1MeetingPolicy  | 禁止 |

Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。 如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定的應用程式，因為她的原則設定已停用。 在由 Amanda 託管的會議中，不論指派給他們的螢幕共用模式原則為何，都不允許任何人共用其螢幕或單一應用程式。 這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。  

目前，如果使用者使用的是 Google Chrome，就無法在團隊會議中播放影片或共用其螢幕。

### <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者授與要求控制

這是每個使用者的原則。 此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。 若要授與控制權，請將游標暫留在畫面頂端。 

如果使用者已開啟此設定，則 [取得**控制權**] 選項會顯示在共用會話的上方列中。 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

如果使用者的設定已關閉，則無法使用 [**提供控制權**] 選項。

![螢幕擷取畫面顯示 [提供控制] 選項無法使用](media/meeting-policies-give-control-not-available.png)

我們來看看下列範例。

|使用者 |會議原則  |允許參與者授與要求控制 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Babek    | Location1MeetingPolicy        | 虛假   |

Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者，但 Babek 無法將控制權授與其他參與者。

若要使用 PowerShell 來控制誰可以授與控制權或接受控制要求，請使用 AllowParticipantGiveRequestControl Cmdlet。

> [!NOTE]
> 若要在共用期間提供並控制共用的內容，雙方都必須使用小組桌面用戶端。 當任一方執行瀏覽器中的 Teams 時，則不支援控制。 這是我們正計畫修正的技術限制所造成。 

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者授與或要求控制

這是每個使用者的原則。 此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。 團隊會議中的外部參與者可以分類如下：  

- 匿名使用者
- 來賓使用者  
- B2B 使用者
- 聯盟使用者  

聯盟使用者是否可在共用時授與外部使用者控制權，由允許外部參與者在其組織中**提供或要求控制**設定。

若要使用 PowerShell 來控制外部參與者是否可以授與控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。

### <a name="allow-powerpoint-sharing"></a>允許 PowerPoint 共用

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。 外部使用者（包括匿名、來賓及同盟使用者）繼承會議召集人的原則。

我們來看看下列範例。

|使用者 |會議原則  |允許 PowerPoint 共用 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy        | 虛假   |

Amanda 無法在會議中共用 PowerPoint 投影片卡座，即使她是會議召集人也一樣。 Daniela 可以共用 PowerPoint 投影片卡座，即使會議是透過 Amanda 來組織。 Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片，即使她無法共用 PowerPoint 投影片投影片也一樣。

### <a name="allow-whiteboard"></a>允許白板

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中共用白板。 外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。 

我們來看看下列範例。

|使用者 |會議原則  |允許白板|
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy        | 虛假   |

Amanda 無法在會議中共用白板，即使她是會議召集人也一樣。 Daniela 可以共用白板，即使會議是由 Amanda 來組織。  

### <a name="allow-shared-notes"></a>允許共用筆記

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中建立和共用筆記。 外部使用者（包括匿名、B2B 及同盟使用者）繼承會議召集人的原則。 目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。

我們來看看下列範例。

|使用者 |會議原則  |允許共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy | 虛假 |

Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。

## <a name="meeting-policy-settings---participants--guests"></a>會議原則設定-參與者 & 來賓

這些設定會控制哪些會議參與者會在會議廳中等待，並在會議遭到准許前進行會議，以及在會議中允許的參與程度。

- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [自動承認人員](#automatically-admit-people)
- [允許撥入使用者略過大廳](#allow-dial-in-users-to-bypass-the-lobby)
- [啟用即時標題](#enable-live-captions)
- [允許在會議中聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。 如果您的群組有音訊會議，且使用它來連接，請參閱[音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果您的 [小組] 群組沒有音訊會議，請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

### <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

這是允許 leaderless 撥入會議會議的每個召集人原則。 此設定會控制撥入使用者是否無需經過驗證的使用者，就能從出席中的組織加入會議。 預設值為 False，表示撥入使用者會在大廳等候，直到組織中的經過驗證的使用者加入會議為止。 

**記事**如果是 False，而撥入使用者會先加入會議，並放在大廳，組織使用者必須加入會議與團隊用戶端，才能從大廳承認使用者。 沒有可撥打給使用者的大廳控制項。 


### <a name="automatically-admit-people"></a>自動承認人員

這是每個召集人原則。 此設定控制使用者是否直接加入會議，或在大廳等候，直到經過驗證的使用者准許。 此設定不會套用至 [撥入使用者]。 

![螢幕擷取畫面顯示會議廳中有使用者的會議](media/meeting-policies-lobby.png)

 會議召集人可以按一下會議邀請中的 [**會議選項**]，針對每個會議所排程的會議變更此設定。
 
 **記事**在會議選項中，設定標示為「誰可以略過大廳」
  
|設定值  |加入行為 |
|---------|---------|
|**任何人**   |所有會議參與者都能直接加入會議，不需要在大廳等候。 這包括經過驗證的使用者、來自受信任組織（同盟）、來賓和匿名使用者的外部使用者。     |
|**貴組織和聯盟組織中的每個人**     |組織內經過驗證的使用者，包括來賓使用者以及受信任組織的使用者，直接加入會議，不需在大廳等候。  匿名使用者在大廳等候。   |
|**貴組織中的每個人**    |從組織內的經過驗證的使用者（包括來賓使用者），直接加入會議，不需在大廳等候。  受信任的組織中的使用者和匿名使用者在大廳等候。 這是預設設定。           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允許撥入使用者略過大廳

這是每個召集人原則。 此設定控制由手機撥入的人員是否直接加入會議，或無論是否已**自動准許 [人員**] 設定，也會在大廳中等待。 預設值為 False。 當為 False 時，撥入使用者會在大廳等候，直到組織使用者與團隊用戶端加入會議，然後允許他們。 當為 True 時，當組織使用者加入會議時，撥入使用者會自動加入會議。 

**記事**如果撥入使用者在組織使用者加入會議之前加入會議，則會將它們放在大廳中，直到組織使用者使用團隊用戶端加入會議，然後允許他們。 


### <a name="enable-live-captions"></a>啟用即時標題

這是針對每個使用者的原則，且適用于會議期間。 此設定會控制是否可使用 [**開啟即時標題**] 選項來開啟和關閉使用者出席會議中的即時輔助字幕。  

![顯示 [開啟即時標題] 選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**已停用，但使用者可以覆寫**     | 在會議期間，使用者不會自動開啟 [即時] 標題。 使用者會看到 [溢出（**...**）] 功能表中的 [**開啟即時標題**] 選項，以將其開啟。 這是預設設定。 |
|**禁止**     | 使用者在會議期間停用 [即時] 標題。 使用者沒有選項可將其開啟。          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>允許在會議中聊天

這是每個召集人原則。 此設定控制是否允許在使用者的會議中使用會議聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>會議原則設定-指定的簡報者角色模式

這是每個使用者的原則。 這項設定可讓您變更小組用戶端的 [**會議選項**] 中的 [**可以出示的人員**] 設定的預設值。 此原則設定會影響所有會議，包括 [立即開會] 會議。

[**可以出席的人員**] 設定可讓會議召集人選擇要在會議中成為簡報者的人員。 若要深入瞭解，請參閱[在團隊會議中](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)[變更團隊會議](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e)與角色的參與者設定。

目前您只能使用 PowerShell 來設定此原則設定。 您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。 或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。

若要指定 [**可以提出的人員**] 的預設值，請將**DesignatedPresenterRoleMode**參數設定為下列其中一項：

- **EveryoneUserOverride**：所有會議參與者都可以是簡報者。 此為預設值。 這個參數會對應到 [小組] 中的 [**所有人**] 設定。
- **EveryoneInCompanyUserOverride**：組織中經過驗證的使用者，包括來賓使用者，都可以是簡報者。 這個參數會對應到 [**我的組織**中的人員] 設定。
- **OrganizerOnlyUserOverride**：只有會議召集人可以成為簡報者，且所有會議參與者都指定為出席者。 這個參數會對應到 [團隊] 中的 [**僅自己**] 設定。

請記住，在您設定預設值之後，會議召集人仍可在團隊中變更此設定，並選擇誰可以在排程的會議中出席。

## <a name="meeting-policy-settings---meeting-attendance-report"></a>會議原則設定-會議出席情況報告

這是每個使用者的原則。 此設定控制會議召集人是否可以下載[會議出席情況報告](teams-analytics-and-reports/meeting-attendance-report.md)。

目前您只能使用 PowerShell 來設定此原則設定。 您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。 或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。

若要讓會議召集人下載會議出席情況報告，請將**AllowEngagementReport**參數設定為 [**已啟用**]。 啟用時，會在**參與者**窗格中顯示下載報告的選項。

若要避免會議召集人下載報表，請將參數設定為 [**已停用**]。 根據預設，此設定會停用，而且無法使用下載報表的選項。

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>會議原則設定-適用于孤島模式的會議提供者

這是每個使用者的原則。 這個設定控制哪一個 Outlook 會議增益集會用於使用*孤島模式的使用者*。 您可以指定使用者是否只能使用 [團隊會議] 增益集，或是同時使用 [團隊會議] 和 [商務用 Skype 會議] 增益集，在 Outlook 中排程會議。

您只能將此原則套用到使用孤島模式的使用者，並在其團隊會議原則中，將**AllowOutlookAddIn**參數設定為**True** 。

目前您只能使用 PowerShell 來設定此原則。 您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。 或者，您可以使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，並將它指派給使用者。

若要指定使用者可以使用的會議增益集，請設定**PreferredMeetingProviderForIslandsMode**參數，如下所示：

- 將參數設定為**TeamsAndSfB** ，以在 Outlook 中同時啟用 [團隊會議增益集] 和 [商務用 Skype] 增益集。 此為預設值。
- 將參數設定為 [ **TeamsOnly** ]，只會在 Outlook 中啟用 [團隊會議] 增益集。 此原則設定可確保所有未來的會議都有小組會議加入連結。 它不會將現有的商務用 Skype 會議加入連結遷移至團隊。 此原則設定不會影響商務用 Skype 中的目前狀態、聊天、PSTN 通話或任何其他功能，這表示使用者將繼續使用商務用 Skype 來取得這些功能。

  如果您將參數設定為 [ **TeamsOnly**]，然後切換回**TeamsAndSfB**，則會啟用兩個會議增益集。 不過，請注意，現有的團隊會議加入連結不會遷移到商務用 Skype。 只有在變更之後所排程的商務用 Skype 會議，才會有商務用 Skype 會議加入連結。

## <a name="meeting-policy-settings---video-filters-mode"></a>會議原則設定-影片篩選模式

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中自訂其影片背景。

目前您只能使用 PowerShell 來設定此原則。 您可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的團隊會議原則。 或者，使用[新的 CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的團隊會議原則，然後將原則指派給使用者。

若要指定使用者是否可以在會議中自訂其影片背景，請設定**VideoFiltersMode**參數，如下所示：

|在 PowerShell 中設定值 |行為  |
|---------|---------|
|**NoFilters**     |使用者無法自訂其影片背景。|
|**BlurOnly**     |使用者可以選擇將影片背景模糊。 |
|**BlurandDefaultBackgrounds**     |使用者可以選擇將影片背景模糊，或從預設的影像集合中選擇，以做為其背景。 |
|**AllFilters**     |使用選項可讓影片背景變模糊、選擇預設的影像，或上傳自訂圖像來作為其背景。 |

> [!NOTE]
> 使用者上傳的影像不會受到小組的篩選。 當您使用 [ **AllFilters** ] 設定時，您應該擁有內部組織原則，以防止使用者上傳冒犯性或不適當的影像，或貴組織沒有許可權可供團隊會議背景使用。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [指派策略給小組中的使用者](assign-policies.md)
