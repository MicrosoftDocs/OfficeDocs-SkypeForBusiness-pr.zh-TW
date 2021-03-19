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
- m365initiative-meetings
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
description: 瞭解如何在 Teams 中管理會議策略設定。 使用策略設定來控制提供給會議參與者的功能，供使用者排程的會議使用。
ms.openlocfilehash: cdeadfd119ae0a1aa1d1f42af84d2c30ac014584
ms.sourcegitcommit: b8c4536db4ce9ea682e247d6c8ee7019b08462f8
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/18/2021
ms.locfileid: "50875163"
---
# <a name="manage-meeting-policies-in-teams"></a>管理 Teams 中的會議原則

::: zone target="docs"
使用會議策略來控制貴組織中使用者排程會議的會議參與者可使用的功能。 您可以使用全域 (全組織的預設) 自動建立或建立及指派自訂策略。 您可以在 Microsoft Teams 系統管理中心或使用 [PowerShell 管理會議政策](teams-powershell-overview.md)。

> [!NOTE]
> 有關使用角色管理會議簡報者和出席者許可權的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以用下列方式執行策略，這會影響會議開始前、會議期間或會議後的使用者會議體驗。

|實現類型  |說明  |
|---------|---------|
|每個召集人    |當您執行每個召集人的政策時，所有會議參與者會繼承召集人的政策。 例如， **自動允許人員** 是每個召集人的政策。 它控制使用者是直接加入會議，或是在大廳等候指派策略的使用者排程的會議。          |
|每個使用者    |當您執行每個使用者原則時，只會使用每個使用者原則來限制召集人和/或會議參與者的某些功能。 例如， **在頻道中允許現在開會** 是每個使用者的政策。     |
|每個召集人和每個使用者     |當您將每個召集人和每個使用者策略組合在一起時，根據會議參與者的政策和召集人的政策，某些功能會受到限制。 例如， **允許雲端錄製** 是每個召集人和每個使用者的政策。 開啟此設定，讓使用者開始和停止錄製。

您可以編輯全域原則中的設定，或建立並指派一或多個自訂策略。 除非您建立並指派自訂策略，否則使用者將取得全域原則。

> [!NOTE]
> 如果使用者已啟用音訊會議授權，或使用者允許進行音訊會議，則會議詳細資料將不可用，則會議詳細資料將可以使用。

## <a name="create-a-custom-meeting-policy"></a>建立自訂會議策略

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。
2. 選取 [新增 **]**。
3. 輸入原則的名稱和描述。 名稱不能包含特殊字元，且長度不可超過 64 個字元。
4. 選擇您想要的設定。
5. 選取 **儲存**。

例如，假設您有多位使用者，並且想要限制其會議所需的頻寬量。 您可以建立名為「有限頻寬」的新自訂原則，並停用下列設定：

在 [音訊與視訊] 下：

- 關閉 [允許雲端錄製]。
- 關閉 [允許 IP 視訊]。

在 [內容共用] 下：

- 停用 [螢幕畫面分享模式]。
- 關閉 [允許白板]。
- 關閉 [允許共用記事]。

然後，將原則指派給使用者。

## <a name="edit-a-meeting-policy"></a>編輯會議政策

您可以編輯全域原則和您建立的任何自訂策略。

1. 在 Microsoft Teams 系統管理中心的左側流覽中，前往 **會議**  >  **會議政策**。
2. 按一下策略名稱的左側以選取該策略， **然後選取** 編輯 。
3. 從此處，進行您需要的變更。
4. 選取 **儲存**。

> [!NOTE]
> 一次只能指派一個會議策略給使用者。

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果使用者已指派給使用者，則無法刪除該策略。 您必須先指派不同的策略給所有受影響的使用者，然後您可以刪除原始策略。

## <a name="meeting-policy-settings"></a>會議策略設定

在會議政策頁面上選取現有的 **策略，或****選取新增** 以新增策略。 設定下列各項的設定。

