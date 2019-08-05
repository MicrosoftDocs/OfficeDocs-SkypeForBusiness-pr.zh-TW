---
title: 管理會議原則
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 05/14/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords:
- ms.teamsadmincenter.meetingpolicies.overview
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- ms.teamsadmincenter.meetingpolicies.contentsharing
- ms.teamsadmincenter.meetingpolicies.general
- ms.teamsadmincenter.meetingpolicies.participantandguests
description: 瞭解如何在團隊中管理會議原則設定。
ms.openlocfilehash: bdad8f852855c8f87eb62851ddc3082026bcc0ed
ms.sourcegitcommit: f5b6270e64752298687a1abff49da58acde8e107
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/12/2019
ms.locfileid: "36184083"
---
# <a name="manage-meeting-policies-in-teams"></a>在團隊中管理會議原則

::: zone target="docs"
會議原則可用來控制會議參與者對於由您組織中的使用者排程之會議所提供的功能。 建立原則並進行變更之後, 您就可以將使用者指派給原則。 您可以在 Microsoft 團隊系統管理中心或[使用 PowerShell](teams-powershell-overview.md)管理會議原則。

您可以透過下列方式來實施原則, 這會影響使用者在會議開始之前、會議期間或會議之後的會議體驗。 

|實現類型  |說明  |
|---------|---------|
|每個召集人    |當您實施每個召集人原則時, 所有會議參與者都會繼承召集人的原則。 例如,**自動承認人員**是每個召集人原則, 並控制使用者是否要直接加入會議, 或在會議廳中等待指派原則的使用者所排程的會議。          |
|每位使用者    |當您執行每個使用者的原則時, 只會套用每個使用者的原則, 以限制召集人和/或會議參與者的特定功能。 例如, [**允許立即開會**] 是每個使用者的原則。     |
|每個召集人和每位使用者     |當您實現每個召集人與每個使用者的原則組合時, 某些功能會根據其原則和召集人原則, 限制會議參與者。 例如, [**允許雲端錄製**] 是每個召集人和每個使用者的原則。 開啟此設定可讓會議召集人與參與者開始並停止錄製。 

根據預設, 會建立名為 [全域] (組織範圍預設值) 的原則。 貴組織中的所有使用者預設都會獲指派此會議原則。 您可以對此原則進行變更, 或是建立一或多個自訂原則, 並將使用者指派給他們。 當您建立自訂原則時, 您可以允許或防止您的使用者使用某些功能, 然後將其指派給將設定套用至其中的一或多個使用者。 

## <a name="change-or-create-a-meeting-policy"></a>變更或建立會議原則

若要變更或建立會議原則, 請移至 Microsoft 團隊管理中心 >**會議** > **會議原則**。 從清單中選取原則, 或選取 [**新增原則**]。 如果您要建立新的原則, 請新增名稱和描述。 名稱不能包含特殊字元, 或長度不能超過64個字元。 選擇您的設定, 然後選取 [**儲存**]。

例如, 假設您有一組使用者, 並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則, 並停用下列設定:

在 [**音訊 & 影片**] 底下:
- 關閉雲端錄製
- 關閉 [允許 IP 影片]

[**內容共用**] 底下:
- 停用螢幕共用模式
- 關閉白板
- 關閉共用筆記

然後將原則指派給使用者。

> [!NOTE] 
> 一次只能為使用者指派一個會議原則。 

## <a name="assign-a-meeting-policy-to-users"></a>指派會議原則給使用者

如果您要將原則套用到一個使用者, 請選取左側流覽窗格中的 [**使用者**], 然後按一下使用者的顯示名稱。 在使用者的頁面上, 在 [**指派的原則**] 旁, 選取 [**編輯**]。 然後在 [**編輯使用者原則**] 窗格的 [**會議原則**] 底下, 從下拉式清單中選取 [會議原則], 然後選取 [**儲存**]。 您也可以從使用者清單指派原則。 若要這樣做, 請按一下使用者的顯示名稱左方來選取使用者。 選取 [**編輯設定**]。 接著, 在 [**編輯設定**] 窗格的 [**會議原則**] 底下, 從下拉式清單中選取原則, 然後選取 [**儲存**]。 
 
