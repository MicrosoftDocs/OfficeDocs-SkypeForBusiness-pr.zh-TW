---
title: 管理音訊和視訊的會議原則
ms.author: mabond
author: mkbond007
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: sonua, shalenc
audience: admin
ms.localizationpriority: medium
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
description: 瞭解如何在 Teams 中管理音訊和視訊的會議原則設定。
ms.openlocfilehash: 9e4e4ac9e2c1c63b9f45a71c5e006bba48ebbfc8
ms.sourcegitcommit: 81b3403a1a77ba202690c2d88bd8d1d5257048e5
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/14/2022
ms.locfileid: "69379369"
---
# <a name="meeting-policy-settings-for-audio--video"></a>音訊&視訊的會議原則設定

<a name="bkaudioandvideo"> </a>
<a name="ndi"> </a>

本文將說明音訊和視訊專屬的會議原則設定。 這些專案包括下列專案：

- [IP 音訊的模式](#mode-for-ip-audio)
- [IP 視訊的模式](#mode-for-ip-video)
- [IP 視訊](#ip-video)
- [媒體位元速率 (Kbps) ](#media-bit-rate-kbps)
- [視訊篩選模式](#video-filters-mode)
- [允許自訂背景設定](#allow-custom-background-settings)
- [ (FECC) 的遠端相機控制 (PTZ) 相機的平移傾斜縮放功能](#far-end-camera-control-fecc-for-pan-tilt-zoom-ptz-cameras)

## <a name="mode-for-ip-audio"></a>IP 音訊的模式

這是每一使用者原則。 此設定可控制是否可以在會議和群組通話中開啟音訊。 以下是此設定的值。

|設定值|行為|
|---|---|
|**已啟用傳出和傳入音訊**|會議中已允許傳出和傳入音訊。 這是預設設定。|
|**未啟用**|會議中已關閉傳出和傳入音訊。|

如果設定為 **[使用者未啟用** ]，該使用者仍然可以排程和組織會議，但他們無法使用音訊。 若要加入會議，他們必須透過公用交換電話網路 (PSTN) 撥入，或是撥打會議電話並透過電話加入會議。 未獲指派任何原則的會議參與者 (例如匿名參與者)，預設會將此設定為 [已啟用傳出和傳入音訊 **]**。 在 Teams 行動用戶端上，如果未啟用此設定，使用者必須透過 PSTN 撥入會議。

此設定不適用一對一通話。 若要限制一對一通話，請設定 Teams [通話原則 []](teams-calling-policy.md) 並關閉 [撥打私人通話 **]** 設定。 此設定也不適用會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

此設定尚無法於 Microsoft 365 政府社群雲端 (GCC)、GCC High 或美國國防部 (DoD) 環境中取得。

若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。

## <a name="mode-for-ip-video"></a>IP 視訊的模式

這是每一使用者原則。 此設定可控制是否可以在會議和群組通話中開啟視訊。 以下是此設定的值。

|設定值|行為|
|---|---|
|**已啟用傳出和傳入視訊**|會議中允許外寄和內送視訊。 這是預設設定。|
|**未啟用**|會議中已關閉傳出和傳入視訊。 在 Teams 行動用戶端上，使用者無法分享會議中的視訊或相片。 <br><br>請注意，如果 **IP 音訊模式** 未啟用，則 **IP 視訊模式** 也將維持未啟用狀態。|

如果設定為 **[使用者未啟用** ]，該使用者就無法開啟其他會議參與者共用的視訊或檢視視訊。 未獲指派任何原則的會議參與者 (例如匿名參與者)，預設會將此設定為 [已啟用傳出和傳入視訊 **]**。

此設定不適用會議室裝置，例如 Surface Hub 和 Microsoft Teams 會議室裝置。

此設定尚無法於 Microsoft 365 政府社群雲端 (GCC)、GCC High 或美國國防部 (DoD) 環境中取得。

> [!NOTE]
> 請記住，此設定同時控制外寄和內送視訊，而 **IP 視訊** 設定則會控制外寄視訊。 若要深入了解，請參閱[哪個 IP 視訊原則設定優先？](#which-ip-video-policy-setting-takes-precedence)和[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。

若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。

## <a name="ip-video"></a>IP 視訊

這是每個召集人和個別使用者原則的組合。 視訊是會議的重要元件。 在某些組織中，系統管理員可能會想要進一步控制哪些使用者的會議有視訊。 此設定可控制是否可以在使用者主持的會議以及在使用者啟動的一對一和群組通話中開啟視訊。 在 Teams 行動用戶端上，此設定會控制使用者是否可以在會議中共用相片和影片。

由已啟用此原則設定的使用者所召集的會議，如果參與者也已啟用此原則設定，則會允許由會議參與者在會議中分享視訊。 未獲指派任何原則的會議參與者 (例如匿名和同盟參與者) 會繼承會議召集人的原則。

> [!NOTE]
> 請記住，此設定可控制傳出視訊，而 [IP 視訊的模式 **]** 設定則可同時控制傳出和傳入視訊。 若要深入了解，請參閱[哪個 IP 視訊原則設定優先？](#which-ip-video-policy-setting-takes-precedence)和[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。

|Teams 桌面和 Web 用戶端|Teams 行動用戶端|
|:---:|:---:|
|![螢幕擷取畫面顯示在電腦上使用音訊/視訊設定加入會議。](media/meeting-policies-audio-video-settings.png)|![螢幕擷取畫面顯示在行動裝置上加入會議與音訊/視訊設定](media/meeting-policies-mobile-join.png)|

讓我們看看下列範例。

|使用者|會議原則|IP 視訊|
|---|---|---|
|Daniela|全域|開啟|
|Amanda|Location1MeetingPolicy|關閉|

由 Daniela 主持的會議允許開啟視訊。 Daniela 可以加入會議並開啟視訊。 因為加迪納的原則設為不允許視訊，因此在 Daniela 的會議中無法開啟影片。 Amanda 可以查看會議中由其他參與者分享的視訊。

在 Amanda 主持的會議中，沒有任何人可以開啟視訊，而無論指派給他們的視訊原則為何。 這表示 Daniela 無法在 Amanda 會議中開啟視訊。  

如果 Daniela 呼叫 Amanda 時有開啟視訊，Amanda 只能用音訊接聽通話。  當通話連接時，Amanda 可以看見 Daniela 的視訊，但無法開啟視訊。 如果 Amanda 呼叫 Daniela，Daniela 可以使用視訊和音訊接聽通話。 當通話連接時，Daniela 可以視需要開啟或關閉其視訊。

若要深入了解，請參閱[管理會議參與者的音訊/視訊](#manage-audiovideo-for-meeting-participants)。

### <a name="which-ip-video-policy-setting-takes-precedence"></a>哪些 IP 視訊原則設定優先？

若為使用者，針對視訊最具限制性的原則設定會優先。 以下是一些範例。

|IP 視訊|IP 視訊的模式|會議體驗|
|---|---|---|
|召集人：**開啟**<br><br>參與者：**開啟**|參與者：**已停用**|[IP 視訊的模式 **]** 設定優先。 獲指派此原則的參與者無法開啟或檢視由其他人分享的視訊。|
|召集人：**開啟**<br><br>參與者：**開啟**|參與者：**已啟用傳出和傳入視訊**|獲指派此原則的參與者可以開啟或檢視由其他人分享的視訊。|
|召集人：**開啟**<br><br>參與者：**關閉**|參與者：**已啟用傳出和傳入視訊**|**IP 視訊** 設定優先。 參與者只能看到傳入視訊，而且無法傳送傳出視訊。|
|召集人：**開啟**<br><br>參與者：**關閉**|參與者：**已停用**|[IP 視訊的模式 **]** 設定優先。 參與者看不到傳入或傳出視訊。|
|召集人：**關閉**||**IP 視** 訊設定優先，因為召集人已關閉此設定。 沒有人可以開啟由獲指派此原則的使用者所召集的會議中的視訊。|

### <a name="manage-audiovideo-for-meeting-participants"></a>管理會議參與者的音訊/視訊

|如果您想要...|設定下列原則設定|
|---|---|
|為會議中參與者停用音訊和視訊|IP 音訊的模式：**已停用**<br> IP 視訊的模式：**已停用**<br>IP 影片：不適用|
|僅為會議的參與者啟用傳入音訊和視訊|IP 音訊的模式：**已啟用傳出和傳入音訊**<br> IP 視訊的模式：**已啟用傳出和傳入視訊**<br>IP 影片： **關閉**|
|為會議中的參與者停用視訊 (參與者僅有音訊)|IP 音訊的模式：**啟用傳出和傳入音訊**<br> IP 視訊的模式：**已停用**<br>IP 影片：不適用
|為會議中參與者啟用音訊和視訊|IP 音訊的模式：**已啟用傳出和傳入音訊** (預設值)<br> IP 視訊的模式：**已啟用傳出和傳入視訊** (預設值)<br>IP 影片： **在** (預設) |

將套用會議召集人的原則與使用者原則之間最具限制性的原則。 例如，如果召集人有一個原則會限制視訊，而使用者的原則不會限制視訊，則會議參與者會繼承會議召集人的原則，且無法存取會議中的視訊。 這表示他們只能使用音訊加入會議。

> [!NOTE]
> 當使用者開始群組通話以使用電話加入時，不會出現 [使用手機的音訊 **]** 畫面。 這是已知問題，我們正在努力解決。 若要解決此問題，請在 [其他加入選項 **]** 下選取 [手機音訊 **]**。

### <a name="teams-mobile-clients"></a>Teams 行動用戶端

對於 Teams 行動用戶端的使用者，在會議期間分享相片和影片的功能也取決於 **IP 視** 訊或 **IP 視訊模式** 設定。 根據設定的優先原則為何，分享視訊和相片的功能均無法使用。 這不會影響螢幕畫面分享，這是您使用個別的 [螢幕畫面分享模式[]](meeting-policies-content-sharing.md#screen-sharing-mode) 設定進行的設定。 此外，您可以設定 [Teams 行動性原則](/powershell/module/skype/new-csteamsmobilitypolicy)，以防止行動裝置使用者透過行動數據連線使用 IP 視訊，這表示他們必須使用 WiFi 連線。

## <a name="media-bit-rate-kbps"></a>媒體位元速率 (Kbps) 

這是每一使用者原則。 此設定會決定使用者在通話和會議中音訊、視訊及視訊應用程式共用傳輸的媒體位元速率。 它會同時套用於通話或會議使用者的上行連結和下行媒體周遊。 此設定會提供您對組織中頻寬管理的細微控制。 根據使用者需要的會議案例而定，我們建議有足夠的頻寬，以便擁有良好的品質體驗。 最小值為 30 Kbps，而最大值取決於會議案例。 若要深入了解 Teams 中高品質會議、通話和即時活動的最低建議頻寬，請參閱[頻寬需求](prepare-network.md#bandwidth-requirements)。

如果會議頻寬不足，參與者會看到一則訊息，指出網路品質不佳。

對於需要最高品質視訊體驗的會議 (例如 CEO 委員會會議和 Teams 即時活動)，建議您將頻寬設定為 10 Mbps。 即使已設定體驗上限，視案例而定，Teams 媒體堆疊會在偵測到特定網路狀況時適應低頻寬情況。

## <a name="video-filters-mode"></a>視訊篩選模式

<a name="bkvideofilters"> </a>

這是每一使用者原則。 此設定可控制使用者是否可以自訂其會議中的視訊背景。

您可以使用 Teams 系統管理中心和 PowerShell 來設定此原則。 您可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) Cmdlet 來編輯現有的 Teams 會議原則。 或者，使用 [New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 來建立新 Teams 會議原則，然後將該原則指派給使用者。

若要指定使用者是否可以在會議中自訂視訊背景，請設定 **VideoFiltersMode** 參數 (在 Teams 系統管理中心選取 **視訊篩選** 設定) 如下所示：

|在 PowerShell 中設定值|在 Teams 系統管理中心中設定值|行為|
|---|---|---|
|**NoFilters**|**無篩選**|使用者無法自訂其視訊背景。|
|**BlurOnly**|**僅背景模糊**|使用者可以選擇模糊其視訊背景。|
|**BlurandDefaultBackgrounds**|**背景模糊和預設影像**|使用者可以選擇模糊其視訊背景，或從預設的影像集中選擇，以用作其背景。|
|**AllFilters**|**所有篩選**|使用者可以選擇模糊其視訊背景，從預設的影像集中選擇，或上傳自訂影像以用作其背景。|

> [!NOTE]
> Teams 不會篩選由使用者上傳的影像。 使用 **AllFilters** 設定時，您應該有內部組織原則，以防止使用者上傳冒犯性或不適當的影像，或組織無權用於 Teams 會議背景的影像。

## <a name="allow-custom-background-settings"></a>允許自訂背景設定

您可以新增自訂背景影像以供每個租使用者使用。 這項功能可讓公司將公司商標套用至 Teams 會議。

> [!NOTE]
> 若要上傳背景影像，您用來執行此程式的系統管理員帳戶必須具備 Teams 授權。

1. 登入 Teams 系統管理中心。

2. 選 **取 [會議** \> **會議原則** \> **] 自訂會議影像**。

   ![會議原則選取專案，其中醒目提示 [自訂會議影像] 按鈕。](media/custom-background-image-button.png)

3. 從 **組織寬背景影像** 選取 [**開** 啟]。

4. 選取 **+ 新增影像**。

5. 在 [管理背景] 面板中，選取 [ **新增影像]**。

6. 確定影像符合下列需求：
  
   - 最小大小 360 px
   - 最大大小 2048 px
   - PNG、JPG 或 BMP 的檔案類型
   - 最多可以上傳 50 張影像

7. 預覽您已選取的影像，然後選取 **[關閉]**。

8. 檢閱影像並視需要新增更多影像。

9. 選取 [儲存 **]**。

會議出席者會看到一系列背景影像，可在出席會議時使用這些影像。

> [!NOTE]
> 變更可能需要 24 小時才會生效。
>
> 這項功能暫時在公開預覽中提供給所有Microsoft Teams 客戶使用。 若要在預覽之後取得此功能，每個使用者都需要進階通訊附加元件授權。 如需詳細資訊，請參閱 [Microsoft Teams 的進階通訊附加元件](/microsoftteams/teams-add-on-licensing/advanced-communications) (部分機器翻譯)。

## <a name="far-end-camera-control-fecc-for-pan-tilt-zoom-ptz-cameras"></a> (FECC) 的遠端相機控制 (PTZ) 相機的平移傾斜縮放功能

遠端相機控制是可指派給Teams 會議室資源帳戶的原則。 它允許連線至 Teams 會議室的 PTZ 相機，在會議期間由 Teams 用戶端應用程式中的會議參與者控制。

若要使用遠端相機控制，會議參與者必須取得 **PTZ 相機控制項** 應用程式。  請參閱 [允許和封鎖應用程式](manage-apps.md#allow-and-block-apps) ，以瞭解如何在貴組織的應用程式市集中使用該應用程式。

若要指定誰可以在會議中使用遠端相機控制項，請使用[New-CsTeamsMeetingPolicy](/powershell/module/skype/new-csteamsmeetingpolicy) Cmdlet 建立並指派新原則給Teams 會議室資源帳戶，或使用[Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)來修改現有的原則。 `TeamsCameraFarEndPTZMode`將參數設定為下列其中一個值：

|設定值|行為|
|---|---|
|`Disabled`|這是預設設定。 設定為 `Disabled` 時，沒有人可以使用 PTZ 相機控制項。|
|`AutoAcceptAll`|PTZ 相機控制項會自動提供給任何會議參與者使用。|
|`AutoAcceptInTenant`|PTZ 相機控制項僅自動提供給與 Teams 會議室相同的組織中的參與者使用。|

設定 `TeamsCameraFarEndPTZMode` 為 `AutoAcceptAll` 或 `AutoAcceptInTenant` 時，在會議期間，仍然可以從 Teams 會議室手動關閉相機控制項。 當相機關閉時，相機控制也無法使用。

支援任何具有機械 PTZ 和 UVC 控制項的相機。 如需 Teams 認證的相機清單，包括 PTZ 和非 PTZ 相機，請參閱 [USB 音訊和視訊周邊裝置的認證韌體版本](rooms/requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)。 使用數位 PTZ 控制項的相機尚未支援此功能。  

> [!NOTE]
> 測試 PTZ 控制項之前，請先更新您的相機韌體。 請參閱原始設備製造商 (OEM) 檔以更新韌體。

## <a name="related-topics"></a>相關主題

- [Teams PowerShell 概觀](teams-powershell-overview.md)
- [在 Teams 中將原則指派給使用者](policy-assignment-overview.md)