- [一般](#meeting-policy-settings---general)
- [音訊&影片](#meeting-policy-settings---audio--video)
- [內容共用](#meeting-policy-settings---content-sharing)
- [參與者&來賓](#meeting-policy-settings---participants--guests)

::: zone-end

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>會議策略設定 - 一般

- [允許現在在頻道中開會](#allow-meet-now-in-channels)
- [允許 Outlook 附加元件](#allow-the-outlook-add-in)
- [允許頻道會議排程](#allow-channel-meeting-scheduling)
- [允許排程私人會議](#allow-scheduling-private-meetings)
- [允許現在在私人會議中開會](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>允許現在在頻道中開會

允許 **現在開會** 是一項每個使用者原則，在會議開始之前即適用。 此設定可控制使用者是否可以在 Teams 頻道中啟動非計畫的會議。 如果您開啟此設定，使用者可以選取會議按鈕來開始非計畫的會議，或在頻道中排程會議。 預設值為 True。

![顯示訊息下方的現在開會圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>允許 Outlook 附加元件

允許 Outlook 附加元件是每個使用者原則，且在會議開始之前適用。 此設定可控制 Teams 會議是否可以從 Outlook (Windows、Mac、Web 和行動) 。

![顯示排程新會議之能力的螢幕擷取畫面](media/meeting-policies-outlook-add-in.png)

如果您關閉此功能，使用者就無法排程。 團隊在 Outlook 中建立新會議時的會議。 例如，在 Windows 上的 Outlook 中，功能區中不會顯示新增 **Teams** 會議選項。

### <a name="allow-channel-meeting-scheduling"></a>允許頻道會議排程

使用現有的 AllowChannelMeeting 排程策略，控制可在小組頻道日曆上建立的事件種類。 這是每個使用者原則，在會議開始之前適用。 此設定可控制使用者是否可以在 Teams 頻道中排程會議。 根據預設，此設定會開啟。

如果關閉此政策，使用者無法建立新的頻道會議。 不過，活動召集人可以編輯現有的頻道會議。

排程會議將會停用。

 ![Teams 中的排程會議選項](media/schedule-meeting-option.png)

頻道選取範圍已停用。

![選取要排程會議之頻道的日曆選項。](media/meeting-policies-select-a-channel-to-meet-in.png)

在頻道文章頁面中，下列功能將會停用：

- **頻道回復撰寫** 方塊上的排程會議按鈕。
  ![排程會議按鈕回復撰寫方塊](media/schedule-meeting-disabled-in-chat2.png)
  
- **在頻道標題** 上排程會議按鈕。
  ![在頻道標題中排程會議按鈕](media/schedule-now-in-header.png)

在頻道日曆中：

- **頻道日曆標題** 上的新增活動按鈕將會停用。
  ![頻道日曆標題上的按鈕已停用](media/add-new-event-disabled.png)

- 使用者無法拖曳並選取頻道日曆上的時間區塊，以建立頻道會議。

- 使用者無法使用鍵盤快速鍵在頻道日曆上建立會議。

在系統管理中心：

頻道日曆應用程式會顯示在應用程式許可權政策頁面上 **的 Microsoft App** 區段。

 ![Teams 系統管理中心中的應用程式許可權政策](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>允許排程私人會議

排程私人會議是每個使用者原則，在會議開始之前適用。 此設定可控制使用者是否可以在 Teams 中排程私人會議。 當會議未發佈到團隊中的頻道時，會議是私人的。

如果您 **關閉允許排** 程私人會議和允許頻道會議排程，Teams 中的使用者會停用新增必要的出席者及新增頻道選項。  根據預設，此設定會開啟。

### <a name="allow-meet-now-in-private-meetings"></a>允許現在在私人會議中開會

這是每個使用者原則，在會議開始之前適用。 此設定可控制使用者是否可以啟動非計畫的私人會議。 根據預設，此設定會開啟。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>會議策略設定 - 音訊&影片

- [允許文字翻譯](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [IP 音訊模式](#mode-for-ip-audio)
- [IP 影片模式](#mode-for-ip-video)
- [允許 IP 視訊](#allow-ip-video)
- [媒體位元速率 (Kbs) ](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>允許文字翻譯

此政策會開啟即時轉錄。 允許抄寫是每個使用者的政策。 此設定可控制是否可以轉譯此特定小組的會議。

![會議政策中的文字翻譯選項](media/live-transcription.png)

即時文字翻譯會即時顯示 Teams 會議期間的語音對文字內容。 文字會顯示在會議影片旁邊，包括演講者的姓名和時間戳記。 若要深入瞭解，請參閱在 Teams 會議中 [查看即時文字翻譯](https://support.microsoft.com/office/view-live-transcription-in-a-teams-meeting-7a1401ec-73b4-431d-875a-8b6af82b3e15)。

Teams 桌面用戶端目前支援即時抄寫功能。 英文口語支援文字翻譯功能。 會議結束後，可在 Teams 桌面或 Web 上查看文字記錄。

以下說明允許抄寫 **和****允許雲端錄製** 策略設定如何共同作業。 下表說明這些設定的值和會議行為。

|允許文字翻譯|允許雲端錄製|行為|
|---------|---------|---------|
|**已上**|**已上**|Teams **會議提供** 開始文字翻譯選項。 會議召集人或會議參與者可以開始和停止文字翻譯。 Teams **會議** 提供開始錄製選項。 會議召集人或會議參與者可以開始和停止錄製。 |
|**已上**|**關閉**|Teams **會議提供** 開始文字翻譯選項。 Teams **會議中** 無法使用開始錄製選項。 |
|**關閉**|**已上**|Teams **會議** 提供開始錄製選項。 Teams **會議中** 無法使用開始文字翻譯選項。|
|**關閉**|**關閉**|Teams 會議中無法錄製和錄製文字。  |

### <a name="allow-cloud-recording"></a>允許雲端錄製

允許雲端錄製是由每個使用者策略控制。 此設定可控制使用者是否可以錄製。 如果會議召集人或另一個會議參與者的特定策略設定已開啟，且他們是來自與召集人同一個組織的已驗證使用者，就可以開始錄製。

組織外部人員 ，例如聯盟和匿名使用者，無法開始錄製。 來賓使用者無法開始或停止錄製。

![錄製選項](media/meeting-policies-recording.png)

讓我們來看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 關閉 |
|艾曼達 | 位置1MeetingPolicy | 已上|
|John (外部使用者)  | 不適用 | 不適用|

Daniela，即使她是召集人，也無法錄製，因為她的政策已設定為關閉。 已啟用策略設定的 Amanda 可以錄製會議，包括由 Daniela 組織的會議。 如果 Amanda 要組織會議，她將能夠錄製該會議。 不過，已停用策略設定和外部使用者之 John 的 Daniela 無法錄製該會議。

若要深入瞭解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

### <a name="mode-for-ip-audio"></a>IP 音訊模式

IP 音訊模式是每個使用者的策略。 此設定可控制是否可以在會議和群組通話中開啟音訊。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外發和傳入音訊**    |會議允許外發和傳入音訊。 這是預設設定。 |
|**禁用**     |會議會關閉外發和傳入音訊。     |

如果使用者設為 **已停用** ，該使用者仍然可以排程和組織會議，但無法使用音訊。 若要加入會議，使用者必須透過公用交換電話網絡 (PSTN) ，或讓會議電話以電話加入使用者。 未指派任何策略的會議 (例如，匿名) 預設會啟用此設定為外發和傳入音訊。  在 Teams 行動用戶端上，如果這項設定已停用，使用者必須透過 PSTN 撥入會議。

此設定不適用於 1：1 通話。 若要限制 1：1 通話，請設定 Teams [通話政策](teams-calling-policy.md) ，並關閉撥打 **私人電話** 設定。 這項設定也不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

此設定尚未適用于 Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD) 環境。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="mode-for-ip-video"></a>IP 影片模式

IP 影片模式是每個使用者的策略。 此設定可控制是否可以在會議和群組通話中開啟視像。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外發和傳入視**    | 會議預設為允許外發和傳入視像。 |
|**禁用**     | 會議會關閉外發和傳入視像。 在 Teams 行動用戶端上，使用者無法共用會議中的影片或相片。 <br><br>請注意，如果 **IP 音訊模式** 已停用， **則 IP 視** 障模式也會維持停用狀態。  |

如果使用者設定為 **已停用，** 該使用者無法開啟視片或觀看其他會議參與者共用的影片。 未指派任何策略的會議 (例如，匿名) 預設會啟用此設定為外) **入視。**

這項設定不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

此設定尚未適用于 Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD) 環境。

> [!NOTE]
> 請記住，此設定同時控制外發和傳入視音訊，而允許 **IP 視** 區設定則控制外發視。 若要深入瞭解，請參閱 [優先使用哪一個 IP 視視策略設定？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視像](#manage-audiovideo-for-meeting-participants)。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="allow-ip-video"></a>允許 IP 視訊

允許 IP 影片是每個召集人和每個使用者策略的組合。 視音訊是會議的重要元件。 在某些組織中，系統管理員可能會想要更多控制哪些使用者的會議有視像。 此設定可控制是否可以在使用者主持的會議以及使用者啟動的 1：1 和群組通話中開啟視訊。 在 Teams 行動用戶端上，此設定可控制使用者是否可以在會議中共用相片和影片。

由已啟用此策略設定的使用者所組織的會議，如果參與者也已啟用策略設定，則允許會議參與者在會議中共用視像。 未指派任何策略的會議參與者 (例如，匿名) 會繼承會議召集人的政策。

> [!NOTE]
> 請記住，此設定會控制外發視視， **而 IP 視** 區模式設定則同時控制外發和傳入視音訊。 若要深入瞭解，請參閱 [優先使用哪一個 IP 視視策略設定？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視像](#manage-audiovideo-for-meeting-participants)。

| Teams 桌面和 Web 用戶端 |Teams 行動用戶端  |
|:-------:|:-------:|
|![螢幕擷取畫面顯示桌面使用音訊/視像設定加入會議](media/meeting-policies-audio-video-settings.png)    |![螢幕擷取畫面顯示在行動版上使用音訊/視像設定加入會議](media/meeting-policies-mobile-join.png)          |

讓我們來看看下列範例。

|使用者 |會議原則  |允許 IP 視訊 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達    | 位置1MeetingPolicy        | 關閉      |

Daniela 主持的會議允許開啟視像。 Daniela 可以加入會議並開啟視像。 Amanda 無法開啟 Daniela 會議中的視像，因為 Amanda 的政策設定為不允許視音訊。 Amanda 可以看到會議中其他參與者共用的影片。

在由 Amanda 主持的會議中，無論指派的視音訊策略如何，沒有人可以開啟視音訊。 這表示 Daniela 無法開啟 Amanda 會議中的視像。  

如果 Daniela 以視音訊通話給 Amanda，則 Amanda 只能用音訊接聽電話。 當通話接通時，Amanda 可以看到 Daniela 的視像，但無法開啟視像。 如果 Amanda 打電話給 Daniela，Daniela 可以使用視像和音訊接聽電話。 通話接通後，Daniela 可以視需要開啟或關閉視像。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪一個 IP 視視策略設定優先

對於使用者，視像的最嚴格政策設定會優先使用。 以下是一些範例。

|允許 IP 視訊|IP 影片模式|會議體驗|
|---------|---------|---------|
|召集人 **：On**<br><br>參與者 **：On** |參與者： **已停用**        |IP **視視模式設定** 會優先使用。 指派此政策的參與者無法開啟或觀看其他人共用的影片。|
|召集人 **：On**<br><br>參與者 **：On** |參與者： **已啟用外發和傳入視訊**          |指派此政策的參與者可以開啟或觀看其他人共用的影片。         |
|召集人 **：On**<br><br>參與者： **關閉** |參與者： **已啟用外發和傳入視訊**         |允許 **IP 視像** 設定優先。 參與者只能看到內送影片，而且無法傳送外寄影片。         |
|召集人 **：On**<br><br>參與者： **關閉** |參與者： **已停用**         |IP **視視模式設定** 會優先使用。 參與者看不到傳入或外發視。|
|召集人： **關閉**    |       |允許 **IP 視** 像設定會優先使用，因為召集人已關閉該設定。 在指派此策略的使用者所組織的會議中，沒有人可以開啟視像。         |

### <a name="manage-audiovideo-for-meeting-participants"></a>管理會議參與者的音訊/視像

|如果您想要...  |設定下列策略設定  |
|---------|---------|
|為會議參與者停用音訊和視像  |IP 音訊模式： **已停用**<br> IP 影片模式： **已停用**<br>允許 IP 影片：N/A       |
|只為會議參與者啟用傳入視音訊  |IP 音訊模式： **已啟用外接和傳入音訊**<br> IP 影片模式： **已啟用外接和傳入視訊**<br>允許 IP 影片： **關閉**       |
|針對會議參與者停用視 (參與者只有音訊) |  IP 音訊模式： **啟用外接和傳入音訊**<br> IP 影片模式： **已停用**<br>允許 IP 影片：N/A
|為會議參與者啟用音訊和視音訊    |IP 音訊模式： **已啟用** 外 (內) <br> IP 視訊模式： **已啟用** 外 (內) <br>允許 IP 視訊 **： (** 預設)     |

會議召集人原則與使用者原則之間的最嚴格原則會適用。 例如，如果召集人有限制視音訊的政策，而使用者的政策沒有限制視音訊，會議參與者會繼承會議召集人的政策，而且無法存取會議中的視像。 這表示他們只能使用音訊加入會議。

> [!NOTE]
> 當使用者啟動群組通話以使用電話加入時，不會顯示使用電話 **進行** 音訊畫面。 這是我們正在努力解決的已知問題。 若要解決此問題， **請選取其他** 連接選項下的 **電話音訊**。  

#### <a name="teams-mobile-clients"></a>Teams 行動用戶端

對於 Teams 行動用戶端上的使用者，會議期間共用相片和影片的能力取決於允許 IP **視** 像或 **IP 視像模式設定** 。 視哪一個策略設定為優先，無法共用影片和相片。 這不會影響螢幕共用，因為螢幕共用是使用個別的螢幕 [共用模式設定來](#screen-sharing-mode) 設定。 此外，您可以設定 [Teams 行動](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 能力政策，以防止行動使用者以行動網路連接使用 IP 視像，這表示他們必須使用 WiFi 連接。

### <a name="media-bit-rate-kbs"></a>媒體位元速率 (Kbs) 

這是每個使用者的策略。 此設定會決定使用者通話和會議中音訊、視像和視像應用程式共用傳輸的總媒體位率。 它同時適用于通話或會議使用者向上連結和向下連結媒體的傳輸。 此設定提供您管理組織中頻寬的精細控制。 根據使用者所需的會議案例，我們建議您有足夠的頻寬，以便獲得良好的品質體驗。 最小值為 30 Kbps，最大值取決於會議案例。 若要深入瞭解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱 [頻寬需求](prepare-network.md#bandwidth-requirements)。

如果會議頻寬不足，參與者會看到一則訊息，指出網路品質不佳。

針對需要最高品質的影片體驗的會議，例如 CEO 董事會會議和 Teams 即時活動，建議您將頻寬設定為 10 Mbps。 即使設定了最大體驗，當偵測到特定網路條件時，Teams 媒體堆疊會視情況調整為低頻寬條件。

## <a name="meeting-policy-settings---content-sharing"></a>會議策略設定 - 內容共用

- [螢幕畫面分享模式](#screen-sharing-mode)
- [允許參與者提供或要求控制權](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者提供或要求控制權](#allow-an-external-participant-to-give-or-request-control)
- [允許 PowerPoint 共用](#allow-powerpoint-sharing)
- [允許白板](#allow-whiteboard)
- [允許共用筆記](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>螢幕畫面分享模式

> [!NOTE]
> 這項功能仍在開發中。 螢幕分享是每個參與者的政策，不過，如本節所述，畫面共用會受到召集人的螢幕共用設定影響。

此設定可控制使用者會議是否允許桌面和/或視窗共用。 未指派任何策略的會議 (例如匿名、來賓、B2B 和) 繼承會議召集人的政策。

|設定值 |行為  |
|---------|---------|
|**整個畫面**    | 會議允許完整桌面共用和應用程式共用 |
|**單一應用程式**   | 會議允許應用程式共用        |
|**禁用**     |會議已關閉螢幕畫面共用和應用程式共用。       |

讓我們來看看下列範例。

|使用者 |會議原則 |螢幕畫面分享模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個畫面 |
|艾曼達   | 位置1MeetingPolicy  | 禁用 |

Daniela 主持的會議允許會議參與者共用其整個螢幕或特定應用程式。 如果 Amanda 加入 Daniela 的會議，Amanda 無法共用她的螢幕或特定應用程式，因為她的政策設定已停用。 在由 Amanda 主持的會議中，不允許任何人共用其螢幕或單一應用程式，無論指派給他們的螢幕共用模式政策如何。 這表示 Daniela 無法共用她的螢幕或單一應用程式在 Amanda 的會議中。  

目前，如果使用者使用的是 Google Chrome，他們無法在 Teams 會議中播放影片或共用螢幕畫面。

### <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者提供或要求控制權

這是每個使用者的策略。 此設定可控制使用者是否可以將共用桌面或視窗的控制權授予其他會議參與者。 若要提供控制權，請將游標停留在畫面頂端。

如果使用者已開啟此設定，共用會話中的頂端列會顯示提供控制項選項。

![顯示給予控制權選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

如果使用者的設定已關閉，則無法使用提供 **控制項** 選項。

![顯示沒有提供控制權選項的螢幕擷取畫面](media/meeting-policies-give-control-not-available.png)

讓我們來看看下列範例。

|使用者 |會議原則  |允許參與者提供或要求控制權 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|巴別克    | 位置1MeetingPolicy        | 關閉   |

Daniela 可以將共用桌面或視窗的控制權授予由巴可克組織之會議的其他參與者，而巴可克則無法將控制權授予其他參與者。

若要使用 PowerShell 控制誰可以給予控制權或接受控制權要求，請使用 AllowParticipantGiveRequestControl Cmdlet。

> [!NOTE]
> 若要在共用期間提供並控制共用內容，雙方必須使用 Teams 桌面用戶端。 當任一方執行瀏覽器中的 Teams 時，則不支援控制。 這是我們正計畫修正的技術限制所造成。

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者提供或要求控制權

這是每個使用者的策略。 無論會議召集人已設定什麼專案，組織是否擁有該使用者的此組，都無法控制外部參與者可以執行什麼操作。 此參數可控制外部參與者是否可以根據共用者在其組織會議政策中設定的內容，獲得控制權或要求控制共用者螢幕。 Teams 會議中的外部參與者可以分類為：  

- 匿名使用者
- 來賓使用者  
- B2B 使用者
- 聯合使用者  

聯合使用者是否可以在共用時提供控制權給外部使用者，由允許外部參與者在組織中提供或要求控制權設定所控制。

若要使用 PowerShell 控制外部參與者是否可以提供控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。

### <a name="allow-powerpoint-sharing"></a>允許 PowerPoint 共用

這是每個使用者的策略。 此設定可控制使用者是否可以共用會議中的 PowerPoint 幻燈片組。 外部使用者 ，包括匿名、來賓和聯盟使用者，會繼承會議召集人的政策。

讓我們來看看下列範例。

|使用者 |會議原則  |允許 PowerPoint 共用 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法共用會議中 PowerPoint 的幻燈片組。 即使會議是由 Amanda 組織，Daniela 也可以共用 PowerPoint 幻燈片組。 Amanda 可以查看會議中其他人共用的 PowerPoint 幻燈片組，即使她無法共用 PowerPoint 幻燈片組。

### <a name="allow-whiteboard"></a>允許白板

這是每個使用者的策略。 此設定可控制使用者是否可以在會議共用白板。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。

讓我們來看看下列範例。

|使用者 |會議原則  |允許白板|
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，也無法共用會議中的白板。 即使會議是由 Amanda 組織，Daniela 也可以共用白板。  

### <a name="allow-shared-notes"></a>允許共用筆記

這是每個使用者的策略。 此設定可控制使用者是否可以在會議建立及共用筆記。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。 最多100 位參與者的會議支援會議筆記選項卡。

讓我們來看看下列範例。

|使用者 |會議原則  |允許共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | 已上       |
|艾曼達   | 位置1MeetingPolicy | 關閉 |

Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 無法在任何會議中記錄筆記。

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="bkmeetingparticipants"> </a>
<!-- Do not remove the bookmark link above. -->

## <a name="meeting-policy-settings---participants--guests"></a>會議政策設定 - 參與者&來賓

這些設定會控制哪些會議參與者在大廳等候，才能獲准加入會議，以及允許他們參與會議的水準。

- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [自動允許人員](#automatically-admit-people)
- [允許撥入使用者跳過大廳](#allow-dial-in-users-to-bypass-the-lobby)
- [啟用即時字幕](#enable-live-captions)
- [允許在會議中聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入會議的選項會因每個 Teams 群組的設定和連接方法而異。 如果您的群組有音訊會議，並使用它來連接，請參閱 [音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果您的 Teams 群組沒有音訊會議，請參閱在 Teams [中加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

### <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

這是允許無主席會議之每個召集人的政策。 此設定可控制無註冊使用者是否可以加入會議，而組織沒有經過驗證的使用者出席。 根據預設，此設定會關閉，這表示匿名使用者會等候在大廳中，直到組織經過驗證的使用者加入會議。

> [!NOTE]
> 如果這項設定已關閉，且匿名使用者會先加入會議，且位於大廳，則組織使用者必須使用 Teams 用戶端加入會議，以從大廳准許該使用者。 電話撥入的使用者沒有可用的大廳控制項。

### <a name="automatically-admit-people"></a>自動允許人員

這是每個召集人的政策。 此設定可控制人員是直接加入會議，還是等候在大廳中，直到經過驗證的使用者獲准加入會議。 此設定不適用於撥入使用者。

![顯示與大廳使用者開會的螢幕擷取畫面](media/meeting-policies-lobby.png)

 會議召集人可以在會議 **邀請** 中選取會議選項，以針對他們排程的每一個會議變更此設定。

> [!NOTE]
> 在會議選項中，設定標示為「誰可以跳過大廳」。 如果您變更任何使用者的預設設定，它會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。
  
|設定值  |加入行為 |
|---------|---------|
|**任何人**   |所有會議參與者都直接加入會議，而不需要在大廳等候。 這包括經過驗證的使用者、來自信任組織的外部使用者 (、) 、來賓和匿名使用者。     |
|**貴組織與聯盟組織中的每個人**     |組織中經過驗證的使用者 ，包括來賓使用者和信任組織的使用者，可以直接加入會議，而不需要在大廳等候。  匿名使用者會等候在大廳。   |
|**貴組織中所有人**    |組織內部經過驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。  信任組織的使用者和匿名使用者會等候在大廳。 這是預設設定。           |
|**僅召集人**    |只有會議召集人可以直接加入會議，而不需要在大廳等候。 其他人，包括組織中經過驗證的使用者、來賓使用者、信任組織的使用者和匿名使用者，都必須在大廳等候。           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允許撥入使用者跳過大廳

這是每個召集人的政策。 此設定可控制以電話撥入的人是直接加入會議，還是等候在大廳中，而不考慮 **自動允許人員** 設定。 根據預設，此設定會關閉。 當這項設定關閉時，撥入使用者會等候在大廳，直到組織使用者與 Teams 用戶端加入會議並准許他們加入會議。 開啟此設定後，撥入使用者會在組織使用者加入會議時自動加入會議。

> [!NOTE]
> 如果撥入使用者在組織使用者加入會議之前加入會議，他們將會放在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入會議。 如果您變更任何使用者的預設設定，它會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。

### <a name="enable-live-captions"></a>啟用即時字幕

這是每個使用者原則，適用于會議期間。 此設定可控制使用者是否可以使用開啟即時字幕選項，並關閉使用者出席會議中即時字幕。  

![顯示開啟即時字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**已停用，但使用者可以重寫**     | 在會議期間，使用者不會自動開啟即時字幕。 使用者會看到溢位區域 **中的** (...) **開啟** 即時字幕選項。 這是預設設定。 |
|**禁用**     | 在會議期間，使用者會停用即時字幕。 使用者沒有開啟的選項。          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>允許在會議中聊天

這是每個參與者的設定。 此設定可控制使用者會議是否允許會議聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>會議策略設定 - 指定的簡報者角色模式

這是每個使用者的策略。 此設定可讓您在 Teams 用戶端的會議選項中變更誰可以出席 **？** 設定預設值。 此策略設定會影響所有會議，包括 Now 會議。

" **誰可以出席？」** 設定可讓會議召集人選擇誰可以在會議中做簡報者。 若要深入瞭解，請參閱 [變更 Teams](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 會議的參與者設定和 [Teams 會議中的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議策略，並將其指派給使用者。

若要在 Teams 中指定誰可以展示 **？** 設定預設值，請設定 **SpecifyedPresenterRoleMode** 參數至下列其中一項：

- **EveryoneUserOverride：** 所有會議參與者都可以是簡報者。 此為預設值。 此參數會對應至 Teams **中的** 每個人都設定。
- **EveryoneInCompanyUserOverride：** 組織中經過驗證的使用者 ，包括來賓使用者，可以是簡報者。 此參數會對應到 Teams **中的** 組織人員設定。
- **召集人OnlyUserOverride：** 只有會議召集人可以擔任簡報者，所有會議參與者都指定為出席者。 此參數會對應到 Teams **中的只有** 我設定。

此外，您也可以在 Teams 系統管理中心編輯此政策。

![Teams 系統管理中心的螢幕擷取畫面](media/designated-presenter-role.png)

請記住，在您設定預設值之後，會議召集人仍可在 Teams 中變更此設定，並選擇誰可以在他們排程的會議中進行展示。

## <a name="meeting-policy-settings---meeting-attendance-report"></a>會議政策設定 - 會議出席報告

這是每個使用者的策略。 此設定可控制會議召集人是否可以下載 [會議出席報告](teams-analytics-and-reports/meeting-attendance-report.md)。

目前，您只能使用 PowerShell 來設定此策略設定。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議策略，並將其指派給使用者。

若要讓會議召集人下載會議出席報告，請設定 **AllowEngagementReport 參數** 為 **啟用**。 啟用時，下載報表的選項會顯示在參與者 **窗格中** 。

若要防止會議召集人下載報表，請設定參數為 **已停用**。 根據預設，此設定會停用，而且無法下載報表的選項。

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>會議策略設定 - 群島模式的會議提供者

這是每個使用者的策略。 此設定會控制哪些 Outlook 會議附加元件適用于位於 *群島模式的使用者*。 您可以指定使用者只能使用 [Teams 會議] 增益集，或是可同時使用 [Teams 會議] 和 [商務用 Skype 會議] 增益集在 Outlook 中排程會議。

您只能將此原則套用到處於離島模式的使用者，並在其 Teams 會議原則中將 **AllowOutlookAddIn** 參數設定為 **True**。

目前，您只能使用 PowerShell 來設定此策略。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議策略，並將其指派給使用者。

若要指定您想要讓使用者使用的會議附加元件，請設定 **PreferredMeetingProviderForIslandsMode** 參數，如下所示：

- 將參數設定為 **TeamsAndSfB，** 以在 Outlook 中同時啟用 Teams 會議附加元件和商務用 Skype 附加元件。 此為預設值。
- 將參數設定為 **Teams，** 只在 Outlook 中啟用 Teams 會議附加元件。 此策略設定可確保所有未來的會議都有 Teams 會議加入連結。 它不會將現有的商務用 Skype 會議加入連結遷移到 Teams。 此策略設定不會影響目前狀態、聊天、PSTN 通話，或商務用 Skype 中的其他任何功能，這表示使用者將繼續使用商務用 Skype 來使用這些功能。

  如果您將參數設定為 **Teams**，然後切換回 **TeamsAndSfB，** 兩個會議附加元件都已啟用。 現有的 Teams 會議加入 **連結不會移** 入商務用 Skype。 只有變更之後排定的商務用 Skype 會議會擁有商務用 Skype 會議加入連結。

## <a name="meeting-policy-settings---video-filters-mode"></a>會議策略設定 - 視像篩選模式

這是每個使用者的策略。 此設定可控制使用者是否可以自訂會議中的視音訊背景。

目前，您只能使用 PowerShell 來設定此策略。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議策略，然後將該策略指派給使用者。

若要指定使用者是否可以自訂會議中的視訊背景，請設定 **VideoFiltersMode** 參數，如下所示：

|在 PowerShell 中設定值 |行為  |
|---------|---------|
|**NoFilters**     |使用者無法自訂其視音訊背景。|
|**模糊Only**     |使用者可以模糊其視音訊背景。 |
|**模糊和定義AultBackgrounds**     |使用者可以選擇模糊其視像背景，或選擇使用預設影像組做為背景。 |
|**AllFilters**     |使用者可以選擇模糊其視像背景、選擇預設的影像集，或上傳自訂影像做為背景。 |

> [!IMPORTANT]
> Teams 不會篩選使用者上傳的影像。 當您使用 **AllFilters** 設定時，您應該有內部組織原則，以防止使用者上傳令人反感或不當的影像，或貴組織沒有許可權用於 Teams 會議背景的影像。

> [!NOTE]
> 並非所有 Teams 用戶端都提供這些功能。 詳細資訊，請參閱會議和即時活動中的影片[和背景標題](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e)。

## <a name="meeting-policy-settings---meeting-reactions"></a>會議策略設定 - 會議反應

AllowMeetingReactions 設定只能使用 PowerShell 來使用。 無法從 Teams 系統管理中心開啟或關閉 AllowMeetingReactions。

會議反應預設為關閉。 關閉使用者的反應並不表示使用者在排程的會議中無法使用反應。 無論預設設定如何，會議召集人仍可從會議選項頁面開啟回應。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [將原則指派給 Teams 中的使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議政策](meeting-policies-restricted-anonymous-access.md)
