---
title: 管理音訊和視音訊的會議政策
author: CarolynRowe
ms.author: crowe
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
- ms.teamsadmincenter.meetingpolicies.audioandvideo
- seo-marvel-apr2020
description: 瞭解如何在 Teams 中管理音訊和視音訊的會議策略設定。
ms.openlocfilehash: 3f7a557555d6846c4ada792ceb05da43ce91ed0f
ms.sourcegitcommit: 2d725b9925696e61e3e7338f890f086e009c28f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/06/2021
ms.locfileid: "51598714"
---
# <a name="meeting-policy-settings-for-audio--video"></a>音訊和視&設定

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

本文將說明音訊和視音訊特有的會議策略設定。 這些包括下列專案：

- [允許文字翻譯](#allow-transcription)
- [允許雲端錄製](#allow-cloud-recording)
- [IP 音訊模式](#mode-for-ip-audio) 
- [IP 影片模式](#mode-for-ip-video) 
- [允許 IP 視訊](#allow-ip-video)
- [媒體位元速率 (Kbs) ](#media-bit-rate-kbs)
- [視區模式](#video-filters-mode)

### <a name="allow-transcription"></a>允許文字翻譯

這是每個召集人和每個使用者策略的組合。 此設定可控制在播放會議錄製期間是否提供字幕和文字翻譯功能。 如果您關閉此功能，在播放會議錄製期間，將無法使用搜尋和 **CC** 選項。 開始錄製的人需要開啟此設定，這樣錄製也會包含轉錄。

請注意，錄製的會議目前僅支援在 Teams 中將語言設定為英文，以及會議中會使用英文時的使用者。

### <a name="allow-cloud-recording"></a>允許雲端錄製

這是每個召集人和每個使用者策略的組合。 此設定可控制是否可以錄製此使用者的會議。 如果參與者已開啟策略設定，且他們是來自同一個組織的已驗證使用者，會議召集人或其他會議參與者可以開始錄製。

組織外部人員 ，例如聯盟和匿名使用者，無法開始錄製。 來賓使用者無法開始或停止錄製。

![顯示錄製選項的螢幕擷取畫面](media/meeting-policies-recording.png)

讓我們來看看下列範例。

|使用者 |會議原則  |允許雲端錄製 |
|---------|---------|---------|
|Daniela | 全域   | 關閉 |
|艾曼達 | 位置1MeetingPolicy | 已上|
|John (外部使用者)  | 不適用 | 不適用|

無法錄製由 Daniela 組織的會議，且已啟用策略設定的 Amanda 無法錄製由 Daniela 組織的會議。 不過，您可以錄製由 Amanda 組織的會議，但已停用策略設定且 John 是外部使用者的 Daniela 無法錄製由 Amanda 組織的會議。

若要深入瞭解雲端會議錄製，請參閱 [Teams 雲端會議錄製](cloud-recording.md)。

### <a name="mode-for-ip-audio"></a>IP 音訊模式

這是每個使用者的策略。 此設定可控制是否可以在會議和群組通話中開啟音訊。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外發和傳入音訊**    |會議允許外發和傳入音訊。 這是預設設定。 |
|**禁用**     |會議會關閉外發和傳入音訊。     |

如果使用者設為 **已停用** ，該使用者仍然可以排程和組織會議，但他們無法使用音訊。 若要加入會議，他們必須透過公用交換電話網路 (PSTN) 或透過電話加入會議。 未指派任何策略的會議 (例如，匿名) 預設會啟用此設定為外發和傳入音訊。  在 Teams 行動用戶端上，如果這項設定已停用，使用者必須透過 PSTN 撥入會議。

此設定不適用於 1：1 通話。 若要限制 1：1 通話，請設定 Teams [通話政策](teams-calling-policy.md) ，並關閉撥打 **私人電話** 設定。 這項設定也不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

此設定尚未適用于 Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD) 環境。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="mode-for-ip-video"></a>IP 影片模式

這是每個使用者的策略。 此設定可控制是否可以在會議和群組通話中開啟視像。 以下是此設定的值。

|設定值 |行為  |
|---------|---------|
|**已啟用外發和傳入視**    | 會議允許外發和傳入視像。 這是預設設定。 |
|**禁用**     | 會議會關閉外發和傳入視像。 在 Teams 行動用戶端上，使用者無法共用會議中的影片或相片。 <br><br>請注意，如果 **IP 音訊模式** 已停用，則 **IP 視** 障模式也會維持停用狀態。  |

如果使用者設為 **已** 停用，該使用者無法開啟視片或觀看其他會議參與者共用的影片。 未指派任何策略的會議 (例如，匿名) 預設會啟用此設定為外) **入視。**

這項設定不適用於會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。 

此設定尚未適用于 Microsoft 365 政府社群雲端 (GCC) 、GCC High 或美國 (DoD) 環境。

> [!NOTE]
> 請記住，此設定同時控制外發和傳入視音訊，而允許 **IP 視** 區設定則控制外發視。 若要深入瞭解，請參閱 [優先使用哪一個 IP 視視策略設定？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視像](#manage-audiovideo-for-meeting-participants)。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

### <a name="allow-ip-video"></a>允許 IP 視訊

這是每個召集人和每個使用者策略的組合。 視音訊是會議的重要元件。 在某些組織中，系統管理員可能會想要更多控制哪些使用者的會議有視音訊。 此設定可控制是否可以在使用者主持的會議以及使用者啟動的 1：1 和群組通話中開啟視訊。 在 Teams 行動用戶端上，此設定可控制使用者是否可以在會議中共用相片和影片。 

由已啟用此策略設定的使用者所組織的會議，如果參與者也已啟用策略設定，則允許會議參與者在會議中共用視像。 未指派任何策略的會議參與者 (例如匿名和) 繼承會議召集人的政策。

> [!NOTE]
> 請記住，此設定會控制外發視， **而 IP 視** 區模式設定則同時控制外發和傳入視音訊。 若要深入瞭解，請參閱 [優先使用哪一個 IP 視視策略設定？](#which-ip-video-policy-setting-takes-precedence) 以及管理會議參與者 [的音訊/視像](#manage-audiovideo-for-meeting-participants)。

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

如果 Daniela 以視音訊通話給 Amanda，則 Amanda 只能用音訊接聽電話。  當通話接通時，Amanda 可以看到 Daniela 的視像，但無法開啟視像。 如果 Amanda 打電話給 Daniela，Daniela 可以使用視像和音訊接聽電話。 通話接通後，Daniela 可以視需要開啟或關閉視像。

若要深入瞭解，請參閱 [管理會議參與者的音訊/影片](#manage-audiovideo-for-meeting-participants)。

#### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪一個 IP 視視策略設定優先？

對於使用者，視像的最嚴格政策設定會優先使用。 以下是一些範例。

|允許 IP 視訊|IP 影片模式|會議體驗|
|---------|---------|---------|
|召集人 **：On**<br><br>參與者 **：On** |參與者： **已停用**        |IP **視區模式設定** 會優先使用。 指派此政策的參與者無法開啟或觀看其他人共用的影片。|
|召集人 **：On**<br><br>參與者 **：On** |參與者： **已啟用外發和傳入視訊**          |指派此政策的參與者可以開啟或觀看其他人共用的影片。         |
|召集人 **：On**<br><br>參與者： **關閉** |參與者： **已啟用外發和傳入視訊**         |允許 **IP 視像** 設定優先。 參與者只能看到內送影片，而且無法傳送外寄影片。         |
|召集人 **：On**<br><br>參與者： **關閉** |參與者： **已停用**         |IP **視區模式設定** 會優先使用。 參與者看不到傳入或外發視。|
|召集人： **關閉**    |       |允許 **IP 視** 像設定會優先使用，因為召集人已關閉該設定。 在指派此策略的使用者所組織的會議中，沒有人可以開啟視像。         |

### <a name="manage-audiovideo-for-meeting-participants"></a>管理會議參與者的音訊/視像

|如果您想要...  |設定下列策略設定  |
|---------|---------|
|為會議參與者停用音訊和視像  |IP 音訊模式： **已停用**<br> IP 影片模式： **已停用**<br>允許 IP 影片：N/A       |
|只為會議參與者啟用傳入視音訊  |IP 音訊模式： **已啟用外接和傳入音訊**<br> IP 影片模式： **已啟用外接和傳入視訊**<br>允許 IP 影片： **關閉**       |
|停用會議參與者的視 (，讓參與者只能) |  IP 音訊模式： **啟用外接和傳入音訊**<br> IP 影片模式： **已停用**<br>允許 IP 影片：N/A        
|為會議參與者啟用音訊和視像    |IP 音訊模式： **已啟用** 外 (內) <br> IP 視訊模式： **已啟用外 (** 內) <br>允許 IP 視訊 **： (** 預設)     |

會議召集人原則與使用者原則之間的最嚴格原則會適用。 例如，如果召集人有限制視音訊的政策，而使用者的政策沒有限制視音訊，會議參與者會繼承會議召集人的政策，而且無法存取會議中的視像。 這表示他們只能使用音訊加入會議。

> [!NOTE]
> 當使用者啟動群組通話以使用電話加入時，不會顯示使用電話 **進行** 音訊畫面。 這是我們正在努力解決的已知問題。 若要解決此問題， **請選取其他** 連接選項下的 **電話音訊**。  

#### <a name="teams-mobile-clients"></a>Teams 行動用戶端

對於 Teams 行動用戶端上的使用者，會議期間共用相片和影片的能力也取決於允許 IP **視** 像或 **IP 視像模式** 設定。 視哪一個策略設定為優先，無法共用影片和相片。 這不會影響螢幕共用，因為螢幕共用是使用個別的螢幕 [共用模式設定來](meeting-policies-content-sharing.md#screen-sharing-mode) 設定。 此外，您可以設定 [Teams 行動](https://docs.microsoft.com/powershell/module/skype/new-csteamsmobilitypolicy) 能力政策，以防止行動使用者以行動網路連接使用 IP 視像，這表示他們必須使用 WiFi 連接。

### <a name="media-bit-rate-kbs"></a>媒體位元速率 (Kbs) 

這是每個使用者的策略。 此設定會決定使用者在通話和會議中進行音訊、視視和視視應用程式共用傳輸的媒體位元速率。 它同時適用于通話或會議使用者上行和下行媒體的傳輸。 此設定提供您管理組織中頻寬的精細控制。 根據使用者所需的會議案例，我們建議您有足夠的頻寬，以便獲得良好的品質體驗。 最小值為 30 Kbps，最大值取決於會議案例。 若要深入瞭解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱 [頻寬需求](prepare-network.md#bandwidth-requirements)。

如果會議頻寬不足，參與者會看到一則訊息，指出網路品質不佳。

針對需要最高品質的影片體驗的會議，例如 CEO 董事會會議和 Teams 即時活動，建議您將頻寬設定為 10 Mbps。 即使設定了最大體驗，當偵測到特定網路條件時，Teams 媒體堆疊也能夠根據案例調整成低頻寬條件。

## <a name="video-filters-mode"></a>視像篩選模式

<a name="bkvideofilters"> </a>

這是每個使用者的策略。 此設定可控制使用者是否可以自訂會議中的視音訊背景。

目前，您只能使用 PowerShell 來設定此策略。 您可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 編輯現有的 Teams 會議政策。 或者，使用 [New-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新的 Teams 會議策略，然後將該策略指派給使用者。

若要指定使用者是否可以自訂會議中的視訊背景，請設定 **VideoFiltersMode** 參數，如下所示：

|在 PowerShell 中設定值 |行為  |
|---------|---------|
|**NoFilters**     |使用者無法自訂其視音訊背景。|
|**模糊Only**     |使用者可以選擇模糊其視音訊背景。 |
|**模糊和定義Backgrounds**     |使用者可以選擇模糊其視像背景，或選擇使用預設影像組做為背景。 |
|**AllFilters**     |Use 可以選擇模糊其視像背景、選擇預設的影像集，或上傳自訂影像做為背景。 |

> [!NOTE]
> Teams 不會篩選使用者上傳的影像。 當您使用 **AllFilters** 設定時，您應該有內部組織原則，以防止使用者上傳令人反感或不當的影像，或是貴組織沒有許可權用於 Teams 會議背景的影像。






## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](assign-policies.md)