如果您要將原則套用到一個以上的使用者, 請在左側流覽窗格中選取 [**使用者**], 然後按一下使用者名稱左邊的 [**編輯設定**], 選取每個使用者。 在 [**編輯設定**] 窗格的 [**會議原則**] 底下, 從下拉式清單中選取原則, 然後選取 [**儲存**]。
 
您也可以將會議原則指派給一或多位使用者, 如下所示:

1. 移至**Microsoft 團隊系統管理中心** > **會議** > **會議原則**。
2. 按一下原則名稱左方, 選取原則。
3. 選取 [**管理使用者**]。
4. 在 [**管理使用者**] 窗格中, 依 [顯示名稱] 或 [使用者名稱] 搜尋使用者, 選取名稱, 然後選取 [**新增**]。 針對您要新增的每個使用者重複此步驟。
5. 完成新增使用者後, 請選取 [**儲存**]。
 
> [!NOTE] 
> 如果使用者已獲指派, 您就無法刪除原則。 您必須先將其他原則指派給所有受影響的使用者, 然後才能刪除原始原則。
 
## <a name="meeting-policy-settings"></a>會議原則設定

當您在 [**會議原則**] 頁面上選取現有的原則, 或選取 [**新增原則**] 來新增原則時, 您可以設定下列各項的設定。

