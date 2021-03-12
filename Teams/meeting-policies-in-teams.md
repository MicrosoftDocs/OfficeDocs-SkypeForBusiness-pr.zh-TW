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
description: 瞭解如何在 Teams 中管理會議政策設定。 使用策略設定來控制使用者排程會議的會議參與者可使用的功能。
ms.openlocfilehash: 77c99516e188ecc0f42fd663a121d439b5470000
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726427"
---
# <a name="manage-meeting-policies-in-teams"></a>管理 Teams 中的會議原則

::: zone target="docs"
使用會議策略來控制組織中使用者排程之會議的會議參與者可使用的功能。 您可以使用全域規則 (自動建立) 自訂策略的全組織預設規則。 您可以在 Microsoft Teams 系統管理中心或 PowerShell 中管理 [會議政策](teams-powershell-overview.md)。

> [!NOTE]
> 有關使用角色管理會議簡報者和出席者許可權的資訊，請參閱 [Teams 會議中的角色](https://support.microsoft.com/office/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019?ui=en-us&rs=en-us&ad=us)。

您可以用下列方式執行策略，這會影響使用者在會議開始、會議期間或會議後的會議體驗。

|執行類型  |說明  |
|---------|---------|
|每個召集人    |當您執行每個召集人策略時，所有會議參與者會繼承該召集人的政策。 例如， **自動准許人員是** 每個召集人的一項政策。 它會控制使用者是否直接加入會議，或是在大廳等候已指派該政策的使用者所排程的會議。          |
|每個使用者    |當您執行每個使用者原則時，只有每個使用者原則會適用于限制召集人和/或會議參與者的某些功能。 例如，在頻道 **中允許現在開會** 是每個使用者的政策。     |
|每一個召集人和每個使用者     |當您執行每個召集人和每個使用者的組合時，根據會議參與者及其政策，某些功能會受限於會議參與者。 例如， **允許雲端錄製** 是每個召集人和每個使用者的政策。 開啟此設定以允許使用者開始和停止錄製。

您可以編輯全域原則中的設定，或建立並指派一或多個自訂策略。 除非您建立並指派自訂策略，否則使用者會取得全域原則。

> [!NOTE]
> 如果使用者已啟用音訊會議授權，或使用者允許進行音訊會議，則會議詳細資料按鈕將可供使用。

## <a name="create-a-custom-meeting-policy"></a>建立自訂會議政策

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
2. 按一下該政策名稱的左側以選取該政策， **然後選取編輯**。
3. 從此處，進行您需要的變更。
4. 選取 **儲存**。

> [!NOTE]
> 一次只能指派一個會議政策給使用者。

## <a name="assign-a-meeting-policy-to-users"></a>將會議原則指派給使用者

[!INCLUDE [assign-policy](includes/assign-policy.md)]

> [!NOTE]
> 如果已指派使用者，您即無法刪除該政策。 您必須先將不同的策略指派給所有受影響的使用者，然後您可以刪除原始策略。

## <a name="meeting-policy-settings"></a>會議政策設定

在會議政策頁面上選取現有 **政策，****或選取新增** 以新增新政策。 設定下列設定。

- [一般](#meeting-policy-settings---general)
- [音訊&影片](#meeting-policy-settings---audio--video)
- [內容共用](#meeting-policy-settings---content-sharing)
- [參與者&來賓](#meeting-policy-settings---participants--guests)

::: zone-end

<a name="bkgeneral"> </a>

## <a name="meeting-policy-settings---general"></a>會議政策設定 - 一般

- [在頻道中允許現在開會](#allow-meet-now-in-channels)
- [允許 Outlook 附加元件](#allow-the-outlook-add-in)
- [允許頻道會議排程](#allow-channel-meeting-scheduling)
- [允許排程私人會議](#allow-scheduling-private-meetings)
- [在私人會議中允許現在開會](#allow-meet-now-in-private-meetings)

### <a name="allow-meet-now-in-channels"></a>在頻道中允許現在開會

允許 **開會** 是一項每個使用者原則，在會議開始之前即適用。 此設定可控制使用者是否可以在 Teams 頻道中啟動非計畫的會議。 如果您開啟此設定，使用者可以選取會議按鈕，在頻道中開始非計畫的會議或排程會議。 預設值為 True。

![顯示訊息下方的目前開會圖示的螢幕擷取畫面](media/meeting-policies-meet-now.png)

### <a name="allow-the-outlook-add-in"></a>允許 Outlook 附加元件

允許 Outlook 附加元件是一項每個使用者原則，在會議開始之前即適用。 此設定可控制 Teams 會議是否可以從 Outlook (Windows、Mac、Web 及行動) 。

![螢幕擷取畫面顯示排程新會議的能力](media/meeting-policies-outlook-add-in.png)

如果您關閉此功能，使用者就無法排程。 Teams 會議在 Outlook 中建立新會議時。 例如，在 Windows 上的 Outlook 中，功能區中不會顯示新 **Teams** 會議選項。

### <a name="allow-channel-meeting-scheduling"></a>允許頻道會議排程

使用現有的 AllowChannelMeeting 排程策略來控制可以在小組頻道日曆上建立的事件種類。 這是每個使用者原則，在會議開始之前即適用。 此設定會控制使用者是否可以在 Teams 頻道中排程會議。 此設定預設為開啟。

如果關閉此策略，使用者無法建立新頻道會議。 不過，活動召集人可以編輯現有的頻道會議。

排程會議將會停用。

 ![Teams 中的排程會議選項](media/schedule-meeting-option.png)

頻道選取已停用。

![選取要排程會議之頻道的月曆選項。](media/meeting-policies-select-a-channel-to-meet-in.png)

在頻道文章頁面中，下列功能將會停用：

- **頻道回復撰寫** 方塊上的排程會議按鈕。
  ![排程會議按鈕回復撰寫方塊](media/schedule-meeting-disabled-in-chat2.png)
  
- **頻道標題上的** 排程會議按鈕。
  ![頻道標題中的排程會議按鈕](media/schedule-now-in-header.png)

在頻道日曆中：

- **頻道月曆標題** 上的新增活動按鈕將會停用。
  ![已停用頻道月曆標題上的按鈕](media/add-new-event-disabled.png)

- 使用者無法拖曳並選取頻道日曆上的時間區塊，以建立頻道會議。

- 使用者無法使用鍵盤快速鍵在頻道日曆上建立會議。

在系統管理中心：

頻道日曆應用程式會顯示在應用程式許可權政策頁面上 **的 Microsoft 應用程式** 區段。

 ![Teams 系統管理中心中的應用程式許可權政策](media/manage-microsoft-apps-policy.png)

### <a name="allow-scheduling-private-meetings"></a>允許排程私人會議

排程私人會議是一項每個使用者原則，在會議開始之前即適用。 此設定會控制使用者是否可以在 Teams 中排程私人會議。 當會議未發佈到團隊中的頻道時，會議是私人的。

如果您關閉允許排 **程** 私人會議和允許頻道會議 **排** 程，Teams 中的使用者會停用新增必要的出席者及新增頻道選項。 此設定預設為開啟。

### <a name="allow-meet-now-in-private-meetings"></a>在私人會議中允許現在開會

這是每個使用者原則，在會議開始之前即適用。 此設定可控制使用者是否可以啟動非計畫的私人會議。 此設定預設為開啟。

<a name="bkaudioandvideo"> </a>

## <a name="meeting-policy-settings---audio--video"></a>會議政策設定 - 音訊&影片

- [允許抄寫](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [IP 音訊模式](#mode-for-ip-audio)
- [IP 影片模式](#mode-for-ip-video)
- [允許 IP 視訊](#allow-ip-video)
- [媒體位元速率 (Kb) ](#media-bit-rate-kbs)

### <a name="allow-transcription"></a>允許抄寫

此政策會開啟即時抄寫。 允許抄寫是每個使用者的一項政策。 此設定會控制是否可以轉譯此特定團隊的會議。

![會議政策中的文字記錄選項](media/live-transcription.png)

即時抄寫功能幾乎即時顯示 Teams 會議期間的語音對語音內容文字。 文字會顯示在會議影片旁邊，包括演講者的姓名和時間戳記。 若要深入瞭解，請參閱在 Teams 會議 [中查看即時抄寫](https://support.microsoft.com/office/view-live-transcription-in-a-teams-meeting-7a1401ec-73b4-431d-875a-8b6af82b3e15)。

目前，Teams 桌面用戶端支援即時抄寫功能。 美國英文口語支援文字抄寫功能。 文字記錄可在 Teams 電腦版或 Web 版會議後使用。

以下說明允許抄寫 **和****允許雲端錄製** 策略設定如何共同作業。 下表說明這些設定的值以及會議行為。

|允許抄寫|允許雲端錄製|行為|
|---------|---------|---------|
|**On**|**On**|Teams **會議提供** 開始文字記錄選項。 會議召集人或會議參與者可以開始和停止抄寫。 Teams **會議提供** 開始錄製選項。 會議召集人或會議參與者可以開始和停止錄製。 |
|**On**|**關閉**|Teams **會議提供** 開始文字記錄選項。 Teams **會議** 沒有提供開始錄製選項。 |
|**關閉**|**On**|Teams **會議提供** 開始錄製選項。 Teams **會議未** 提供開始抄寫選項。|
|**關閉**|**關閉**|Teams 會議無法錄製和抄寫。  |

### <a name="allow-cloud-recording"></a>允許雲端錄製

允許雲端錄製會以每個使用者策略控制。 此設定會控制使用者是否可以錄製。 如果會議召集人或另一個會議參與者的特定策略設定已開啟，而且如果他們是來自與會議召集人同一個組織的已驗證使用者，就可以開始錄製。

組織外部人員 ，例如聯盟和匿名使用者，無法開始錄製。 來賓使用者無法啟動或停止錄製。

![錄製選項](media/meeting-policies-recording.png)

讓我們看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 關閉 |
|艾曼達 | Location1MeetingPolicy | On|
|John (外部使用者)  | 不適用 | 不適用|

她即使是召集人，也無法錄製，因為她的政策已設定為關閉。 已啟用該策略設定的安百達可以錄製會議，包括由方安達組織的會議。 如果 Amanda 要組織會議，她將能夠錄製會議。 不過，已停用該政策設定且 John 是外部使用者，因此無法錄製該會議。

若要深入瞭解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

### <a name="mode-for-ip-audio"></a>IP 音訊模式

IP 音訊模式是每個使用者的政策。 此設定可控制是否可以在會議和群組通話中開啟音訊。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外向和傳入音訊**    |會議允許外發和傳入音訊。 這是預設設定。 |
|**禁用**     |傳出和傳入音訊在會議中會關閉。     |

如果使用者設為停用，該使用者仍然可以排程和組織會議，但無法使用音訊。 若要加入會議，使用者必須透過公用交換電話網路 (PSTN) 或讓會議通話以透過電話加入使用者。 未指派任何規則的會議參與者 (例如，匿名參與者) 預設會啟用撥出和傳入音訊。  在 Teams 行動用戶端上，如果這項設定已停用，使用者必須透過 PSTN 撥入會議。

此設定不適用於 1 對 1 通話。 若要限制 1 對 1 通話，請設定 Teams [通話政策](teams-calling-policy.md) ，並關閉撥打 **私人通話** 設定。 這項設定也不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD 環境) 這項設定。

若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="mode-for-ip-video"></a>IP 影片模式

IP 影片模式是每個使用者的一項政策。 此設定可控制是否可以在會議和群組通話中開啟視音訊。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外向和傳入視**    | 會議預設會允許外發和傳入視音訊。 |
|**禁用**     | 傳出和傳入的視音訊在會議中會關閉。 在 Teams 行動用戶端上，使用者無法共用會議中的影片或相片。 <br><br>請注意，如果 **IP 音訊模式** 已停用， **則 IP** 視障模式也會維持停用狀態。  |

如果使用者設為停用，該使用者無法開啟視障或觀看其他會議參與者共用的影片。 未指派任何規則的會議參與者 (例如，匿名參與者) 預設會啟用此設定為外) 和傳入影片。 

這項設定不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD 環境) 這項設定。

> [!NOTE]
> 請記住，此設定會控制外發和傳入視事，而 **允許 IP 視** 區設定則控制外接視。 若要深入瞭解，請參閱 [哪個 IP 視視策略設定為優先？](#which-ip-video-policy-setting-takes-precedence) 以及管理 [會議參與者的音訊/視音訊](#manage-audiovideo-for-meeting-participants)。

若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="allow-ip-video"></a>允許 IP 視訊

允許 IP 影片是每個召集人和每個使用者政策的組合。 影片是會議的重要元件。 在某些組織中，系統管理員可能會想要進一控制哪些使用者的會議有視音訊。 此設定可控制是否可以在使用者主持的會議，以及由使用者啟動的 1：1 和群組通話中開啟視訊。 在 Teams 行動用戶端上，此設定可控制使用者是否可以在會議中共用相片和影片。

由已啟用此策略設定的使用者所組織的會議，允許會議參與者在會議中共用視像，如果參與者也已啟用該策略設定。 未指派任何策略的會議參與者 (例如匿名和) 繼承會議召集人的策略。

> [!NOTE]
> 請記住，此設定會控制外接視視， **而 IP 視** 區模式則同時控制外接和傳入視事。 若要深入瞭解，請參閱 [哪個 IP 視視策略設定為優先？](#which-ip-video-policy-setting-takes-precedence) 以及管理 [會議參與者的音訊/視音訊](#manage-audiovideo-for-meeting-participants)。

| Teams 桌面與 Web 用戶端 |Teams 行動用戶端  |
|:-------:|:-------:|
|![螢幕擷取畫面顯示桌上型電腦音訊/視音訊設定的會議加入](media/meeting-policies-audio-video-settings.png)    |![螢幕擷取畫面顯示使用行動版音訊/視音訊設定加入會議](media/meeting-policies-mobile-join.png)          |

讓我們看看下列範例。

|使用者 |會議原則  |允許 IP 視訊 |
|---------|---------|---------|
|Daniela   | 全域   | On       |
|艾曼達    | Location1MeetingPolicy        | 關閉      |

由 Daniela 主持的會議允許開啟視音訊。 Daniela 可以加入會議並開啟影片。 Amanda 無法開啟在立達的會議視區，因為安百達的這個政策設定為不允許視視。 Amanda 可以在會議中查看其他參與者共用的影片。

在由 Amanda 主持的會議中，無論指派的視音訊策略如何，沒有人可以開啟視音訊。 這表示在安甘達的會議中，有一段影片無法開啟。  

如果 Daniela 撥打 Amanda 視音訊，Amanda 只能以音訊接聽通話。 當通話接通時，艾安達可以看到張雅華的視視，但無法開啟視音訊。 如果 Amanda 打電話給立達，立達可以使用視音訊和視音訊接聽通話。 當通話接通時，Daniela 可以視需要開啟或關閉視音訊。

若要深入瞭解，請參閱管理 [會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪個 IP 視區策略設定為優先

對於使用者，影片的最嚴格政策設定會優先。 以下是一些範例。

|允許 IP 視訊|IP 影片模式|會議體驗|
|---------|---------|---------|
|召集人： **在**<br><br>參與者： **已** |參與者： **已停用**        |IP **視區模式設定** 會優先。 指派此政策的參與者無法開啟或觀看其他人共用的影片。|
|召集人： **在**<br><br>參與者： **已** |參與者： **已啟用外向和傳入視訊**          |指派此政策的參與者可以開啟或觀看其他人共用的影片。         |
|召集人： **在**<br><br>參與者： **關閉** |參與者： **已啟用外向和傳入視訊**         |允許 **IP 視區** 設定會優先。 參與者只能看到傳入的影片，而且無法傳送外寄影片。         |
|召集人： **在**<br><br>參與者： **關閉** |參與者： **已停用**         |IP **視區模式設定** 會優先。 參與者無法看到傳入或傳出的影片。|
|召集人： **關閉**    |       |允許 **IP 視區** 設定會優先，因為會議召集人已關閉此設定。 在指派此政策的使用者所組織的會議中，沒有人可以開啟視音訊。         |

### <a name="manage-audiovideo-for-meeting-participants"></a>管理會議參與者的音訊/視音訊

|如果您想要...  |設定下列政策設定  |
|---------|---------|
|停用會議參與者的音訊和視音訊  |IP 音訊模式： **已停用**<br> IP 視訊模式： **已停用**<br>允許 IP 影片：N/A       |
|僅為會議參與者啟用傳入視像和音訊  |IP 音訊模式：已啟用外 **接和傳入音訊**<br> IP 視訊模式： **已啟用外接和傳入視訊**<br>允許 IP 影片： **關閉**       |
|停用會議參與者的視 (參與者只有音訊) |  IP 音訊模式： **啟用外接和傳入音訊**<br> IP 視訊模式： **已停用**<br>允許 IP 影片：N/A
|為會議參與者啟用音訊和視音訊    |IP 音訊模式：預設會 **啟用** 外 (傳入) <br> IP 視訊模式 **：啟用** 外 (視訊) <br>允許 IP 視訊 **： (** 預設)     |

會採用會議召集人原則與使用者原則之間限制最嚴格的原則。 例如，如果會議召集人有限制視音訊的政策，而使用者的政策沒有限制視視，則會議參與者會繼承會議召集人的政策，而且無法存取會議中的視音訊。 這表示他們只能使用音訊加入會議。

> [!NOTE]
> 當使用者啟動群組通話以使用電話加入時，音訊 **畫面** 中不會顯示使用電話。 這是我們正在努力解決的已知問題。 若要解決此問題，請在其他連接選項 **下** 選取 **電話音訊**。  

#### <a name="teams-mobile-clients"></a>Teams 行動用戶端

對於 Teams 行動用戶端上的使用者，在會議期間共用相片和影片的能力取決於允許 IP **視片** 或 **IP 視區模式** 設定。 根據優先處理哪些政策設定，無法共用影片和相片。 這不會影響螢幕畫面分享，因為螢幕畫面分享是使用個別的螢幕 [畫面分享模式](#screen-sharing-mode) 設定所設定。 此外，您可以設定 [Teams 行動](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 性政策，防止行動使用者以行動資料連線使用 IP 影片，這表示他們必須使用 WiFi 連接。

### <a name="media-bit-rate-kbs"></a>媒體位元速率 (Kb) 

這是每個使用者的策略。 此設定會決定使用者在通話和會議中進行音訊、視視及視視應用程式共用傳輸的總媒體位元速率。 它會同時適用于通話或會議使用者上下移動的上行和下行媒體。 此設定讓您精細地控制管理貴組織的頻寬。 根據使用者所需的會議案例，我們建議有足夠的頻寬，提供良好的品質體驗。 最小值為 30 Kbps，最大值取決於會議案例。 若要深入瞭解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱 [頻寬需求](prepare-network.md#bandwidth-requirements)。

如果會議沒有足夠的頻寬，參與者會看到一則訊息，指出網路品質不佳。

針對需要最高品質影片體驗的會議，例如 CEO 會議及 Teams 即時活動，建議您將頻寬設定為 10 Mbps。 即使已設定最大使用體驗，當偵測到特定網路條件時，Teams 媒體堆疊會視情況調整為低頻寬條件。

## <a name="meeting-policy-settings---content-sharing"></a>會議政策設定 - 內容共用

- [螢幕畫面分享模式](#screen-sharing-mode)
- [允許參與者提供或要求控制權](#allow-a-participant-to-give-or-request-control)
- [允許外部參與者提供或要求控制權](#allow-an-external-participant-to-give-or-request-control)
- [允許 PowerPoint 共用](#allow-powerpoint-sharing)
- [允許白板](#allow-whiteboard)
- [允許共用筆記](#allow-shared-notes)

### <a name="screen-sharing-mode"></a>螢幕畫面分享模式

> [!NOTE]
> 這項功能仍在開發中。 螢幕畫面分享是每個參與者的一項政策，但如本節所述，可能會受召集人的螢幕畫面分享設定影響。

此設定會控制使用者會議是否允許桌面和/或視窗共用。 未指派任何策略的會議參與者 (例如匿名、來賓、B2B 和) 繼承會議召集人的策略。

|設定值 |行為  |
|---------|---------|
|**整個螢幕**    | 會議允許完整桌面共用和應用程式共用 |
|**單一應用程式**   | 會議允許應用程式共用        |
|**禁用**     |會議已關閉螢幕畫面分享和應用程式共用。       |

讓我們看看下列範例。

|使用者 |會議原則 |螢幕畫面分享模式 |
|---------|---------|---------|
|Daniela  | 全域   | 整個螢幕 |
|艾曼達   | Location1MeetingPolicy  | 禁用 |

Daniela 主持的會議允許會議參與者共用其整個螢幕或特定應用程式。 如果 Amanda 加入立安達的會議，由於她的政策設定已停用，因此她無法共用螢幕或特定應用程式。 在由 Amanda 主持的會議中，無論指派的螢幕共用模式策略如何，都不允許任何人共用螢幕或單一應用程式。 這表示雅心無法共用螢幕畫面或 Amanda 會議中的單一應用程式。  

目前，如果使用者使用的是 Google Chrome，他們無法播放影片或在 Teams 會議分享螢幕畫面。

### <a name="allow-a-participant-to-give-or-request-control"></a>允許參與者提供或要求控制權

這是每個使用者的策略。 此設定會控制使用者是否可以將共用桌面或視窗的控制權授予其他會議參與者。 若要提供控制權，請將游標停留在畫面頂端。

如果使用者已開啟此設定，共用會話的頂端列會顯示提供控制選項。

![顯示提供控制項選項的螢幕擷取畫面](media/meeting-policies-give-control.png)

如果使用者的設定已關閉， **則沒有提供** 控制項選項。

![螢幕擷取畫面顯示沒有提供控制項選項](media/meeting-policies-give-control-not-available.png)

讓我們看看下列範例。

|使用者 |會議原則  |允許參與者提供或要求控制權 |
|---------|---------|---------|
|Daniela   | 全域   | On       |
|納克克    | Location1MeetingPolicy        | 關閉   |

在由他克組織的會議中，有方能將共用桌面或視窗的控制權授予其他參與者，而立克則無法將控制權授予其他參與者。

若要使用 PowerShell 來控制誰可以給予控制權或接受控制權要求，請使用 AllowParticipantGiveRequestControl Cmdlet。

> [!NOTE]
> 若要在共用期間提供並控制共用內容，雙方必須使用 Teams 桌面用戶端。 當任一方執行瀏覽器中的 Teams 時，則不支援控制。 這是我們正計畫修正的技術限制所造成。

### <a name="allow-an-external-participant-to-give-or-request-control"></a>允許外部參與者提供或要求控制權

這是每個使用者的策略。 無論會議召集人已設定什麼，組織是否為使用者設定此設定，都無法控制外部參與者可以執行哪些操作。 此參數根據共用者在其組織的會議政策中設定的內容，控制外部參與者是否可以獲得控制權或要求控制共用者螢幕。 Teams 會議的外部參與者可以分類如下：  

- 匿名使用者
- 來賓使用者  
- B2B 使用者
- 聯盟使用者  

在共用時，聯合使用者是否可以將控制權授予外部使用者，而共用是由允許外部參與者提供或要求其組織中控制權設定所控制。

若要使用 PowerShell 來控制外部參與者是否可以提供控制權或接受控制權要求，請使用 AllowExternalParticipantGiveRequestControl Cmdlet。

### <a name="allow-powerpoint-sharing"></a>允許 PowerPoint 共用

這是每個使用者的策略。 此設定會控制使用者是否可以在會議共用 PowerPoint 幻燈片組。 外部使用者 ，包括匿名、來賓和聯盟使用者，會繼承會議召集人的政策。

讓我們看看下列範例。

|使用者 |會議原則  |允許 PowerPoint 共用 |
|---------|---------|---------|
|Daniela   | 全域   | On       |
|艾曼達   | Location1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，她也無法共用會議中的 PowerPoint 幻燈片組。 即使會議是由安安達組織，但方安達也可以共用 PowerPoint 幻燈片組。 雖然她無法共用 PowerPoint 幻燈片組，她還是可以查看會議中其他人共用的 PowerPoint 幻燈片組。

### <a name="allow-whiteboard"></a>允許白板

這是每個使用者的策略。 此設定會控制使用者是否可以在會議共用白板。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。

讓我們看看下列範例。

|使用者 |會議原則  |允許白板|
|---------|---------|---------|
|Daniela   | 全域   | On       |
|艾曼達   | Location1MeetingPolicy        | 關閉   |

即使 Amanda 是會議召集人，她也無法共用會議中的白板。 即使會議是由張安達組織，但方安達也可以共用白板。  

### <a name="allow-shared-notes"></a>允許共用筆記

這是每個使用者的策略。 此設定會控制使用者是否可以在會議建立和共用筆記。 外部使用者 ，包括匿名、B2B 和聯盟使用者，會繼承會議召集人的政策。 會議 **最多支援** 100 位參與者的會議記錄。

讓我們看看下列範例。

|使用者 |會議原則  |允許共用筆記 |
|---------|---------|---------|
|Daniela   | 全域   | On       |
|艾曼達   | Location1MeetingPolicy | 關閉 |

Daniela 可以在 Amanda 的會議中記錄筆記，而 Amanda 不能在任何會議中記錄筆記。

<!-- Bookmark used by Context Sensitive Help (CSH). Do not delete. -->
<a name="bkmeetingparticipants"> </a>
<!-- Do not remove the bookmark link above. -->

## <a name="meeting-policy-settings---participants--guests"></a>會議政策設定 - 參與者&來賓

這些設定會控制哪些會議參與者在獲准進入會議前在大廳等候，以及允許他們參與會議。

- [讓匿名人員開始會議](#let-anonymous-people-start-a-meeting)
- [自動准許人員進入](#automatically-admit-people)
- [允許撥入使用者旁路大廳](#allow-dial-in-users-to-bypass-the-lobby)
- [啟用即時字幕](#enable-live-captions)
- [在會議中允許聊天](#allow-chat-in-meetings)

> [!NOTE]
>加入會議的選項會因每個 Teams 群組的設定和連接方法而異。 如果您的群組有音訊會議，並使用音訊會議來連接，請參閱 [音訊會議](https://docs.microsoft.com/microsoftteams/audio-conferencing-in-office-365)。 如果您的 Teams 群組沒有音訊會議，請參閱在 Teams 中 [加入會議](https://support.office.com/article/join-a-meeting-in-teams-1613bb53-f3fa-431e-85a9-d6a91e3468c9)。

### <a name="let-anonymous-people-start-a-meeting"></a>讓匿名人員開始會議

這是允許無主席電話撥入式會議之每個召集人的政策。 此設定會控制撥入使用者是否可以在未經過驗證的組織使用者出席的情況下加入會議。 根據預設，此設定為關閉，這表示撥入式使用者將等候在大廳，直到組織已驗證的使用者加入會議。

> [!NOTE]
> 如果此設定已關閉，且電話撥入使用者會先加入會議，且位於大廳，則組織使用者必須與 Teams 用戶端加入會議，以從大廳准許使用者進入。 沒有大廳控制項可供撥入的使用者使用。

### <a name="automatically-admit-people"></a>自動准許人員進入

這是每個召集人的政策。 此設定會控制人員是否直接加入會議，或等候在大廳等候，直到通過驗證的使用者獲准參加。 此設定不適用於撥入使用者。

![顯示與使用者在大廳開會的螢幕擷取畫面](media/meeting-policies-lobby.png)

 會議召集人可以在會議 **邀請** 中選取會議選項，以針對他們排程的每一個會議變更此設定。

> [!NOTE]
> 在會議選項中，設定會標示為「誰可以避開大廳」。 如果您變更任何使用者的預設設定，該設定會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。
  
|設定值  |加入行為 |
|---------|---------|
|**任何人**   |所有會議參與者直接加入會議，而不需要在大廳等候。 這包括已驗證的使用者、來自信任組織的外部 (、) 、來賓和匿名使用者。     |
|**貴組織及聯盟組織的每個人**     |組織中已驗證的使用者 ，包括來賓使用者和信任的組織使用者，可以直接加入會議，而不需要在大廳等候。  匿名使用者在大廳等候。   |
|**貴組織所有人**    |組織內部已驗證的使用者 ，包括來賓使用者，可以直接加入會議，而不需要在大廳等候。  來自信任組織和匿名使用者的使用者在大廳等候。 這是預設設定。           |
|**僅召集人**    |只有會議召集人可以直接加入會議，而不必在大廳等候。 其他所有人 ，包括組織中已驗證的使用者、來賓使用者、信任組織的使用者和匿名使用者，都必須在大廳等候。           |

### <a name="allow-dial-in-users-to-bypass-the-lobby"></a>允許撥入使用者旁路大廳

這是每個召集人的政策。 此設定會控制以電話撥入的人是否直接加入會議，或在大廳等候，而不管自動 **准許人員設定** 。 此設定預設為關閉。 關閉此設定時，撥入使用者會等候在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入。 開啟此設定時，撥入使用者會在組織使用者加入會議時自動加入會議。

> [!NOTE]
> 如果撥入式使用者在組織使用者加入會議之前加入會議，他們會被放置在大廳，直到組織使用者使用 Teams 用戶端加入會議並准許他們加入。 如果您變更任何使用者的預設設定，該設定會適用于該使用者組織的所有新會議，以及使用者未修改會議選項的任何先前會議。

### <a name="enable-live-captions"></a>啟用即時字幕

這是每個使用者原則，在會議期間適用。 此設定會控制使用者是否可以使用開啟即時字幕選項，以在使用者出席的會議中開啟和關閉即時字幕。  

![顯示開啟即時字幕選項的螢幕擷取畫面](media/meeting-policies-live-captions.png)

|設定值 |行為  |
|---------|---------|
|**已停用，但使用者可以覆蓋**     | 在會議期間，使用者不會自動開啟即時字幕。 使用者在溢點陣圖上看到開啟即時字幕選項 **(...)** 功能表來開啟它們。 這是預設設定。 |
|**禁用**     | 在會議期間，使用者會停用即時字幕。 使用者沒有開啟的選項。          |

<a name="bkcontentsharing"> </a>

### <a name="allow-chat-in-meetings"></a>在會議中允許聊天

這是每個參與者的設定。 此設定會控制使用者會議是否允許會議聊天。

<a name="bkparticipantsandguests"> </a>

## <a name="meeting-policy-settings---designated-presenter-role-mode"></a>會議政策設定 - 指定的簡報者角色模式

這是每個使用者的策略。 此設定可讓您變更 Teams 用戶端中會議選項中之 Who  **can present？** 設定的預設值。 此策略設定會影響所有會議，包括 Now Meetings 會議。

誰 **可以出席？** 設定可讓會議召集人選擇會議簡報者。 若要深入瞭解，請參閱變更 Teams 會議的參與者 [設定](https://support.microsoft.com/article/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e) 和 [Teams 會議的角色](https://support.microsoft.com/article/roles-in-a-teams-meeting-c16fa7d0-1666-4dde-8686-0a0bfe16e019)。

您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。

若要在 Teams 中指定 Who **can present？** 設定預設值，請設定 **DesignatedPresenterRoleMode** 參數至下列其中一項：

- **EveryoneUserOverride：** 所有會議參與者都可以是簡報者。 此為預設值。 此參數會對應到 Teams **中的所有人** 設定。
- **EveryoneInCompanyUserOverride：** 組織中已驗證的使用者 ，包括來賓使用者，可以是簡報者。 此參數會對應到 Teams **中的組織** 人員設定。
- **OrganizerOnlyUserOverride：** 只有會議召集人可以擔任簡報者，而所有會議參與者都指定為出席者。 此參數會對應到 Teams **中的僅自己** 設定。

此外，您也可以在 Teams 系統管理中心編輯此政策。

![Teams 系統管理中心的螢幕擷取畫面](media/designated-presenter-role.png)

請記住，設定預設值之後，會議召集人仍然可以在 Teams 中變更此設定，並選擇誰可以在他們排程的會議中展示。

## <a name="meeting-policy-settings---meeting-attendance-report"></a>會議政策設定 - 會議出席報告

這是每個使用者的策略。 此設定會控制會議召集人是否可以下載 [會議出席報告](teams-analytics-and-reports/meeting-attendance-report.md)。

目前，您僅能使用 PowerShell 來設定此策略設定。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。

若要讓會議召集人下載會議出席報告，請設定 **AllowEngagementReport 參數** 為 **Enabled。** 啟用時，下載報表的選項會顯示在參與者 **窗格中** 。

若要防止會議召集人下載報表，請設定參數為 **停用**。 根據預設，此設定會停用，而且無法下載報表。

## <a name="meeting-policy-settings---meeting-provider-for-islands-mode"></a>會議政策設定 - 群島模式的會議提供者

這是每個使用者的策略。 此設定會控制哪些 Outlook 會議附加元件適用于 *位於群島模式的使用者*。 您可以指定使用者只能使用 [Teams 會議] 增益集，或是可同時使用 [Teams 會議] 和 [商務用 Skype 會議] 增益集在 Outlook 中排程會議。

您只能將此原則套用到處於離島模式的使用者，並在其 Teams 會議原則中將 **AllowOutlookAddIn** 參數設定為 **True**。

目前，您僅能使用 PowerShell 設定此策略。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議政策，並將它指派給使用者。

若要指定您想要提供給使用者使用的會議附加元件，請設定 **PreferredMeetingProviderForislandsMode** 參數，如下所示：

- 將參數設定為 **TeamsAndSfB，** 以在 Outlook 中同時啟用 Teams 會議附加元件和商務用 Skype 附加元件。 此為預設值。
- 將參數設定為 **Teams，** 以在 Outlook 中僅啟用 Teams 會議外掛程式。 此策略設定可確保所有未來的會議都有 Teams 會議加入連結。 它不會將現有的商務用 Skype 會議加入連結遷移到 Teams。 此策略設定不會影響目前狀態、聊天、PSTN 通話，或商務用 Skype 中的其他任何功能，這表示使用者將繼續使用商務用 Skype 來使用這些功能。

  如果您將參數設定為 **Teams，** 然後切換回 **TeamsAndSfB，** 兩個會議附加元件都已啟用。 現有的 Teams 會議加入 **連結不會** 移入商務用 Skype。 只有變更之後排程的商務用 Skype 會議會擁有商務用 Skype 會議加入連結。

## <a name="meeting-policy-settings---video-filters-mode"></a>會議政策設定 - 視視篩選模式

這是每個使用者的策略。 此設定會控制使用者是否可以在會議中自訂其視視背景。

目前，您僅能使用 PowerShell 來設定此策略。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議政策，然後將該策略指派給使用者。

若要指定使用者是否可以在會議中自訂視訊背景，請設定 **VideoFiltersMode** 參數，如下所示：

|在 PowerShell 中設定值 |行為  |
|---------|---------|
|**NoFilters**     |使用者無法自訂其視視背景。|
|**BlurOnly**     |使用者可以模糊其視視背景。 |
|**BlurandDefaultBackgrounds**     |使用者可以選擇模糊其視視背景，或選擇使用預設影像組作為背景。 |
|**所有篩選**     |使用者可以選擇模糊其視視背景、選擇預設的影像集，或上傳自訂影像以做為背景使用。 |

> [!IMPORTANT]
> Teams 不會篩選使用者上傳的影像。 當您使用 **AllFilters** 設定時，您應有內部組織原則來防止使用者上傳令人反感或不適當的影像，或是貴組織沒有許可權用於 Teams 會議背景的影像。

> [!NOTE]
> 並非所有 Teams 用戶端都提供這些功能。 詳細資訊請參閱會議和即時活動中 _的_ 影片 [和背景標題](https://support.microsoft.com/office/meetings-and-live-events-5c3e0646-dc37-45ad-84a4-1666fac62d4e)。

## <a name="meeting-policy-settings---meeting-reactions"></a>會議政策設定 - 會議反應

AllowMeetingReactions 設定只能使用 PowerShell 來使用。 Teams 系統管理中心無法開啟或關閉 AllowMeetingReactions。

會議反應預設為關閉。 為使用者關閉反應並不表示使用者在排程的會議中無法使用反應。 無論預設設定如何，會議召集人仍然可以從會議選項頁面開啟回應。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](assign-policies.md)
- [從使用者移除 RestrictedAnonymousAccess Teams 會議政策](meeting-policies-restricted-anonymous-access.md)