- [一般](#meeting-policy-settings---general)
- [音訊 & 影片](#meeting-policy-settings---audio--video)
- [內容共用](#meeting-policy-settings---content-sharing)
- [參與者 & 來賓](#meeting-policy-settings---participants--guests)

::: zone-end 

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>會議原則設定-一般

- [允許頻道中的 [立即開會]](#allow-meet-now-in-channels)
- [允許私人 [立即開會] (即將推出)](#allow-private-meet-now-coming-soon)
- [允許 Outlook 增益集](#allow-the-outlook-add-in)
- [允許頻道會議排程](#allow-channel-meeting-scheduling)
- [允許排程私人會議](#allow-scheduling-private-meetings)

### <a name="allow-meet-now-in-channels"></a>允許頻道中的 [立即開會]

這是針對每個使用者的原則, 在會議開始之前就會套用。 此設定控制使用者是否可在團隊頻道中啟動零星會議。 如果您開啟此選項, 當使用者在團隊頻道中張貼訊息時, 使用者可以按一下撰寫方塊下的 [**立即開會**], 以在頻道中啟動即席會議。

![顯示郵件下方 [立即開會] 圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-private-meet-now-coming-soon"></a>允許私人 [立即開會] (即將推出)

這是針對每個使用者的原則, 在會議開始之前就會套用。 此設定可控制使用者是否能開始即席私人會議。  

### <a name="allow-the-outlook-add-in"></a>允許 Outlook 增益集

這是針對每個使用者的原則, 在會議開始之前就會套用。 此設定控制團隊會議是否可在 Outlook 中排程 (Windows、Mac、web 及行動裝置)。

![螢幕擷取畫面顯示排程新會議的功能](media/meeting-policies-outlook-add-in.png)

如果您關閉此功能, 使用者在 Outlook 中建立新會議時, 將無法排程團隊會議。 例如, 在 Windows 版 Outlook 中, 新的 [**小組會議**] 選項不會顯示在功能區中。

### <a name="allow-channel-meeting-scheduling"></a>允許頻道會議排程

這是針對每個使用者的原則, 在會議開始之前就會套用。 此設定控制使用者是否可在團隊頻道中排程會議。  如果您關閉此功能, 當使用者在團隊頻道中開始會議, 且在小組中的會議排程會議時, 使用者將無法使用 [**排程會議**] 選項, 使用者就無法使用 [**選取要開會的頻道**] 選項。

![顯示團隊中 [排程 meetion] 選項的螢幕擷取畫面](media/meeting-policies-schedule-a-meeting.png)

![顯示 [選取要開會的頻道] 選項的螢幕擷取畫面](media/meeting-policies-select-a-channel-to-meet-in.png)

### <a name="allow-scheduling-private-meetings"></a>允許排程私人會議

這是針對每個使用者的原則, 在會議開始之前就會套用。 此設定可控制使用者是否可以在小組中排程私人會議。 如果會議不是發佈至小組中的頻道, 就是私人的。

請注意, 如果您關閉 [**允許排程私人會議**] 和 [**允許頻道會議排程**], 則無法使用 [**排程會議**] 選項, 而且使用者將無法在小組中排程會議。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>會議原則設定-音訊 & 影片

- [允許進行文字](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [允許 IP 影片](#allow-ip-video)
- [媒體位元速率 (KBs)](#media-bit-rate-kbs)
- [啟用即時輔助字幕 (即將推出)](#enable-live-captions-coming-soon)

### <a name="allow-transcription"></a>允許進行文字

這是每個組織單位和每個使用者原則的組合。 此設定控制在播放會議錄製期間是否可使用 [標題] 和 [操作模式] 功能。 如果您關閉此功能, 則在播放會議錄製期間將無法使用 [**搜尋**] 和 [**抄送**] 選項。 開始錄製需要已開啟此設定的人員, 才能讓錄製也包含操作。 

請注意, 目前只有將團隊中的語言設定為英文, 且在會議中朗讀英文的使用者, 才支援會議記錄會議。

![螢幕擷取畫面顯示會議中的 [工具] 選項](media/meeting-policies-transcription.png)

### <a name="allow-cloud-recording"></a>允許雲端錄製

這是每個組織單位和每個使用者原則的組合。 此設定控制是否可以錄製此使用者的會議。 如果參與者已開啟該原則設定, 且是來自同一個組織的經過驗證的使用者, 則錄製可以由會議召集人或其他會議參與者啟動。

貴組織外部人員 (例如同盟與匿名使用者) 無法啟動錄製。 來賓使用者無法啟動或停止錄製。 

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

我們來看看下列範例。

|使用者名 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 虛假 |
|Amanda | Location1MeetingPolicy | 滿足|
|約翰 (外部使用者) | 不適用 | 不適用|

依 Daniela 組織的會議無法錄製, 且 Amanda 已啟用原則設定的使用者, 無法錄製由 Daniela 組織的會議。 您可以錄製由 Amanda 組織的會議, 但 Daniela, 誰已停用原則設定, 而誰是外部使用者, 就無法錄製由 Amanda 組織的會議。

若要深入瞭解雲端會議錄製, 請參閱[小組雲端會議錄製](cloud-recording.md)。

### <a name="allow-ip-video"></a>允許 IP 影片

這是每個組織單位和每個使用者原則的組合。 影片是會議的關鍵元件。 在某些組織中, 系統管理員可能會想要進一步控制哪些使用者的會議擁有影片。 此設定控制是否能在使用者託管的會議中以及使用者開始的1:1 通話和群組通話中開啟影片。 在已啟用此原則的使用者組織的會議中, 如果會議參與者也已啟用原則, 則允許會議參與者在會議中進行影片共用。 沒有指派任何原則的會議參與者 (例如匿名及同盟參與者) 會繼承會議召集人的原則。

![螢幕擷取畫面顯示使用音訊和影片設定的會議](media/meeting-policies-audio-video-settings.png)

我們來看看下列範例。

|使用者名 |會議原則  |允許 IP 影片 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足        |
|Amanda    | Location1MeetingPolicy        | 虛假      |

由 Daniela 託管的會議允許開啟影片。 Daniela 可以加入會議, 然後開啟 [影片]。 Amanda 無法在 Daniela 的會議中開啟影片, 因為 Amanda 的原則設定為 [不允許視頻]。 Amanda 可以查看會議中其他參與者所共用的影片。

在由 Amanda 託管的會議中, 任何人都無法開啟影片, 不論指派的是何種影片原則。 這表示 Daniela 無法在 Amanda 的會議中開啟影片。  

如果 Daniela 呼叫 Amanda 的 [影片], Amanda 只能以音訊接聽通話。  通話連線時, Amanda 可以看到 Daniela 的影片, 但無法開啟影片。 如果 Amanda 呼叫 Daniela, Daniela 可以使用影片和音訊接聽通話。 當通話連線時, Daniela 可以視需要開啟或關閉她的影片。

### <a name="media-bit-rate-kbs"></a>媒體位元速率 (KBs)

這是每個使用者的原則。 此設定會針對使用者的通話和會議中的音訊、影片及影片式應用程式共用傳輸, 決定媒體位元速率。 它適用于通話或會議中的使用者的上行與下行媒體遍歷。 此設定可讓您精細控制貴組織中的頻寬管理。 根據使用者所需的會議案例, 我們建議您有足夠的頻寬來提供良好的品質體驗。 最小值為 30 Kbps, 而最大值則視會議案例而定。 若要深入瞭解在小組中提供優質會議、通話及即時事件的最小建議頻寬, 請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。

如果沒有足夠的頻寬可供會議使用, 參與者會看到指出網路品質不佳的訊息。

如果會議需要最高品質的影片體驗, 例如 CEO 董事會會議和小組現場活動, 我們建議您將頻寬設定為 10 Mbps。 即使已設定最大的體驗, 小組媒體堆疊也會在檢測到某些網路條件時適應低頻寬情況 (視情況而定)。 

### <a name="enable-live-captions-coming-soon"></a>啟用即時輔助字幕 (即將推出)

這是針對每個使用者的原則, 且適用于會議期間。 如果此設定為 [開啟], 使用者會看到在會議期間顯示標題的選項。

<a name="bkcontentsharing"> </a>

## <a name="meeting-policy-settings---content-sharing"></a>會議原則設定-內容共用

- [螢幕共用模式](#screen-sharing-mode)
- [允許參與者授與要求控制](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者授與或要求控制](#allow-an-external-participant-to-give-or-request-control)
- [允許 PowerPoint 共用](#allow-powerpoint-sharing)
- [允許白板](#allow-whiteboard)
- [允許共用筆記](#allow-shared-notes)
- [允許在會議中聊天 (即將推出)](#allow-chat-in-meetings-coming-soon)

### <a name="screen-sharing-mode"></a>螢幕共用模式

這是每個組織單位和每個使用者原則的組合。 此設定控制使用者的會議是否允許桌面和/或視窗共用。 沒有指派任何原則的會議參與者 (例如, 匿名、來賓、B2B 及同盟參與者) 會繼承會議召集人的原則。

|設定值 |行為  |
|---------|---------|
|**整個畫面**    | 在會議中允許進行完整的桌面共用和應用程式共用 |
|**單一應用程式**   | 允許在會議中共用應用程式        |
|**禁止**     |在會議中關閉螢幕共用和應用程式共用。       |

我們來看看下列範例。

|使用者名 |會議原則 |螢幕共用模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個畫面 |
|Amanda   | Location1MeetingPolicy  | 禁止 |

Daniela 託管的會議可讓會議參與者共用整個螢幕或特定的應用程式。 如果 Amanda 加入 Daniela 的會議, Amanda 無法共用她的螢幕或特定的應用程式, 因為她的原則設定已停用。 在由 Amanda 託管的會議中, 不論指派給他們的螢幕共用模式原則為何, 都不允許任何人共用其螢幕或單一應用程式。 這表示 Daniela 無法在 Amanda 的會議中共用她的螢幕或單一應用程式。  

目前, 如果使用者使用的是 Google Chrome, 就無法在團隊會議中播放影片或共用其螢幕。

### <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者授與要求控制

這是每個使用者的原則。 此設定可控制使用者是否可以將共用桌面或視窗控制權授與其他會議參與者。 若要授與控制權, 請將游標暫留在畫面頂端。 

如果使用者已開啟此設定, 則 [取得**控制權**] 選項會顯示在共用會話的上方列中。 

![顯示 [授與控制權] 選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

如果使用者的設定已關閉, 則無法使用 [**提供控制權**] 選項。

![螢幕擷取畫面顯示 [授與控制權] 選項無法使用](media/meeting-policies-give-control-not-available.png)

我們來看看下列範例。

|使用者名 |會議原則  |允許參與者授與要求控制 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Babek    | Location1MeetingPolicy        | 虛假   |

Daniela 可以將共用桌面或視窗控制權提供給依 Babek 組織的會議中的其他參與者, 但 Babek 無法將控制權授與其他參與者。

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者授與或要求控制

這是每個使用者的原則。 此設定會控制會議中的外部參與者是否可以將共用的桌面或視窗控制權提供給會議中的其他參與者。 團隊會議中的外部參與者可以分類如下:  

   - 匿名使用者
   - 來賓使用者  
   - B2B 使用者
   - 聯盟使用者  

聯盟使用者是否可在共用時授與外部使用者控制權, 由允許外部參與者在其組織中**提供或要求控制**設定。

### <a name="allow-powerpoint-sharing"></a>允許 PowerPoint 共用

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中共用 PowerPoint 投影片投影片。 外部使用者 (包括匿名、來賓及同盟使用者) 繼承會議召集人的原則。

我們來看看下列範例。

|使用者名 |會議原則  |允許 PowerPoint 共用 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy        | 虛假   |

Amanda 無法在會議中共用 PowerPoint 投影片卡座, 即使她是會議召集人也一樣。 Daniela 可以共用 PowerPoint 投影片卡座, 即使會議是透過 Amanda 來組織。 Amanda 可以在會議中查看其他人所共用的 PowerPoint 投影片, 即使她無法共用 PowerPoint 投影片投影片也一樣。

### <a name="allow-whiteboard"></a>允許白板

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中共用白板。 外部使用者 (包括匿名、B2B 及同盟使用者) 繼承會議召集人的原則。 

我們來看看下列範例。

|使用者名 |會議原則  |允許白板|
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy        | 虛假   |

Amanda 無法在會議中共用白板, 即使她是會議召集人也一樣。 Daniela 可以共用白板, 即使會議是由 Amanda 來組織。  

### <a name="allow-shared-notes"></a>允許共用筆記

這是每個使用者的原則。 此設定可控制使用者是否可以在會議中建立和共用筆記。 外部使用者 (包括匿名、B2B 及同盟使用者) 繼承會議召集人的原則。 目前只有超過20名參與者的會議才支援 [**會議記事**] 索引標籤。 

我們來看看下列範例。

|使用者名 |會議原則  |允許共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | 滿足       |
|Amanda   | Location1MeetingPolicy | 虛假 |

Daniela 可以在 Amanda 的會議中記錄筆記, 而 Amanda 無法在任何會議中記錄筆記。

### <a name="allow-chat-in-meetings-coming-soon"></a>允許在會議中聊天 (即將推出)

這是每個召集人原則。 此設定控制是否允許在使用者的會議中使用會議聊天。 

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---participants--guests"></a>會議原則設定-參與者 & 來賓

這些設定會控制哪些會議參與者會在會議廳中等待, 並在會議遭到准許前進行會議, 以及在會議中允許的參與程度。

- [自動承認人員](#automatically-admit-people)
- [允許匿名人員開始會議](#allow-anonymous-people-to-start-a-meeting)
- [允許撥入使用者略過大廳](#allow-dial-in-users-to-bypass-the-lobby-coming-soon)
- [允許召集人覆寫會議廳設定](#allow-organizers-to-override-lobby-settings-coming-soon)

> [!NOTE]
>加入會議的選項會根據每個團隊群組的設定和連接方法而有所不同。 如果您的群組有音訊會議, 且使用它來連接, 請參閱[Office 365 中的音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果您的 [小組] 群組沒有音訊會議, 請參閱[在小組中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

### <a name="automatically-admit-people"></a>自動承認人員

這是每個召集人原則。 此設定控制使用者是否直接加入會議, 或在大廳等候, 直到經過驗證的使用者准許。

![螢幕擷取畫面顯示與大廳中的使用者進行的會議](media/meeting-policies-lobby.png)

 會議召集人可以按一下會議邀請中的 [**會議選項**], 針對每個會議所排程的會議變更此設定。 **(即將推出)**
  
|設定值  |加入行為 |
|---------|---------|
|**人員**   |所有會議參與者都能直接加入會議, 不需要在大廳等候。 這包括經過驗證的使用者、聯盟使用者、來賓、匿名使用者, 以及透過電話撥入的人員。       |
|**貴組織和聯盟組織中的每個人**     |組織內經過驗證的使用者, 包括來賓使用者以及來自同盟組織的使用者, 直接加入會議, 不需在大廳等候。  在大廳由手機撥入的匿名使用者和使用者。   |
|**貴組織中的每個人**    |從組織內的經過驗證的使用者 (包括來賓使用者), 直接加入會議, 不需在大廳等候。  在大廳以電話撥入的聯盟使用者、匿名使用者和使用者。           |

### <a name="allow-anonymous-people-to-start-a-meeting"></a>允許匿名人員開始會議

這是每個召集人原則。 此設定會控制匿名人員 (包括 B2B) 與同盟使用者, 是否可在沒有已驗證的使用者的情況下, 從出席中的組織加入使用者的會議。 

![螢幕擷取畫面顯示等候使用者的訊息](media/meeting-policies-anonymous-user-lobby.png)

以下是在會議中有驗證使用者的情況下匿名人員的加入行為。

|允許匿名人員開始會議  |自動承認人員 |匿名人員的加入行為 |
|---------|---------|---------|
|滿足    | 人員      | 直接加入         |
|   | 貴組織中的每個人       | 在大廳等候        |
|   | 貴組織和聯盟組織中的每個人       | 在大廳等候         |
|虛假    | 人員        | 直接加入        |
|   | 貴組織中的每個人     | 在大廳等候        |
|   | 貴組織和聯盟組織中的每個人      | 在大廳等候         |

以下是在會議中沒有經過驗證的使用者時, 匿名人員的加入行為。

|允許匿名人員開始會議 |自動承認人員  |匿名人員的加入行為 |
|---------|---------|---------|
|滿足    | 人員      | 直接加入         |
|   | 貴組織中的每個人       | 在大廳等候        |
|   | 貴組織和聯盟組織中的每個人       | 在大廳等候         |
|虛假    | 人員        | 在大廳等候。 當第一個經過驗證的使用者加入會議時, 系統會自動准許使用者。        |
|   | 貴組織中的每個人     |在大廳等候         |
|   | 貴組織和聯盟組織中的每個人      | 在大廳等候         |

### <a name="allow-dial-in-users-to-bypass-the-lobby-coming-soon"></a>允許撥入使用者略過大廳 (即將推出)

這是每個召集人原則。 此設定控制由手機撥入的人員是否直接加入會議, 或無論是否已**自動准許 [人員**] 設定, 也會在大廳中等待。

以下是透過電話撥入的人員的加入行為。

|允許撥入使用者略過大廳  |自動承認使用者  |撥入之人的加入行為 |
|---------|---------|---------|
|滿足    | 人員      | 直接加入         |
|   | 貴組織中的每個人       | 直接加入        |
|   | 貴組織和聯盟組織中的每個人       | 直接加入         |
|虛假    | 人員        | 直接加入        |
|   | 貴組織中的每個人     |在大廳等候         |
|   | 貴組織和聯盟組織中的每個人      | 在大廳等候         |

### <a name="allow-organizers-to-override-lobby-settings-coming-soon"></a>允許召集人覆寫會議廳設定 (即將推出)

這是每個召集人原則。 此設定會控制會議召集人是否可以覆寫管理員設定的 [大廳] **** 設定,**讓撥入使用者**在排程新會議時略過大廳。 

會議召集人可以按一下會議邀請中的 [**會議選項**], 以變更每個會議排程的會議廳設定。 

此設定會影響會議召集人是否可以針對召集人排程的每個會議變更 [**自動承認人員**] 設定。

|允許召集人覆寫會議廳設定  |自動承認人員  |行為 |
|---------|---------|---------|
|滿足    | 人員      | 召集人可以將設定變更為任何其他值。 |
|   | 貴組織中的每個人       | 召集人可以將設定變更為任何其他值。|
|   | 貴組織和聯盟組織中的每個人       | 召集人可以將此變更為任何其他值。         |
|虛假    | 人員        | 召集人可以將設定變更為任何其他值。|
|   | 貴組織中的每個人     |召集人可以將設定變更為**貴組織中的所有人**。 |
|   | 貴組織和聯盟組織中的每個人      | 召集人無法覆蓋前廳流覽設定。 |

以下說明此設定會如何影響會議召集人是否可以針對召集人排程的每個會議, 將 [**允許撥入使用者] 變更為 [略過大廳**] 設定。
    
|允許召集人覆寫會議廳設定  |允許撥入使用者略過大廳  |行為 |
|---------|---------|---------|
|滿足    |  滿足        | 召集人可以將設定變更為 False。       |
|滿足      | 虛假         | 召集人可以將設定變更為 True。        |
|虛假     | 滿足        |召集人可以將設定變更為 False。         |
|虛假      |虛假          |召集人無法覆蓋會議廳設定, 而且無法允許撥入使用者繞過會議中的大廳。        |

[整篇文章](meeting-policies-in-teams.md)

## <a name="related-topics"></a>相關主題
[小組中的訊息原則](messaging-policies-in-teams.md)
