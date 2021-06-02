---
title: Microsoft Teams 適用的行動裝置必要診斷資料
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: majaisin
description: Microsoft Teams 適用的原則控制項的行動裝置屬性和事件清單。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: baea63a8ed51d2e47fa24b7602573b1dda342e93
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717984"
---
# <a name="required-mobile-diagnostic-data-for-microsoft-teams"></a>Microsoft Teams 適用的行動裝置必要診斷資料

下列文章包含 Microsoft Teams 行動裝置事件的清單，以及每個事件收集的屬性清單。

## <a name="events"></a>事件

> [!NOTE]
> 以下所列的所有事件有共同的屬性，若要檢閱這些屬性，請參閱[隨著所有事件傳送的屬性](#properties-sent-with-all-events)。

### <a name="panelaction"></a>PanelAction

> [!NOTE]
> 如需 PanelAction事件屬性的詳細資訊，請參閱[隨著面板動作事件傳送的屬性](#properties-sent-with-panelaction-events)。

- **accessibilityUserConfiguration** - 當使用者切換協助工具功能時。
- **acknowledgeSettingChange** - 確認 [我們已更新通知設定] 對話方塊中的更新。 這是用來確認更新通知並決定整體通知可靠性的功能成功度量值。
- **actionComposeMenu**
  - 建立訊息擴充使用量。
  - 操作訊息擴充使用量。
- **active_session_banner_dismissed** - 已關閉共用作用中提醒的位置。
- **activityChatClicked** - 當系統選取 **[活動]** 索引標籤中的 [非即時聊天]，或顯示出分割視圖時，進行觸發。
- **activityCoNtextMenu** - 活動摘要中的溢出動作。
- **activityFeedClick** - 已點選活動摘要專案，並瀏覽至聊天機器人。
- **activityFeedLongPress** - 在摘要專案上擷取長按手勢。
- **activityFeedSwipe** - 在摘要專案上擷取滑動手勢。
- **activityFilterClick** - 擷取活動篩選使用量。
- **activityFilterOptionsClick** - 擷取活動篩選使用量。
- **activityFilterOptionsClicked** - 擷取活動篩選使用量。
- **activityLiveChatClicked** -當系統選取 **[活動]** 索引標籤上的 [即時會議] 中的 [聊天] 時，進行觸發。
- **activityLiveDetailsClicked** - 當系統選取 **[活動]** 索引標籤上的 [即時會議] 中的 **[詳細資料]** 時，觸發。
- **activityTabClicked** -可協助您判斷：
  - **[活動]** 索引標籤已顯示。
  - 小組會擷取 **[事件]** 索引標籤事件。
- **activityTypeDropdown** -擷取活動篩選使用情況，以在 **[我的活動]** 和 **[摘要]** 之間進行切換。
- **addChannel** - 新增頻道。此項目提供成功建立頻道的成功資料。
- **addMember** - 已觸發選取 **[更多]** 功能表中的 **[邀請人員]** 按鈕。
- **addMembers** - 新增成員至小組或私人頻道。
- **addToCalendar** - 針對私人行事曆中遺失的行事曆事件，選取 **新增至行事曆** 按鈕。
- **addToList** - 已將連絡人新增至連絡人清單。
- **addToMeeting** - 選取會議參與者清單中的 **[新增至會議]** 按鈕 (適用于交談中的參與者)。
- **addUserAsContact** - 從連絡人個人檔案卡中選取 **[新增連絡人]** 圖示，即可新增連絡人。
- **admitAll** -從 [會議廳] 區段中選取 **[允許所有]** 按鈕的次數。
- **admitParticipant** - 從會議名單中允許某人進入會議的次數。
- **alertsNavAlert** - 點選摘要專案。
- **android：null** - 將聊天機器人設為靜音或取消靜音。 這會加強聊天中現有的遙測，只會增加應用程式資訊。
- **anonymousMeetingJoin** - 系統在匿名加入提供名稱頁面中選取 **[加入會議]**，或在名稱對話方塊中點選 **[確定]**。
- **anonymousMeetingJoinWelcome** - 系統在匿名加入會議登陸頁面中選取 **[以來賓身分加入]**。
- **anonymousMeetingPostMeetingChat** - 通話結束畫面中的聊天的使用者觀看次數。
- **anonymousMeetingPostMeetingRejoin** - 匿名使用者嘗試重新加入會議的次數。
- **anonymousMeetingSignIn** - 使用者從名稱輸入畫面瀏覽到登入畫面的次數。
- **anonymousMeetingSignInWelcome** 系統在匿名加入會議登陸頁面中選取 **[登入並加入]**。
- **anonymousMeetingToggleMuted** - 靜音切換按鈕已選取的次數。
- **anonymousMeetingToggleVideo** - 選取影片切換按鈕的次數。
- **appKilled** - 應用程式已終止。
- **approveTimeOffRequest** - 當前線工作者 (FLW) 主管批准前線工作者休假的要求時。
- **assigneeChange** - 當新的受託人被新增至工作專案時，觸發。
- **assignmentPickerClicked** - 選取 **[指派給]** 按鈕，並開啟受託人選擇器頁面。
- **assignmentRemoved** - 當選取 **x** 將受託人自工作專案移除時 (這是移除受託人的唯一方法)時，觸發。
- **attachmentAdded** - 確認工作中的附件已成功新增。
- **attachmentDeleted** - 確認工作中的附件已成功刪除。
- **attachmentUpdated** - 確認工作中的附件已成功更新。
- **audioOnlyLowBatteryBanner** - 由於電量不足，已選取 **[僅限音訊]** 選項。
- **audioOnlyPoorNetworkBanner** - 由於連線狀況不佳，已選取 **[關閉影片]** 選項。
- **audioUserDoubleTap** - 點兩下音訊參與者。
- **autoReconnectCallmebackCallDrop** - 選取通話結束畫面中的 **Callmeback** 按鈕的次數。
- **autoReconnectDialIn**
  - 已選取 [重新連線 UFD] 中的 **[撥入]** 按鈕。
  - 進行重新連線時，選取 **[撥入]** 按鈕的次數。
- **autoReconnectDialInonCallDrop** - 已選取 [通話中斷 UFD] 中的 **[撥入]** 按鈕。
- **autoReconnectDialOut** - 已選取 [重新連線 UFD] 中的 **[回電給我]** 按鈕。
- **autoReconnectRejoinonCallDrop** - 選取通話結束畫面中的 **[重新加入]** 或 **[重新撥號]** 按鈕的次數。
- **backFromCallMePSTN** - [回電給我] PSTN 號碼流程未完成。
- **backToPhotoShare** - 返回相機。
- **backToStageFromWhiteboard** - 從白板返回通話畫面。
- **backToWhiteboardFromStage** - 從通話畫面移至白板。
- **blockAnonymous** - 當：
  - 從設定中啟用通話設定封鎖無來電者識別碼的通話。
  - 從設定中停用通話設定封鎖無來電者識別碼的通話。
  - 從操作列表中啟用通話設定封鎖無來電者識別碼的通話。
  - 從操作列表中停用通話設定封鎖無來電者識別碼的通話。
- **blockCaller** - 封鎖：
  - 新的 iOS 通話操作列表中的號碼和連絡人。
  - 連絡人卡片中的連絡人和號碼。
  - 設定中的號碼。
- **blockChat** - 封鎖聊天機器人。 這會加強聊天中現有的遙測，且只會增加應用程式資訊。
- **botClickCardAction** - 連接器卡使用情況。
- **breakStartEndClicked** - 在螢幕上的時鐘中，已選取 **[開始]** 或 **[結束休息]** 按鈕。
- **breakStartEndTriggered** - 註冊使用者選擇使用「開始」或「結束」。
- **bucketSelected** - 確認已成功選取貯體。
- **bucketUnselected** - 確認已成功取消選取貯體。
- **bucketPickerClicked** - 確認已成功啟動貯體挑選器。
- **BYOELiveEventJoin** - BYOE (廣播您自己的事件) 使用者加入即時事件。
- **calendarLiveChatClicked** - 從 **排程** 索引標籤上的即時會議進行聊天。
- **calendarMeetingJoin** -  從行事曆選取的 **[會議加入]** 按鈕。
- **calendarTab** - 在底部導軌中選取 **[會議]** 索引標籤。對瞭解行事曆使用狀況，並比較底部導軌上的其他應用程式，或判斷在從底部列選取之後，在呈現行事曆文章時是否有問題上很有幫助。
- **calendarTabClicked** - 在下列情況中，這會顯示行事曆使用狀況，並允許您與底部導軌上的其他導航應用程式進行比較。 這可供您在下列情況下用以判斷是否有問題：
  - **[排程]** 索引標籤已顯示。
  - 底部導軌中的 **[會議]** 索引標籤已選取。
- **calendarUpcomingChatClicked** - 從 **[排程]** 索引標籤上的即將開始的會議進行聊天。
- **callAccepted** - 接受通話。
- **callAcceptedSFB** - 接受通話。
- **callAppPreference** - 已選取偏好通話應用程式。
- **callControlsManualDismiss** - 通話控制項已手動關閉。
- **callControlsManualInvoke** - 通話控制項是手動調用。
- **callHistoryItemExpand** - 通話記錄專案展開。
- **callHistoryTab** -  在 [通話] 中已選取 **[CallHistory]** 索引標籤。
- **callInProgressShown** - 將顯示**_進行中的通話_* 橫幅。
- **callMePSTNConnected** - **[與我通話]** 成功。
- **callOrMeetUpAddParticipants** - 觸發時機：
  - 已於一對一通話螢幕中點選 [新增參與者] 按鈕。
  - 在 [新增參與者] 中選取 [人員] (VoIP)。
  - 在 [新增參與者] 中選取 PSTN。
  - 在即時私人會議中新增人員。
  - 在即時私人會議中選取 PSTN。
  - 在即時私人會議中選取 [公司聯絡人]。
  - 在即時私人會議中選取 [裝置聯絡人]。
  - 在即時私人會議中新增參與者完成。
  - 在即時頻道會議中新增人員。
  - 在即時頻道會議中選取 PSTN。
  - 在即時頻道會議中選取 [小組成員]。
  - 在即時頻道會議中選取 [裝置聯絡人]。
  - 在即時頻道會議中新增參與者完成。
- **callOrMeetUpAddParticipantsDone** - 使用者完成其參與者新增。
- **callOrMeetUpAddRoom** - 觸發時機：
  - 已在名單中選取 **[新增會議室]**。
  - 已在 [新增會議室] 中選取搜尋結果。
  - 已針對 [附近] 選取 **[關閉]**。
  - 已針對 [附近] 選取 **[啟用 BT]** 或 **[位置]**。
  - 已在 [新增會議室] 中選取附近的會議室結果。
  - 已在 [新增會議室] 中選取建議的會議室結果。
  - 已在 [新增會議室] 中選取 **[完成]**。
- **callOrMeetUpAudioOffSwitch** - 當在即時通話或會面中，使用 [配套聯結] 模式時，翻轉 **[關閉音訊]** 按鈕。
- **callOrMeetUpAutoReconnect** - 不良網路效能會導致使用者的裝置進入 [自動重新連線] 模式。
- **callOrMeetUpCallAccepted** - 觸發時機：
  - 接受通話。
  - 接受 PSTN 通話。
- **callOrMeetUpCallEnded** - 觸發時機：
  - 已點選 **[結束通話]** 按鈕。
  - 當處於 CallOrMeetupLive 時，已點選 **[通話已結束]** 按鈕。
  - 當處於 lockScreen 時，已點選 **[通話已結束]** 按鈕。
  - 當處於通知時，已點選 **[通話已結束]** 按鈕。
  - 當處於 inApp 時，已點選 **[通話已結束]** 按鈕。
  - 當處於 callKit 時，已點選 **[通話已結束]** 按鈕。
  - 已點選 PSTN **[通話已結束]** 按鈕。
- **callOrMeetUpChatWithParticipants** - 當處於即時會議或通話中時，切換聊天。
- **callOrMeetUpDeviceAudioSwitch** - 觸發時機：
  - 將音訊來源切換至喇叭。
  - 將音訊來源切換至裝置。
  - 將音訊來源切換至藍牙。
  - 將音訊來源切換至關閉音訊。
  - 在即時會議或通話中，切換喇叭。
  - 在即時會議或通話中，將喇叭切換至 [關閉音訊]。
  - 當在即時通話或會面中，使用 [配套聯結] 模式時，翻轉 **[關閉音訊]** 按鈕。
  - 處於 PSTN 中時，切換裝置音訊。
- **callOrMeetUpEnterDriveMode** - 從 **[...]** 功能表手動切換至 [駕車模式]。
- **callOrMeetupExitDriveMode** - 已點選 **[結束駕車模式]** 按鈕。
- **callOrMeetUpHold** - 觸發時機：
  - 當您在即時會議或通話中時，已點選 **[保留]** 按鈕。
  - 在 PSTN 保留通話。
- **callOrMeetUpIncomingVideoSwitch** - 在即時會議或通話中時，關閉 IncomingVideo。
- **callOrMeetUpInvitedParticipants** - 觸發時機：
  - 在私人即時會議期間，於 **[其他受邀者]** 參與者群組的底部，已點選 **[查看全部]**。
  - 在即時頻道會議期間，於 **[其他受邀者]** 參與者群組的底部，已點選 **[查看全部]**。
- **callOrMeetUpJoinedParticipants** - 觸發時機：
  - 在私人即時會議期間，於 **[會議中]** 參與者群組的底部，已點選 **[查看全部]**。
  - 在即時頻道會議期間，於 **[會議中]** 參與者群組的底部，已點選 **[查看全部]**。
- **callOrMeetUpLobbyParticipants** - 觸發時機：
  - 在私人即時會議期間，於 **[會議廳]** 參與者群組的底部，已點選 **[查看全部]**。
  - 在即時頻道會議期間，於 **[會議廳]** 參與者群組的底部，已點選 **[查看全部]**。
- **callOrMeetUpMicrophoneSwitch** - 觸發時機：
  - 開啟麥克風。
  - 關閉麥克風。
  - 在即時會議或通話中，系統會選取 **[麥克風]** 按鈕。
  - 處於 PSTN 中時，切換麥克風。
- **callOrMeetUpMuteParticipant** -遠端參與者已設為靜音。
- **callOrMeetUpMuteParticipants** - 在即時會議或通話中將所有參與者設為靜音。
- **callOrMeetUpParticipants** - 在即時會議或通話中切換參與者。
- **callOrMeetUpRemoteMuteUFD** - 您已設為靜音 UFD。
- **callOrMeetUpResume** - 觸發時機：
  - 在即時會議或通話中，系統會選取 **[繼續]** 按鈕。
  - 在 PSTN 中繼續通話。
- **callOrMeetUpSearchParticipants** - 觸發時機：
  - 在私人即時會議期間，已點選會議參與者中的 **[搜尋]**。
  - 已在私人會議期間查看 **[會議廳]** 參與者群組後，點選 **[搜尋]**。
  - 已在私人會議期間查看 **[會議中]** 參與者群組後，點選 **[搜尋]**。
  - 已在私人會議期間查看 **[其他受邀者]** 參與者群組後，點選 **[搜尋]**。
  - 在即時頻道會議期間，已點選會議參與者中的 **[搜尋]**。
  - 已在即時頻道會議期間查看 **[會議廳]** 參與者群組後，點選 **[搜尋]**。
  - 已在即時頻道會議期間查看 **[會議中]** 參與者群組後，點選 **[搜尋]**。
  - 已在即時頻道會議期間查看 **[其他受邀者]** 參與者群組後，點選 **[搜尋]**。
- **callOrMeetUpVideoSwitch** - 觸發時機：
  - 開啟視訊。
  - 關閉視訊。
  - 在即時會議或通話中，已選取 [視訊] 按鈕。
- **callPark** - 觸發時機：
  - 已在 **[...]** 功能表中選取 **[駐留通話]**。
  - **[擷取]** 按鈕已選取。
  - 已在 [擷取] 對話方塊中選取 **[選取]**。
  - 已在 [擷取] 對話方塊中選取 **[取消]**。
- **callPreferenceSetting** - 通話偏好設定應用程式設定。
- **callsTabNewCall** - 已在 **[通話]** 索引標籤中選取 **[新通話]**。
- **callTransfer** - 已開始通話傳輸。
- **callVoicemailTab** -  已在 [通話] 中選取 **[語音信箱]** 索引標籤。
- **cameraPermissionCancel** -  已在 [相機權限] 對話方塊中選取 **[取消]**。
- **cameraPermissionGoToSettings** -  系統會從 [相機權限] 對話方塊瀏覽至 **[設定]**。
- **cancelEditMeeting** - 在選取 **[編輯會議]** 之後，請在 [會議排程器] 頁面上選取 **[關閉]** 按鈕。 當使用者放棄 [編輯會議] 選取時，就會登入。
- **cancelFileShare** -  已在 [確認] 對話方塊中選取 **[取消]**。
- **cancelFileUpload** -  已在 [上傳] 對話方塊中選取 **[x]**。
- **cancelMeeting** - 從 [會議詳細資料] 頁面選取 **[取消事件]**。 用來取得已取消會議數量的匯總資料。
- **cancelNavigationToLink** - 已選擇取消瀏覽。
- **cancelRequestToJoinTeam** - 取消加入小組的要求。
- **cancelRequestToJoinTeamError** - 取消加入要求的錯誤。
- **cancelNewMeeting** - 若記錄已放棄的 [建立會議] 選項，並確認在下列情況下導致問題的原因：
  - 在 [會議排程器] 頁面上已選取 **[關閉]** 按鈕。
  - 在選取 **[編輯會議]** 後，在 [會議排程器] 頁面上已選取 **[關閉]** 按鈕。
- **cardView- 不做為已指派** - 卡片檢視和卡片呈現。 卡片是重要的平臺構造，且需度量其使用方式和模式才能瞭解平臺使用狀況，並持續瞭解用戶端的潛在問題。 若要度量加入小組的任何錯誤，則必須使用此專案。
- **castPpt** - 事件觸發時機：
  - 已選取 PowerPoint 選項。
  - 已選取特定的 PowerPoint。
  - 已在檔案選取器頁面中選取 [小組和頻道] 資料夾。
  - 在檔案選擇器頁面中選取 OneDrive 資料夾。
  - 停止轉換工作模式。
  - 點選多工 PiP。
  - 從檔案查看中選取顯示選項。
- **castScreen** - 參考：
  - 點選共用畫面選項。
  - 停止螢幕共用工作模式。
  - 鄭在從檔案查看中選取顯示選項。
- **center_on_team_clicked** - 使用者已成功將地圖置於群組上。
- **channelFollow** - 開啟頻道通知。
- **channelUnfollow** - 關閉頻道通知。
- **channelsActiveSetting** - **[當我活躍於桌面時，通知我]** 之通知設定已變更。
- **chatCreation** - 成功建立聊天。
- **changeIsActiveSetting** - 變更桌面活動型通知。
- **頻道** - 聊天中的 [新增訊息] 按鈕或文字方塊。
- **channelDetails** - 頻道瀏覽資訊的時機：
  - 已選取頻道標頭。
  - 會瀏覽至頻道詳細資料頁面。
- **channelFollow/channelUnfollow** - 追蹤或取消追隨頻道。
- **channelNav** - 從任何位置瀏覽至頻道。
- **channelNavTab** - 在下列情況下，為 Teams 中的檔案提供成功和可查看資料：
  - 已在頻道中選取 **[檔案]** 索引標籤。
  - 有一個連接器卡回復。
- **channelNotificationSettings** - 觸發時機：
  - 已選取 **[新通知設定]** 對話方塊。
  - 已在頻道檢視中選取 [頻道通知設定] 按鈕。
  - 已選取頻道通知設定。
- **channelSelected** - 確認已成功選取一個新方案的頻道。
- **channelSendMessage** -觸發時機：
  - 已發送頻道訊息。
  - 在撰寫方塊中 @提及 機器人。
- **channelTabOverflow** - 選取頻道中的 **[更多]** 索引標籤。
- **聊天** - 參照：
  - 聊天中的 [新訊息] 按鈕或文字方塊。
  - 已選取 callHistory 專案上的一對一聊天。
  - 來自通話清單的一對一聊天選項。
- **聊天 - 不做為已指派** - 查看未讀取的聊天或編輯聊天名單，具體如下：
  - 將使用者新增至聊天時，選取 **[完成]** 按鈕。
  - 已選取 [聊天清單] 篩選器，以 [未讀取] 進行篩選。
- **chatAddChat** - 已點選 [新增成員至聊天] 按鈕(此動作與一對一聊天和群組聊天一樣)。
- **chatAllowJoinViaLink** -開啟或關閉 [聊天詳細資料] 頁面中的聯結連結功能。
- **chatAvatarEdit** - 追蹤 [聊天詳細資料] 頁面中有多少群組變更其頭像。
- **chatAvatarEditCamera** - 當使用者從即時相機摘要編輯頭像時，進行觸發。
- **chatAvatarEditGallery** - 當使用者從手機的圖庫編輯頭像時，進行觸發。
- **chatAvatarEditView** - 當使用者查看現有的頭像影像時，進行觸發。
- **chatListNavConversations** - 當使用者點進去聊天清單專案時。
- **chatCancelAudioCall** - 取消群組音訊通話 - [確認] 對話方塊。
- **chatCanceVideoCall** - 取消群組視訊通話 - [確認] 對話方塊。
- **chatCM_CopyText** 點選聊天快顯功能表上的 **[複製文字]**。
- **chatCM_DeleteMessage** 刪除聊天快顯功能表上的 **[刪除訊息]**。
- **chatCM_edit** - 點選聊天快顯工能表上的 **[編輯]**。
- **chatCM_Forward** - 點選聊天快顯功能表上的 **[轉寄]**。
- **chatCM_markUnread** - 點選聊天快顯功能表上的 **[標記為未讀取]**。
- **chatCM_save** - 點選聊天快顯功能表上的 **[儲存]**。
- **chatCM_SeenBy** - 點選快顯功能表選項上的 **[已查看]**。 已讀功能，例如 [讀取者] (readby)。
- **chatContactsEnter** - 已輸入 **[聊天連絡人]** 索引標籤。
- **chatDetails** - 在下列情況下，提供聊天詳細資料頁面的成功和可探索性資料：
  - 已選取聊天標頭。
  - 已瀏覽至聊天詳細資料頁面。
- **chatRecentEnter** - 已輸入 **[最近聊天]** 索引標籤。
- **chatSendMessage** - 傳送聊天訊息。
- **chatShareLink** 追蹤有多少使用者傳送群組邀請連結。
- **chatStartAudioCall** - 觸發時機：
  - 已點選一對一音訊通話按鈕。
  - 點選搜尋結果上的 **[音訊]** 按鈕。
  - 點選右側的 **[開始通話]** 按鈕。
  - 已點選 callHistory 專案中的一對一音訊通話。
  - 已點選語音信箱專案中的一對一音訊通話。
  - 放置群組音訊通話 - [確認] 對話方塊。
- **chatStartAudioCallOnBehalfOf** - 代理人會從操作列表中以老闆的姿態開始通話。
- **chatStartAudioCallOnBehalfOfMyself** - 代理人會從操作列表中以自己的身分開始通話。
- **chatStartAudioCallSFB** - 已點選一對一音訊通話按鈕。
- **chatStartVideoCall** - 觸發時機：
  - 已點選一對一視訊通話按鈕。
  - 點選搜尋結果中的 [視訊] 按鈕。
  - 已點選 callHistory 專案中的一對一視訊通話。
  - 放置群組視訊通話 - [確認] 對話方塊。
- **chatStartVideoCallSFB** - 已點選一對一視訊通話按鈕。
- **chatWithMeetingParticipants** - 從 [會議詳細資料] 頁面選取 **[聊天]** 索引標籤。
- **checkListAddClicked** - 已選取檢查清單區段中的工作詳細資料視圖內的 **[新增專案]**。
- **checkListItemAdded** - 已為工作建立檢查清單專案。
- **checkListItemDeleted** - 已自工作中刪除檢查清單專案。
- **checkListItemUpdated** - 已為工作更新檢查清單專案。
- **channelPickerClicked** - 確認已成功啟動頻道挑選器。
- **checklistSeeAllClicked** 當選取 [工作詳細資料] 內的 **[查看全部]** 按鈕，以查看所有檢查清單專案。
- **chicletExpand** - 瞭解在行動裝置上如何預覽卡片，以及預覽關閉行為。
- **clearFilter** - 在查看工作清單時，所有篩選條件都被清除的時候。
- **clickPhotoOfficeLens** - 選取 **[拍照]** - 啟動相機 (僅限 Android)。
- **clockInEntryTeamSelectionShown** - 當未打卡時，使用者選取小組進行打卡。
- **clockInOutClicked** - 在螢幕上的時鐘，已選取 **[上班打卡]** 或 **[下班打卡]** 按鈕。
- **clockInOutTriggered** - 註冊使用者的上下班打卡。在您已選取位置 (假設必須提供位置)後，這才會觸發。
- **closedBannerMessage** - 當通知的橫幅訊息關閉時，進行觸發。
- **closeLobbyBanner** - 會議廳快顯使用 **[關閉]** 按鈕進行關閉的次數。
- **commentAdded** - 確認已將註解新增至工作。
- **commentsClicked** - 確認已成功地啟動註解檢視。
- **commentUpdated** - 確認工作中的註解已成功更新。
- **companionBannerJoin** - 選取頂層橫幅中的 **[加入]**。
- **companionDismiss** - 關閉配套橫幅。
- **companionDismissProximity** - 關閉配套橫幅。
- **companionJoin** - 已在工作表上選取 [以配套選項加入]。
- **companionJoinProximity** - 透過配套橫幅加入。
- **completionStateChange** - 當在工作清單的篩選條件檢視中選取已完成或未完成的篩選條件切換時，進行觸發。
- **composeExpandComposer** -  已點選 **[格式]** 按鈕。
- **composeFilePick** - 本機檔案選擇器已啟動。
- **composeImagePicker** -  已點選 **[影像]** 按鈕。
- **composeLocation** -  已點選撰寫中的 **[位置]** 按鈕。
- **composeMention** - @提及。
- **composeOpenEmoticonPicker** - 已點選表情符號選擇器。
- **composeOpenFunPicker** - 已點選有趣選擇器。
- **composeParticipantAdded** - 當新增參與者至 [班次] 應用程式時。
- **composeSearchResult** - 訊息擴充結果選取，這對瞭解應用程式搜尋結果相關性很有幫助。 也增強了使用應用程式資料遙測傳送郵件功能。
- **composeSelectExtension** - 點選 [ME] 應用程式。
- **composeSendSmartReply** - 已點擊智慧回覆項目。
- **composeSendMessage** 增強使用應用程式資料遙測傳送郵件功能。
- **confirmAudioOn** - 使用者確認想開啟音訊。
- **confirmFileShare** -  已在 [確認] 對話方塊中選取 **[共用]**。
- **consultTransfer** - 觸發時機：
  - 選取 **[傳輸]** > **[先查閱]**
  - 傳輸目標設定為 [人員]
  - 傳輸目標設定為 [手機號碼]。
- **consultTransferCall** - 觸發時機：
  - 已啟動查閱通話。
  - 已在確認傳輸對話方塊中選取 [確認]。
  - 已在確認傳輸對話方塊中選取 [取消]。
  - 已選取 **[橫幅傳輸]** 按鈕。
  - 已選取 **[橫幅繼續]** 按鈕。
- **consultTransferChat** - 觸發時機：
  - 已啟動查閱聊天。
  - 已在確認傳輸對話方塊中選取 [確認]。
  - 已在確認傳輸對話方塊中選取 [確認]。
  - 已選取 **[橫幅傳輸]** 按鈕或 **[橫幅繼續]** 按鈕。
- **consumeVoiceMessage** - 已播放語音訊息。
- **ContactCard_SeeMoreOOF** - 查看更多長 OOF 訊息。
- **contactOrganizer** - 已選取 **[連絡人召集人]**。
- **交談、索引標間** - 已選取 [索引標籤]。
- **copyLink** - 複製頻道文章的連結。
- **contactActivity** - 已選取 [從連絡人卡片查看使用者活動] 的按鈕時。
- **[交談]** - 當使用者瀏覽至 **[聊天]** 或 **[貼文]** 索引標籤時。
- **cortanaClose** - 當使用者手動關閉 Cortana 畫布時。
- **cortanaEduCategorySelect** - 當使用者按一下教育提示類別項目時。
- **cortanaEduOpen** - 當 Cortana 畫布上顯示教育頁面時。
- **cortanaInvoke** - 當 Cortana 開始聆聽時。
- **cortanaKWSSwitchToggle** - 當使用者點選 Cortana 設定頁面中的 KWS 開關時。
- **cortanaMicPermissionDialogButtonClick** - 當使用者在 Cortana 畫布上授予或拒絕麥克風權限時。
- **cortanaOpen** - 當使用者開啟 Cortana 畫布時。
- **cortanaOptionsOpen** - 當使用者點選 Cortana 畫布上的選項按鈕時。
- **cortanaSafetyFirstActions** - 當使用者接受安全第一的宣告時。
- **cortanaSafetyFirstLaunch** - 當使用者在 FRE 完成後第一次開啟 Cortana 時。
- **cortanaSettingsOpen** - 當使用者透過按一下 Cortana 畫布上的 Cortana 設定按鈕開啟 Cortana 設定頁面時。
- **cortanaStopResponding** - 當使用者按一下 Cortana 畫布上的取消按鈕時。
- **cortanaUserSettingsLaunch** - 當使用者在 Teams 設定中開啟 Cortana 設定時。
- **cortanaVoiceSelect** - 當使用者在 Cortana 設定頁面中選取 Cortana 語音字型時。
- **createChannel** - 在下列情況下，針對新頻道建立，提供成功建立或捨棄動作所需的成功資料：
  - 已選取 **[建立頻道]** 頁面上的 **[完成]** 按鈕。
  - 已選取 **[建立頻道]** 頁面上的 **[取消]** 按鈕。
- **createComposeExtension** - 建立訊息擴充使用狀況，或操作 [ME] 的使用狀況。
- **createConversationClicked** - 當交談是與其他工作者一同建立時。
- **createDefaultPlannerPlan** - 當 [工作] 應用程式第一次被該群組中的任何人開啟時，系統會自動建立共用清單，檢查使用 Planner 服務所建立的自動清單。 當使用者第一次嘗試建立共用工作清單時，確認預設共用工作清單已在 Planner 中成功建立。
- **createOrJoinTeam** - 已選取 **+** 按鈕來建立或加入小組。
- **createPersonalPlan** -已建立個人清單，並使用 ToDo 服務建立檢查清單。 確認已在 [待辦事項] 中建立新的個人工作清單。
- **createPersonalSubtask** - 確認已成功建立個人子工作。
- **createPersonaltask** - 確認已成功建立個人工作。
- **createPlan** - 確認已成功建立共用工作清單。 確認已透過中介層成功建立共用方案。
- **createPlannerPlan** - 已建立共用清單、使用 Planner 服務建立的檢查清單。 確認已在 Planner 中建立新的共用工作清單。
- **createPlannerTask** - 檢查撥打給 Planner 服務的通話。 確認已在共用工作清單中成功建立工作。
- **createShiftClicked** - 當主管選取 **[建立班次]** 時。
- **createShiftOrTimeOffClicked** - 如果您選取 **[建立班次]** 或 **[休假]**，則會觸發。
- **createTask** - 用於當建立動作失敗時，Planner 服務的檢查通話。確認工作建立作業失敗。
- **createTaskList** - 當使用者從 [常用] 檢視瀏覽至建立方案檢視時。
- **createTeam** - 在下列情況下，針對新團隊建立，提供成功建立或捨棄動作所需的成功資料：
  - 已選取 **[建立團隊]** 頁面上的 **[完成]** 按鈕。
  - 已選取 **[建立團隊]** 頁面上的 **[取消]** 按鈕。
- **createTeam、createChannel** - 這項功能會針對團隊中的成員成功新增，提供成功的資料，且在下列情況下成功建立新的團隊：
  - 已選取 **[新增成員]** 頁面中的 **[跳過]** 按鈕([先有檢查])。
  - 已選取 **[新增成員]** 頁面中的 **[完成]** 按鈕([先有檢查])。
  - 顯示團隊或頻道建立確認。
- **crossCloudDialogCancel** -  已為跨雲端對話方塊選取 **[取消]**。
- **crossCloudDialogJoin** -  已為跨雲端對話方塊選取 **[以來賓身分加入]**。
- **dashboardNav** - 使用者瀏覽至聊天儀表板上的磚。
- **dateChanged** - 使用者修改了班次日期。
- **datePickerLaunch** - 確認日期選擇器已順利啟動。
- **dayClicked** - 當使用者看到其班次時，選取日檢視。
- **daySaved** - 使用者儲存每日的可使用時間，節省一天的班次。
- **declineTimeOffRequest** - 當使用者拒絕工作休假要求。 這是休假的重要功能，可供主管拒絕休假要求。
- **deleteClicked** - 當在 [工作詳細資料] 中選取 **[刪除]** 時，會顯示 [確認] 對話方塊。
- **deleteContact** - 使用者刪除現有的私人連絡人。
- **deleteMeeting** - 選取 [會議詳細資料] 頁面中的 **[刪除]** 按鈕。
- **deletePersonaltask** - 確認已成功刪除個人工作。
- **deletePersonalSubtask** - 確認已成功刪除個人子工作。
- **deletePlannerTask** - 確認共用工作刪除作業已順利完成。
- **deleteShift** - 班次刪除。
- **duration_picker_dismissed** - 當持續時間選擇器關閉時。
- **deleteTask** - 使用 Planner 服務驗證，以判斷刪除動作成功與否。 確認工作刪除失敗，也就是說，刪除工作不成功。
- **deleteVoicemail** - 已點選 [刪除語音訊息專案]。
- **demotedToAttendee** - 使用者降級簡報者 - 對話方塊中的 **[變更]** 按鈕。
- **denyParticipant** - 使用者拒絕某位使用者進入名單的次數。
- **descriptionChanged** - 確認共用工作描述已成功變更。
- **descriptionClicked** - 當使用者從工作詳細資料中選取 **[檢視描述]**。
- **detailsTabClicked** - 已在會議中選取 **[詳細資料]** 索引標籤。
- **deviceAddressBookSync** - 當 [設定] 頁面開啟通訊錄同步處理時，觸發。
- **deviceAddressBookUnsync** - 當 [設定] 頁面關閉通訊錄同步處理時，觸發。
- **dialIn** - 使用者選擇 [撥入] 會議 (不同的位置)。
- **dialInBadNetworkBanner** -  已針對不良連線橫幅選取 **[撥入]**。
- **dialInBadNetworkBannerCancel** - 已在原生對話方塊中取消 **撥入**。
- **dialInBadNetworkBannerConfirm** - 已在原生對話方塊中確認 **撥入**。
- **dialInCall** -  已在 **[撥入]** 快顯提示上選取 **[通話]**。
- **dialInCancel** -  已在 **[撥入]** 快顯提示上選取 **[取消]**。
- **dialOutCall** - 當使用者發生下列情況時，觸發：
  - 以 [駕車模式] 加入。
  - 選取 **[回電給我]** 快顯提示上的 **[通話]**。
- **dialOutCallAAD** - 當在操作列表中自 **[我的號碼]** 中選取任何號碼時
- **dialOutCallRecent** - 當在操作列表中自先前的最近號碼中選取任何號碼時。
- **dialOutCancel** -  已在 **[回電給我]** 快顯提示中選取 **[取消]**。
- **dialOutDialog** -  已在操作列表中選取 **[新號碼]**。
- **dialOutFailRetry** -  已從失敗橫幅中選取 **[重試]**。
- **DialPad** - 已從通話清單中選取 **[DialPad]** 按鈕。
- **disableCategory** - 停用通知類型或停用來電通知。
- **已停用 - ** 已在 [初次執行體驗 (FRE)] 中選取 **[略過通知]**。 這會為 FRE 流程提供略過通知的重要成功資料。
- **disableQuietDays** - 免打擾天數已停用。 免打擾天數的功能成功遙測。
- **disableQuietHours** -已停用免打擾時數。
- **discoverTeams** - 瀏覽至 [瀏覽及加入 Teams] 頁面。
- **Dismiss_earlycancelledCQF** - 已關閉 CQF 早期取消的通話表單。
- **Dismiss_ratemycallCQF** - 已關閉 CQF 評分我的通話表單。
- **Dismiss_ratemyliveeventCQF** - 已關閉 CQF 評分我的即時事件表單。
- **dismissBadNetworkBanner** -  已針對不良連線橫幅選取 **[關閉]**。
- **dismissFlyout** - 已選取 **[關閉]** 按鈕。
- **dismissModality** - 形式選擇器不需共用就會退出。
- **dismissModalityPicker** - 已選取 **[形式選擇器]** 按鈕。
- **dismissReadReceiptsNotice** - 已從功能注意事項中選取 **[瞭解]**。
- **dismissStartRecording** - 開始錄製時，解除錯誤。
- **dismissStopRecording** - 暫停錄製時，解除錯誤。
- **dismissUseWifiForVideoBanner** - 當使用者關閉橫幅時，進行觸發：
  - 這會告知使用者遠端參與者影片已遭封鎖，而使用者必須切換到 WiFi 才能看到它。
  - 這表示使用者必須切換到 WiFi 才能共用影片。
- **DLPDelete** - 使用者刪除了封鎖的訊息。
- **DLPEdit** - 使用者編輯了封鎖的訊息。
- **DLPOverride** - 使用者覆寫了封鎖的訊息。
- **DLPOverrideReport** - 使用者檢舉了誤報，並覆寫了訊息。
- **DLPReport** -使用者舉報了誤報。
- **DLPResolve** - 使用者嘗試解決 DLP 訊息。
- **DLPSeeOriginal** - 使用者已點選查看原始訊息。
- **downloadFile** - 有助於：
  - 判斷下載作業是否已啟動。
  - 判斷檔案是否已順利下載。
- **dragDatePickerHandle**
- **dtmfPSTNCall** - 已點選 DialPad 上的 [DTMF] 按鈕。
- **dueDateChanged** - 當使用者指派工作到期日時，進行觸發。
- **dueDatePickerClicked** - 當已選取 [工作詳細資料] 中的 **[到期日]** 按鈕時，觸發，並開啟到期日選擇器頁面。
- **dueDateSelected** - 當使用者在查看工作清單時，以到期日套用篩選條件時，進行觸發。
- **dueDateUnselected** - 當使用者在查看工作清單時，未以到期日套用篩選條件時，進行觸發。
- 在聊天訊息中 **編輯** - **[編輯]** 按鈕。
- **editChannel** - 使用者選取按鈕來編輯他們所擁有或管理的頻道。
- **editContact** - 使用者編輯現有的私人連絡人，可透過瀏覽至連絡人卡片來完成。
- **editMeetingResponse** - 從會議詳細資料頁面編輯會議回復。
- **editNavigation** -  已在 **[更多]** 功能表中選取 **[重新排序]**，以編輯末列應用程式順序。
- **editRsvpMeetingOptions** - 選取 **[盡快回覆]**，以變更先前的選取。
- **editShiftClicked** -編輯班次。
- **editSmartReply** - 已編輯智慧回覆項目。
- **editTeam** - 使用者可以點選按鈕來編輯他們所擁有或管理的團隊。
- **editTeam、editChannel** - 與團隊成員成功新增相關，且在下列情況下成功建立現有團隊：
  - 已選取 **[新增成員]** 頁面中的 **[取消]** 按鈕(現有團隊或頻道)。
  - 已選取 **[新增成員]** 頁面中的 **[完成]** 按鈕(現有團隊或頻道)。
- **emergencyCall** - 緊急通話位置通話方案。
- **emergencyCallDirectRouting** - 緊急通話放置直接路由。
- **emergencyCallLocationPolicyBased** - DialEmergency 使用 DialPad。
- **emergencycallSecurityDeskNotify** - 緊急通話已放置，安全性前台已通知。
- **enableCategory** - 與啟用時，通知設定相關：
  - 通知的類型。
  - 來電通知。
- **已啟用** - 與啟用初次執行體驗 (FRE) 流程中的通知相關：
  - 已在 [初次執行體驗 (FRE)] 中選取 **啟用通知**。
  - 已在提醒中選取 [啟用]。
- **啟用/停用** - 通話權限或連絡人權限 (僅限 Android)。
- **啟用、稍後** - 通知權限提示 **[接受]** 按鈕、初次執行體驗 (FRE) 通知權限 (iOS)。 這會擷取已啟用通知功能的人數，並提供相關資訊。
- **enablediOSPrompt** - 使用者實際上會在 iOS 通知權限提示中啟用通知。 這會在通知權限提示中提供從 iOS 啟用通知的使用者相關資訊。
- **enabledQuietDays** - 已啟用免打擾天數。
- **enableLocationPermission** - 當使用者為共用位置功能啟用位置權限時。
- **enableQuietDays** - 使用者啟用免打擾天數。
- **enableQuietHours** -已啟用免打擾時數。
- **endEditing** -  已按 **[儲存]** 按鈕。
- **endFileShare** -  已在檔案共用對話方塊上選取 **[返回]**。
- **endMyShift** - 共用模式的裝置數量或登出次數。
- **endPhotoShare** - 從相片共用 **x**。
- **entryPointClicked** - 選取 **[排程]** 索引標籤中的 **[要求]**。要求是用於當前線工作者 (FLW) 要求班次時間等等時。
- **endPSTNCallSelected** - 使用者結束 PSTN 和內容通話。
- **endPSTNCallShown** - 系統提示使用者結束 PSTN 或內容通話。
- **endVideoShare** - 從影片中共用 **x**。
- **errorShown** - 顯示錯誤。
- **展開/摺疊** - 裝置連絡人或公司連絡人區段。
- **expandCollapseSection** - 點選區段標題來展開或摺疊區段。
- **預期： atMention-Android： chatSendMessage-iOS： sendMsg** -@提及 撰寫方塊中的機器人。
- **Expected: botClickCardAction - Android: showCard - iOS: 遺失** - 點選卡片按鈕。卡片是重要的平臺構造，且需度量其使用方式和模式才能瞭解平臺使用狀況，並持續瞭解用戶端的潛在問題。
- **預期： chatSendMessage-iOS： composeSendMessage** - 點選 **[回復]** ，並在頻道中回復聊天機器人。
- **預期： composeSendMessage - Android： replyChannel -iOS：遺失** - 點選 **[回復]** ，並在頻道中回復聊天機器人。
- **預期： messageLike-Android： reactLike_CM** ，例如機器人訊息。
- **預期： messageUnread-Android： markAsLastUnread** - 訊息的快顯功能表選項。
- **federatedUpgradeNewChat** - 舊的聊天會升級至原生。
- **檔案** - 追蹤是否已在 [聊天和頻道檔案] 索引標籤中成功完成檔案。
- **fileSelected** - 已選取 PowerPoint 簡報。
- **fileThumbnailPreviewDownloaded** - 可協助辨識檔案的縮圖是否已順利呈現。
- **fileThumbnailPreviewFromCache** - 擷取是否成功顯示快取的縮圖，並協助辨識檔案的縮圖是否已順利呈現。
- **fileThumbnailPreviewNotAvailable** - 可協助辨識檔案的縮圖是否已順利呈現。
- **fillFrameVideo** -從操作列表填滿框架。
- **firstTimeSignedIn** 登入或註冊事件觸發者：
  - 登入成功。
  - 首次登入成功。
  - 使用者可以看到登入錯誤。
  - 記錄有關初次登入時所執行的 MAM/MDM 策略遙測。
  - 初次成功登入後，記錄應用程式安裝引用的參數。
- **fitToFrameVideo** -從操作列表調整為框架。
- **flipCamera** -翻轉相機。
- **forcedUpdateAccept** -使用者接受更新 [強制更新] 對話方塊中的應用程式版本。
- **forcedUpdateExit** -使用者關閉應用程式，而不是在 [強制更新] 對話方塊中更新應用程式版本。
- **forcedUpdatePrompt** - 用於當較舊版本的使用者可能無法取得最新的安全性和隱私權修正程式，而需要獲取的情況下。
- **formattingBold** -使用者選取粗體格式設定。
- **formattingHighlight** -使用者選取醒目提示格式設定。
- **formattingImportant** -使用者選取重要性。
- **formattingItatlics** -使用者選取斜體。
- **formattingTextColor** -使用者選取文字色彩格式設定。
- **formattingUnderline** -使用者選取底線。
- **FRE - 不做為已指派** - 記錄遙測關於應用程式啟動的 MAM/MDM 原則。 用於 MAM 和 MDM 的 Intune 整合遙測。 在初次執行體驗 (FRE) 期間提供失敗的成功資料。
- **freActionClicked** - **[開始使用]**、**[稍後嘗試]**，或在初次執行體驗 (FRE)中選取 **[關閉]** (GPS)。
- **freDone** - 初次執行體驗 (FRE) 已完成。
- **freTriggered** - 使用者在初次執行體驗 (FRE) 上檢視上班打卡。
- **funSearchQueryEntered** - 已輸入 Giphy 查詢。 Teams 中的 Giphy 附件功能的成功資料。
- **funSelectItem** - Giphy 影像已選取。 Teams 中的 Giphy 附件功能的成功資料。
- **galleryImage** - 影像上傳 - 圖庫。
- **get_directions_clicked** -已選取 **[取得方向]** 按鈕。
- **goToNotificationSettings** - 從 **[我們已更新 通知設定]** 對話方塊，移至 [通知設定] 頁面。
- **GPSPromptClicked** - 已在 OS 提示中選取 **[允許]** 或 **[不允許]**。允許 GPS 或不允許。
- **group_map_closed** - 使用者會從聊天中開啟地圖檢視。
- **group_map_open** - 使用者關閉地圖檢視。
- **groupCallJoin** - 使用者加入 [群組通話]。
- **groupClicked** - 當使用者選取班次群組時，進行追蹤。
- **guideMe** - 使用者會選取橫幅，通知他們 3P 的應用程式封鎖通知，並提供疑難排解指導方針。
- **hamburgerMenu** - 瀏覽至漢堡功能表。漢堡功能表包含重要動作，例如帳戶切換、通知設定、資料設定和設定檔設定。
- **handoffComplete** - 已移交此裝置上的會議或通話。
- **handoffJoin** 在操作列表上選取 [會議移交] 選項。
- **hardwareAudioOff** -透過硬體按鈕關閉音訊。
- **hardwareAudioOn** -透過硬體按鈕開啟音訊。
- **隱藏** - 隱藏聊天。
- **hideChannel** - 隱藏團隊和頻道清單中的頻道。
- **影像** - 影像。
- **immediateCallForward** - 已設定立即撥打轉接目標，或啟用立即撥打轉接 (已停用找我的來電)。
- **importanceToggleClicked** -當 **時觸發!** 欄位會在工作專案詳細資料內進行切換。
- **importantMessage_select** -使用者會從優先內容功能表中選取重要的訊息。
- **importantMessageSend** -使用者傳送重要的訊息。
- **inCallDialOut** -使用者從 [通話中其它] 選項中選取 **[回電給我]** 按鈕。
- **initiatePhotoShare** -啟動相片共用。
- **initiateVideoShare** - 啟動影片共用。
- **安裝** -安裝或安裝事件。
- **installReferrer** - 初次成功安裝後，記錄應用程式安裝引用的參數。
- **invisionWhiteboardClicked** - 已選取視覺白板：
  - **[頻道檔案]** 索引標籤。
  - 會議 **[聊天檔案]** 索引標籤。
- **inviteFreemium** - 在邀請畫面中點選 **+** 按鈕。
- **inviteGuest** - 在邀請畫面中點選 **+** 按鈕。
- **joinFromDeeplinkInTeams** - 從 Teams 應用程式內透過深度連結加入的使用者。
- **joinFromDeeplinkOutsideTeams** - 從 Teams 應用程式外透過深度連結加入的使用者。
- **joinFromJoinLauncher** - 從 [加入啟動器] 中加入的使用者。
- **joinFromNudge** -從 [輕推] 加入的使用者。
- **joinFromStore** -從應用程式商店下載應用程式後加入的使用者。
- **joinMeeting** - 在下列情況下，從行事曆中偵測加入會議的成功或失敗：
  - 透過 [撥入] 加入會議。
  - 透過 [回電給我] 加入會議。
  - 只加入會議內容。
  - 從 [議程] 檢視中選取 **[會議加入]** 按鈕。
- **joinOptionsEdu** - 教育界的使用者選取加入已排定會議的選項，且顯示正確的選項。
- **joinTeam** - 已按 **[加入]** 按鈕。
- **joinViaCode** - 使用者透過程式碼加入會議。
- **labelPickerClicked** - 確認已成功啟動標籤挑選器。
- **labelSelected** - 確認已成功選取標籤。
- **labelUnselected** - 確認已成功取消選取標籤。
- **launchLinksGallery** -當使用者從儀表板輸入連結資源庫時。
- **啟動來源，例如直接、連結、appShortcut** -直接或透過連結啟動 (錄製行動應用程式管理(MAM)，或行動裝置管理(MDM)遙測，以收集作用中使用者的資料)。
- **leaveChat** -確認離開聊天。
- **legacyChatLink** -已選取舊版聊天的連結。
- **likeAppDismiss** -當詢問使用者是否喜歡該應用程式的提示在沒有回應的情況下關閉時。
- **likeAppNo** - 當詢問使用者是否喜歡應用程式的提示收到 [否] 的回復時。
- **likeAppYes** - 當詢問使用者是否喜歡應用程式的提示收到 [是] 的回復時。
- **likeMsg** - 選取 **[喜歡]**。
- **linkPreviewCancel** - 瞭解預覽關閉行為。
- **listUserClicked** - 當使用者在 [正在執行中] 中選取使用者時。
- **liveCaptions** - 即時字幕已開啟或關閉。
- **liveEventAdditonalLink** - 已選取其他連結。
- **liveEventInfo** - 已選取 **[資訊]** 按鈕。
- **liveEventJoin** - 使用者加入即時活動。
- **liveEventLeave** - 已按 **[離開]** 按鈕。
- **liveEventPresenterJoin** - 簡報者已加入即時活動。
- **liveEventPresenterJoinAsAttendee** - 即時活動簡報者以出席者身分加入。
- **liveEventQnA** - 已選取 **[問與答]** 圖示。
- **liveEventYammer** - 已選取 **[Yammer]** 圖示。
- **liveMeetingPushNotificationClicked** - 已選取 [推送通知]。
- **liveMeetingToastClicked** - 已選取 [應用程式內快顯]。
- **live_location_in_chats_from_profile_clicked** - 已在設定檔檢視中選取 **[即時位置]**。
- **lobbyPickAudio** - 使用者從會議廳切換音訊輸出的次數。
- **lobbyToggleMuted** - 使用者從會議廳開啟或關閉麥克風的次數。
- **lobbyToggleVideo** - 使用者從會議廳開啟或關閉影片的次數。
- **logOutClicked** -使用者登出時。
- **location_active_tracking** -使用者的裝置切換為作用中追蹤。
- **locationCard** - 選取位置卡。
- **location_family_sync** -顯示在 MSA 系列應用程式中建立的 [家庭] 群組成員。 確認顯示出所有可授與授權的家庭成員。
- **location_group_map_sync** - 已開啟地圖檢視。
- **location_map_load** -地圖檢視載入。
- **location_map_markers_load** - 地圖檢視載入。確認所有主動共用的使用者位置標記都能在地圖檢視中正確顯示。
- **location_message_send** -使用者發起位置共用工作模式。
- **location_data_use_privacy_denied** -使用者在彈出通知上關閉或選取 **[現在不要]**，以 TFL 解釋位置資料之使用。
- **location_data_use_privacy_granted** -使用者在彈出通知上選取 **[允許]**，以 TFL 解釋位置資料之使用。
- **location_settings_open** -使用者開啟位置設定。
- **location_sharing_start** -使用者在聊天中共用其即時位置。
- **location_sharing_stop** -使用者在聊天中停止共用其即時位置。
- **loginFailed** -使用者無法登入。
- **loginSuccess** - 使用者可以登入。
- **manageBlockedNumbers** - 透過 [設定] 存取已封鎖的號碼。
- **manualSendMessage** - 已手動傳送郵件。
- **mapAppPicker** -當使用者在位置卡上點選時，選取要使用的地圖應用程式。
- **markAsRead** -標示為已讀取。
- **markAsUnread** -標示為未讀取。
- **markChannelRead** -使用者標示頻道已讀取。
- **messageBookmarkMessage** - 連接器卡儲存。 在應用程式特定資料中使用現有的遙測。 或儲存機器人訊息。
- **markAsLastUnread** - 連接器卡快顯功能表。
- **maskCallerId** -使用者啟用或停用通話設定以遮罩來電者識別碼。
- **meetingAttachmentFileClick** - 按一下會議附件項目。
- **meetingAttachmentFileOptions** - 按一下會議附件項目選項。
- **meetingAttachmentSeeMoreClick** - 按一下會議附件查看更多按鈕。
- **meetingDetailCalendarList** - 已從 calendarList 中選取 [會議詳細資料] 頁面，或選取 [會議詳細資料] 頁面上的 **[詳細資料]** 索引標籤。
- **meetingDetailChatWithParticipants** -從 [會議詳細資料] 頁面與參與者聊天。
- **meetingDetailDeleteMeetingforSelf** - 為某人從 [會議詳細資料] 頁面刪除 [會議]。
- **meetingDetailJoin** - 已選取 [會議詳細資料] 頁面上的 **[會議加入]** 按鈕。
- **meetingDetailParticipants** - 從 [會議詳細資料] 頁面上查看所有參與者。
- **meetingDetailScheduledMeeting** - 已從 [排定的會議物件] (**[...]**) 中選取 [會議詳細資料] 頁面，或選取已排定會議的 **[詳細資料]** 索引標籤。
- **meetingDetailSearchParticipants** -已選取 **[搜尋]** 會議排程中的會議參與者。
- **meetingInsightFileClick** - 按一下會議相關的檔案項目。
- **meetingInsightFileLocatorClick** - 按一下會議相關內容定位器提示按鈕。
- **meetingInsightFileOptions** - 按一下會議相關的檔案項目選項。
- **meetingInsightSeeMoreClick** - 按一下會議相關內容的查看更多按鈕。
- **meetingJoinLeave** - 保持點選 -> 在點選 **[加入]** 按鈕之後，點選 **[x]**。
- **meetingJoinNow** - **[立即加入 VOIP]** 已選取。
- **meetingJoinNowWithCallMe** -使用者使用 **[與我通話]** 加入會議。
- **meetingJoinNowWithPSTN** -使用者使用 [撥打] 加入會議。
- **meetingLeaveChat** -離開聊天。
- **meetingMuteChat** - 將聊天設為靜音。
- **meetingNotesCreatedInChatLink** - 已在 [私人會議聊天] 或 [頻道會議聊天] 中選取 **[會議筆記建立]** chicklet。
- **meetingNotesMentionCharLink** - 已在 [私人會議聊天] 中選取 @提及 連結。
- **meetingNotesMentionCharLink** - 已在 [頻道會議聊天] 中選取 @提及 連結。
- **meetingNotesTabEntryPoint** - 已在[私人會議] 或 [頻道會議] 中選取 **[會議筆記]** 索引標籤。
- **meetingNotificationSettingsAccepted** -通知設定選項已變更為 [僅限接受]。
- **meetingNotificationSettingsAll** -通知設定選項已變更為 [全部]。
- **meetingNotificationSettingsNone** -通知設定選項已變更為 [無]。
- **messagePriority_select** -已選取訊息優先順序進入點。
- **messageSeeOriginal** -使用者將已翻譯的訊息還原為原始訊息。
- **meetingSeeParticipantsChatDetails** -查看所有參與者。
- **memberListLoadMore** -向下捲動以載入更多。
- **messagedEditMessage** -使用者編輯訊息。
- **messageShareMessage** -分享訊息。
- **messageTranslate** -使用者翻譯訊息。
- **messageUnabletoEdit** -使用者無法編輯訊息。
- **meetingUserAnonB2B** -匿名 B2B 已加入會議。
- **meetingUserAnonB2C** -匿名 B2C 已加入會議。
- **meetingUserDialIn** PSTN ([撥入]) 使用者已加入會議。
- **meetingUserDialOut** - PSTN [回電給我] 使用者已加入會議。
- **meetingUserFederated** -聯合使用者已加入會議。
- **meetingUserFreemium** -免費增值使用者已加入會議。
- **meetingUserGuest** -來賓使用者已加入會議。
- **meetingUserTenant** -租使用者已加入會議。
- **messageCopyMessage** - 複製訊息。
- **messageDelete** - 訊息刪除。
- **messageEditMessage** - 編輯訊息。
- **messageForwardMessage** - 使用者從訊息快顯功能表選取 [轉寄] 進入點。
- **messageLike/messageUnlike** - 喜歡或不喜歡的訊息。
- **messageMuteSender** - 將寄件者設為靜音或取消靜音。
- **messageLike** - 像連接器卡。 在應用程式特定資料中使用現有的遙測。
- **messageScheduledMeeting** 已在頻道中選取會議物件 (不只是排定的會議)。
- **messageTriggered** -這是當訊息觸發通知時。
- **micPermissionCancel** -  已在 [麥克風權限] 對話方塊中選取 **[取消]**。
- **micPermissionGoToSettings** -使用者從 [麥克風權限] 對話方塊瀏覽至 [設定]。
- **MicrosoftWhiteboardClicked** - 已在 **[頻道檔案]** 索引標籤或 **[會議交談檔案]** 索引標籤上選取 [Microsoft 白板]。
- **moreOptionsClicked** - 當已選取工作專案編輯器畫面上的 **[...]** 功能表右上角時，觸發。
- **moveTaskClicked** - 工作專案更多選項清單內的選項。
- **multiCallEndFromUFD** -使用者在多重通話案例中以等候接聽方式結束通話的次數。
- **multiCallResumeFromUFD** -使用者選取以從等候中繼續通話的次數。
- **multiCallSwitch** -使用者選取選項來切換通話且顯示出保留通話清單的次數。
- **multipleAccounts** -使用者的帳戶數量。
- **multipleTenants** -每個帳戶的租使用者數目。
- **靜音** - 將聊天設為靜音。
- **muteOnWhiteboard** - 使用者在白板畫面上靜音或解除靜音。
- **muteParticipant** - 將參與者設為靜音 (移至操作列表)。
- **my_location_button_clicked** 使用者選取 **[我的位置]** 按鈕，將地圖放在其位置。
- **my_location_clicked** 使用者選取地圖上的 **藍色點點**，將地圖放在其位置。
- **myShiftPickerClicked** - 僅限登入的要求為 [切換] 或 [提出]。已選取 **我的班次** 選擇器。
- **nameGroupChat** -名稱群組聊天。
- **nativeTimeClockBreak** -上班的休息時間。
- **nativeChatLink** - 已選取本機交談的連結。
- **navActivity**- 瀏覽至 [活動摘要] 頁面。

- **navBookmark** -使用者瀏覽至底部列或應用程式列的 **[已儲存]** 索引標籤或應用程式。
- **navCalendar** - 度量是否使用者瀏覽至行事曆。
- **navCallingSettings** -使用者瀏覽到通話設定。
- **navCalls** -  已點選 **[通話]** 索引標籤。
- **navCamera** -使用者瀏覽至底部列或應用程式列的 **[相機]** 索引標籤或應用程式。
- **navChat** -使用者瀏覽至底部列或應用程式列的 **[聊天]** 索引標籤或應用程式。
- **navContacts** -使用者瀏覽至底部列或應用程式列的 **[連絡人]** 或 **[人員]** 索引標籤或應用程式。
- **navDashboardTab** -使用者瀏覽至交談中的 **[儀表板]** 索引標籤。
- **navDynamics365** - Dynamics365 應用程式開啟時觸發。
- **navFiles** - 已選取 [檔案] 應用程式，追蹤使用者是否可以在應用程式列 (iOS) 中啟動 [檔案] 應用程式。
- **navFilesTab** - 已選取 [檔案] 應用程式，追蹤使用者是否可以在底部瀏覽列 (iOS) 中啟動 [檔案] 應用程式。
- **navMeetings** - 已點選 **[行事曆]** 索引標籤。
- **navNotes** -當 [記事] 應用程式開啟時觸發。
- **navOrganization** - 當 [組織] 應用程式開啟時觸發。
- **navOrgChart** - 當 [Orgchart] 應用程式開啟時觸發。
- **navPeople** - 當 [人員] 應用程式開啟時觸發事件。
- **navPeopleSettings** -當您瀏覽至 [設定] 功能表中的 **[人員]** 類別時觸發。
- **navPersonalFiles** - 已選取 [檔案] 應用程式，追蹤使用者是否可以在底部瀏覽列 (Android) 中啟動 [檔案] 應用程式。
- **navPhotoTab** - **[相片]** 索引標籤。
- **navSaved** -使用者瀏覽至底部列或應用程式列的 **[已儲存]** 索引標籤或應用程式。
- **navSelectPlan** -當使用者選取要從 [常用] 檢視瀏覽到的共用方案時。
- **navSelectPersonalList** -當使用者選取要從 [常用] 檢視瀏覽到的個人方案時。
- **navSelectSmartList** -當使用者選取要從 [常用] 檢視瀏覽到的智慧方案時。
- **navTasks** -當 [工作] 應用程式開啟時觸發。
- **navTeams** 點選 **[查看全部]**。
- **navVideocamera** -使用者瀏覽至底部列或應用程式列的 **[相機]** 索引標籤或應用程式。
- **navVideoTab** - **[影片]** 索引標籤。
- **navVoicemail** -使用者瀏覽至 [語音信箱] 頁面。
- **navWalkieTalkie** 使用者已開啟 [對講機] 應用程式。
- **navWiki** -當 [Wiki] 應用程式開啟時觸發。
- **newChat** -使用者建立聊天。
- **newCall** -點選 **[新通話]** 按鈕。
- **newCallDialPad** - 點選索引標籤上的 **[Dialpad]** 按鈕。
- **newCallPeople** -點選索引標籤上的 **[人員]** 按鈕。
- **noBGActivityDetected** -超過背景活動失敗臨界值。
- **notBlockedDevice** -使用者無法在30天內達到背景活動失敗的臨界值。
- **notNow** - 已於 [提醒] 中選取 **[現在不要]**。
- **notNowUpdate** -UpdateDefer。
- **notificationNavChannelConversation** -使用頻道交談通知來啟動應用程式。
- **notificationNavChannelThreadConversation** -使用頻道交談中的特定訊息通知來啟動應用程式。
- **notificationSettingTurnedOff** - 關閉 Teams Android 應用程式的推送通知。
- **notificationNavPreCall** -在會議開始時，使用者會收到會議通知，並將他們導覽到選取範圍中的 [預先通話] 畫面。
- **ocvFeedback** - 與 OCV 回函表單的效能相關聯。
- **ocvFormCancelled** - 當 OCV 回函表單取消且使用者返回應用程式時，會傳送事件。
- **ocvFormOpened** - OCV 表單開啟時，傳送的事件。
- **ocvFormSubmit** - 當使用者點選 OCV 意見反映表單上的 [提交] 時，傳送的事件。
- **offerRecipientClicked** - 僅限登入的要求為 [提出方案]。 使用者進入團隊成員選擇器以提供班次。 [方案] 代表提供班次休假。
- **offerSwapShiftFromL1** -使用者嘗試從班次清單中提出或切換的班次類型。 iOS 動作是 **SwipedRight** 而 Android 動作是 **LongPressed**。
- **offerSwapShiftFromL1Triggered** -使用者提供與其他使用者交換班次。
- **officeLens** -當應用程式在下列情況下啟動 officeLens 相機功能時觸發：
  - 使用者嘗試將相片附加到訊息中
  - 使用者嘗試拍攝相片，並直接上傳到圖庫。
- **officeLens 或 cameraImage** - 已選取的相機圖片 - 標準相機或 office lens。
- **onBackClicked** - 每當選取 [返回] 箭回到頁面時。
- **oneNote** - 當使用者開啟 OneNote 應用程式時。
- **開啟** - [通知設定] 點選。
- **開啟編輯** -Wiki 使用遙測 - 使用者選取編輯 Wiki。
- **openApp** - 開啟個人應用程式。
- **openAppDrawer** - 已在底部列中選取 **[更多]** 以開啟應用程式選單。
- **openEditMeetingForm** - 從 [會議詳細資料] 頁面中選取 **[編輯]** 按鈕。
- **openFile** - 協助：
  - 若要識別檔案是否可以成功在聊天中開啟。
  - 若要識別檔案是否可以從檔案清單中開啟。
  - 檢查是否可以從 OneDrive 清單開啟檔案。
  - 若要識別從頻道清單開啟的開啟檔案。
  - 決定是否可以從群組聊天開啟檔案。
  - 決定是否可以從 [檔案] 應用程式成功開啟檔案。
  - 決定是否可以成功地從 chicklet 開啟訊息檔案。
  - 決定是否可以成功開啟 [最近] 清單中的檔案。
  - 決定是否可以成功開啟檔案清單中的檔案。
  - 決定是否可以從訊息檔案 chicklet 開啟檔案。
  - 決定是否可以從檔案清單成功開啟檔案。
- **openInAppClicked** - 工作專案更多選項清單內的選項，僅限個人工作使用。
- **opensCalendarView** - 點選 **[排程]** 索引標鉛上的 **[開啟班次]**。
- **openContactCard** - 使用者點選 **[連絡人]** 圖示或 [人員] 應用程式中的連絡人，以啟動該連絡人的設定檔卡。
- **openContactCard_ReactionSummary** -從 [反應摘要] 頁面瀏覽至 [連絡人卡片]。
- **openFileInApp** -可協助辨識是否使用者選擇要在 Teams 以外開啟檔案，或是在 Teams 內開啟。
- **openHamburgerMenu** -已選取 **[漢堡]** 圖示 (左上方)，開啟用於存取設定、目前狀態和租使用者切換器的側邊功能表。
- **openInStream** - 在 [Stream] 中開啟影片。
- **openMeetingDetails** - 開啟會議詳細資料，或是特定會議的 [開啟會議詳細資料] 頁面。
- **openModalityPicker** - X = 聊天和頻道的ChatsAndChannels。
- **openNewMeetingFrom** - 確認已成功更新個人子工作。
- **openNewMeetingForm** - 在設定新會議時開啟排程器。
- **openPhotoLibrary** - 選取相片文件庫。
- **openQuietDays** - 瀏覽至 [免打擾天數] 頁面。
- **openQuietHours** - 瀏覽至 [免打擾時數] 頁面。
- **openReactionHoverBubble** - 按[反應摘要] 頁面上的 **[新增反應]** 按鈕。
- **openReactionSummary** - 調用反應摘要選單。
- **openSettingsSetUpInstructions** - 從指示開啟 **[設定]**。
- **openSharedLink** - 當使用者開啟 [儀表板連結] 磚或 [連結] 庫的連結時。
- **openShiftsClicked** - 有多少人點選 **[行事曆]** 圖示。
- **組織圖 - 不做為已指派** - 組織圖的基本使用方式遙測。
- **pageEntered** -使用者輸入頁面。
- **parental_consent_grant** -使用者在其 MSFamily 中授與權限，以使用 TFL 中的即時位置功能。
- **parental_consent_remove** -使用者在其 MSFamily 中移除權限，以使用 TFL 中的即時位置功能。
- **pauseVoicemail** - 已在語音信箱專案上點選 **[暫停]**。
- **peoplePickerInvoked** - 在 Teams 行動裝置中的七個位置使用 [人員選擇器]，包括 (但不限於)：
  - 新增聊天選擇器。
  - 轉寄訊息。
  - 將參與者新增至會議。
- **personalAppNavBotChat** - 瀏覽至個人應用程式中的機器人。
- **personalAppNavTab** - 瀏覽至個人應用程式中的索引標籤。
- **photoLibraryPicker** - 在影像選擇器內，**開啟相片文件庫**。
- **pickGalleryPhoto** - 從圖庫挑選相片。
- **pickParticipantChatDetails** - 從清單中挑選使用者。
- **pickRecentPhoto** - 選擇最近使用的影像以共用。
- **pinChannel** - 釘選頻道，將它顯示在小組和頻道清單上方。
- **pinSelf** - 將自己從操作列表中釘選。
- **pinUser** - 將使用者從操作列表中釘選。
- **播放** - 播放錄製。
- **playVoicemail** -  已在語音信箱專案中點選 **[播放]**。
- **plusButtonClicked** - 選取 **[加號按鈕]** (**+**)。
- **pptNextSlide** - 以簡報者或私人檢視方式進行下一張投影片。
- **pptPrevioustSlide** - 以簡報者或私人檢視方式進行上一張投影片。
- **pptReturnToPresenter** - 移至 **[即時]** 投影片 (簡報者和其他人都在的投影片)。
- **pptStopPresenting** -停止簡報。
- **pptTakeControl** -取得控制權。
- **preJoinAddRoom** - 在 [預先加入] 下拉式清單中選取 **[新增會議室]** 按鈕，在 **[新增會議室]** 案例中選取 **[加入]**。
- **preJoinAudioOff** - 在 [預先加入] 下拉式清單中選取 **[關閉音訊]** 按鈕。
- **preJoinAutoAddRoom** - 當附近有會議時，選取 **[立即加入]**。
- **preJoinBack** -  已選取 **[返回]** 或 **[關閉]** 按鈕。
- **preJoinDenied** -使用者無法加入會議。
- **preJoinDeviceAudio** - **[使用裝置音訊加入]** 已從下拉式清單中選取。
- **preJoinDialIn** - 在 [預先加入] 下拉式清單中選取 **[撥入]** 按鈕。
- **preJoinDialInCall** - 使用者確認預先加入中的 **[撥入]** 要求。
- **preJoinDialInCancel** - 使用者取消預先加入中的 **[撥入]** 要求。
- **preJoinDialOut**-已選取 [預先加入] 下拉式清單中的 **[回電給我]** 按鈕。
- **preJoinDialOutCall** - 使用者確認預先加入中的 **[回電給我]** 要求。
- **preJoinDialOutCancel** - 使用者取消預先加入中的 **[回電給我]** 要求。
- **preJoinPSTNOptions** -使用者為其他加入選項選取下拉式清單。
- **priorityChange** - 在查看工作清單時，套用優先順序篩選的狀況下，觸發。
- **priorityPickerClicked** - 當使用者從工作清單篩選畫面瀏覽至優先順序篩選選擇器時，進行觸發。
- **privateMeetingJoin** -  已從 [私人會議聊天] 點選 **[會議加入]** 按鈕。
- **processInBG** - 處理背景中的內送通知(Android)。
- **processInFG** - 處理前景中的內送通知(Android)。
- **progressItemClicked** - 確認使用者已成功開啟工作的進度選擇器。
- **promotedToPresenter** - 使用者提升出席者 - 對話方塊中的 **[變更]** 按鈕。
- **provideFeedbackDismiss** - 關閉詢問使用者是否要傳送有關為什麼不喜歡應用程式的意見反應之快顯提示。
- **provideFeedbackNo** - 對詢問使用者是否要傳送有關為什麼不喜歡應用程式的意見反應之快顯提示回應為 [否]。
- **provideFeedbackYes** - 對詢問使用者是否要傳送有關為什麼不喜歡應用程式的意見反應之快顯提示回應為 [是]。
- **provideRatingDismiss** - 關閉詢問使用者是否要在回應喜歡該應用程式後，在應用程式商店為我們評分之快顯提示。
- **provideRatingNo** - 針對詢問使用者是否要在回應喜歡該應用程式後，在應用程式商店為我們評分之快顯提示回應為 [否]。
- **provideRatingYes** - 針對詢問使用者是否要在回應喜歡該應用程式後，在應用程式商店為我們評分之快顯提示回應為 [是]。
- **proximityPermissionDismissed** - 系統已關閉權限橫幅。
- **proximityPermissionGranted** - 會在快顯視窗中提供權限。
- **proximityPermissionViewed** - 已點選權限橫幅。
- **pushNotification** - 觸發事件為：
  - 透過通知啟動。
  - 已選取推送通知。
  - 已點選 [重新連結] 推送通知。
  - **[重新連結失敗]** 推送通知已點選。
- **quickNotificationAction** -當使用者與通知中的其中一個快速動作回應 (例如直接從推送通知中對訊息按讚的功能) 進行互動。
- **quickSelectImagePicker** - 快速選取。
- **quickStartLiveEventJoin** - 使用者已加入快速入門即時活動。
- **quietHoursValues** -在 [返回] 按鈕瀏覽中擷取免打擾時數狀態。
- **quotedReplySent** -使用者使用內容輸入傳送回復訊息。
- **reactAngry_CM** -從快顯功能表中傳送 [生氣] 表情符號。
- **reactAngry_HB** -從游標暫留顯示中傳送 [生氣] 表情符號。
- **reactHeart_CM** -從快顯功能表中傳送 [愛心] 表情符號。
- **reactHeart_HB** -從游標暫留顯示中傳送 [愛心] 表情符號。
- **reactLaugh_CM** -從快顯功能表中傳送 [大笑] 表情符號。
- **reactLaugh_HB** -從游標暫留顯示中傳送 [大笑] 表情符號。
- **reactLike_CM** - 從快顯功能表中按讚回應，或對機器人訊息按讚。
- **reactLike_doubleTap** - 透過點兩下按讚回應。
- **reactLike_HB** -從游標暫留顯示中按讚回應。
- **reactSad_CM** -從快顯功能表中傳送 [悲傷] 表情符號。
- **reactSad_HB** -從游標暫留顯示中傳送 [悲傷] 表情符號。
- **reactSurprised_CM** - 從快顯功能表中傳送 [驚訝] 表情符號。
- **reactSurprised_HB** - 從游標暫留顯示中傳送 [驚訝] 表情符號。
- **reactRemoved_HB** - 當使用者透過反應摘要頁面體驗，移除反應時。
- **readReceipts** - 使用者已啟用功能。
- **redeemInvite** - 在應用程式中的兌換。
- **refreshCalendarList** - 下拉以重新整理 [日程] 檢視。
- **refreshLinksGallery** - 當使用者向下滑動，以重新整理連結資源庫。
- **removeAssignee** - 確認受託人已從 [指派選擇器] 檢視中移除 (與透過選取 [指派選擇器] 檢視外的 **x** 所觸發的 *assignmentRemoved* 相反)。
- **removeMeeting** - 從已取消的會議的 [會議詳細資料] 頁面中選取 **[從行事曆移除]**。
- **removeParticipantFromEditMeeting** - 從 [會議詳細資料] 頁面選取 **[編輯會議]** 之後，移除參與者。
- **removeParticipantFromNewMeeting** - 在設定新會議時，從 [排程器] 頁面中移除參與者。
- **removeReplyObject** - 使用者已移除 [撰寫] 中的回覆物件。
- **removeUser** - 確認受託人已從 [指派選擇器] 檢視內移除 (與透過選取 [指派選擇器] 檢視外的 **x** 所觸發的 *assignmentRemoved* 相反)。
- **removeUser_CM** - 當使用者透過 [聊天參與者] 清單移除某人。
- **removeUserConfirm** - 使用者已確認 [移除使用者] 對話方塊。
- **removeUserCoNtextMenu** - 使用者透過 [快顯功能表] 移除參與者。
- **removeUserSwipe** - 使用者透過滑動移除參與者。
- **reorderChannelItem** - 使用者重新排序釘選的頻道。
- **reportAbuseConfirmation** - 當使用者選取確認畫面上的 **[完成]** 按鈕時。
- **reportAbuseOpen** 在快顯功能表中選取 **[舉報問題]** 按鈕的次數。
- **reportAbuseSend** - 當使用者選取 **[報告]** 按鈕時，遙測應儲存選取的報告類型。
- **replyChain** -已選取 **[新訊息]** 按鈕或回覆鏈 (執行緒) 中的文字方塊。
- **replyChannel** -已選取頻道中的 **[回覆]** 按鈕。
- **replyNavigation** - 已選取回覆物件，以瀏覽到參照的文章。
- **replySendMessage** -傳送頻道回覆。
- **replyViaMsgOptions** -使用者開始透過快顯功能表回覆。
- **replyViaSwipe** -使用者開始透過滑動回覆。
- **requestActedOn** - 當主管處理待認領班次要求時觸發。
- **requestActionClicked** - 當使用者要求採取動作時，例如當選取了班次要求時 (前線工作者 (FLW) 主管或前線工作者進行檢視。
- **requestDetailsClicked** - 當選取了班次要求時 (前線工作者 (FLW) 主管或前線工作者進行檢視)。
- **requestJoinTeam** - 已按 **[要求]** 按鈕。
- **requestSent** - 記錄檔，是否已傳送要求。
- **requestToJoinTeam** - 要求加入團隊 (公開或私下)。
- **requestToJoinTeamError** - 具有加入要求的錯誤。
- **requestTypeClicked** - 決定人員從要求選擇器中選取的要求類型。
- **resolveIssue** -  已在 [通知疑難排解] 中選取 **[解決]**，以瀏覽至封鎖程式應用程式。
- **responseClicked** - 使用者選取回覆頁面。
- **retryButtonClicked** -已選取 **[重試]** 按鈕。
- **returnToMessage** - 已選取 **[返回]** 按鈕，以瀏覽回訊息。
- **runningLate** -使用者遲到了。
- **safeLink** - 連結已驗證為安全。
- **saveEditMeeting** - 在更新會議之後，在 [會議排程器] 頁面上選取 **[儲存]** 按鈕。
- **saveNewMeeting** - 在 [會議排程器] 頁面上選取 **[儲存]** 按鈕。 若要記錄已成功儲存的會議，以及由於用戶端或服務錯誤而無法建立之會議的百分比。
- **savePlanClicked** - 會在預設開啟應用程式中的新方案建立器裡選取 **[建立]** 時觸發。
- **scheduledMeetingJoin** - 已從 [排定的會議] 物件中選取 **[會議加入]** 按鈕。
- **scrollCalendarList** - 在行事曆中測量卷軸。
- **scrollDatePicker** - 瀏覽行事曆日期選擇器控制項。
- **searchAbandoned** - 判斷搜尋是否已放棄。
- **searchCancelled** - 判斷：
  - 搜尋成功或使用者是否放棄搜尋。
  - 搜尋查詢成功。
- **searchContacts** - 從 [通話清單] 中搜尋。
- **searchIcon** - 判斷：
  - 是否可觸發搜尋。
  - 搜尋觸發項目的來源。
  - 是否成功找到相關結果。
- **searchInitiated** - 判斷是否可觸發搜尋，以及搜尋觸發項目的來源。
- **searchMeetingParticipants** -搜尋參與者以在排程表單中新增。 以區分建立的約會數量與建立的會議數量。
- **searchResultsClicked** - 判斷：
  - 是否能成功找到相關結果。
  - 是否搜尋結果來自 [全部] 索引標籤，或來自個別網域。
- **searchTab** - 判斷：
  - 搜尋結果的網域資訊 - 適用于人員、聊天、訊息和檔案。
  - 是否搜尋結果來自 [全部] 索引標籤，或來自個別網域。
- **searchTabClicked** - 判斷：
  - 搜尋結果的網域資訊 - 適用于人員、聊天、訊息和檔案。
  - 是否成功找到相關結果。
- **seeAllMeetingParticipants** - 從 [會議詳細資料] 頁面中選取 **[查看全部]**，或查看所有參與者。 在行事曆漏斗圖上記錄使用者資料，其中行事曆會議詳細資料會扮演重要的角色，可協助驗證 [撥入]、Teams 會議、RSVP 等選項。
- **seeMeetingDescription** - 開啟 [會議詳細資料] 頁面，或選取 [會議詳細資料] 頁面上的 [會議描述] 中的 **[查看更多]**。 資料會記錄在行事曆漏斗圖上，其中行事曆會議詳細資料會扮演重要的角色，可協助驗證 [撥入]、Teams 會議、RSVP 等選項。
- **seeRsvpMeetingOptions** - 從 RSVP 快顯提示中選取 **[通知召集人]**，或從 [會議詳細資料] 頁面中選取 **[Rsvp]** 選項。
- **selectActivityType** - 擷取內容在摘要專案上選取手勢。
- **selectCalendarDate** - 在 [行事曆日期選擇器] 控制項上選取特定日期。
- **selectDevice** - 在 [顯示] 應用程式中選取特定裝置。
- **selectGeneralSetting** - 移至 [一般設定]。
- **選取範圍** - 已選取裝置連絡人或已選取公司連絡人。
- **selectMeetingChicklet** |會議。
- **selectMeetingRsvpOption** - 選取 **[RSVP]** 按鈕以選擇選項。
- **selectMeetingRsvpOptions** - 選取 **[RSVP]** 按鈕以選擇選項。
- **selectPersonalList** - 透過點選來確認使用者成功地瀏覽到個人工作清單。
- **selectPlannerList** - 透過點選來確認使用者成功地瀏覽到共用工作清單。
- **selectSettingOption** - 移至 [漢堡] 功能表中的 **[設定]** 索引標籤。
- **selectTheme** - 啟用暗色調佈景主題。
- **selectUser** - 確認已成功選取工作受託人。
- **selfLongPress** - 請長按自己。
- **Send_earlycancelledCQF** - 使用者在 CQF 提前取消的通話表單上提交意見反應。
- **send_map_pin_clicked** - 使用者傳送靜態位置。
- **Send_ratemycallCQF** - 使用者在 CQF 評分我的通話表單上提交意見反應。
- **Send_ratemyliveeventCQF** - 使用者在 CQF 評分我的即時活動表單上提交意見反應。
- **sendForward** - 使用者確認要從轉寄選擇器傳送轉寄訊息。
- **sendImage** -傳送影像。
- **sendLocation** -傳送位置。
- **sendMsg** - 在回覆中選取 **[傳送]**。
- **sendRequestBulkClicked** - 針對每個大量要求傳送記錄一次。
- **sendRequestClicked** -  已選取 **[班次要求傳送]**。
- **sendVoiceMessage** - **[記錄]** 按鈕已釋出。
- **設定/解除** - 裝置連絡人設定。
- **settingsNavReadReceiptNotice** - 使用者從 [功能注意事項] 移至 [設定]。
- **settingsOpened** - 當使用者的裝置時區不符合團隊時區，且使用者移至 [設定] 時，就會觸發。
- **shareFile** - 當選取 **[共用檔案]** 時觸發。 也可協助您檢查：
  - 使用者能夠啟動共用檔案作業。
  - 使用者可以順利地共用檔案。
- **shareHistory** - 已選取 [共用歷史記錄選取器]。
- **shareInto** -- 使用者會從其他應用程式共用到 Teams 中。
- **sharePlanToChat** - 共用清單是從工作應用程式手動共用到群組聊天做為 chicklet，請透過後端訊息服務傳送檢查 chicklet。
- **sharePPTFromChannels** -  已選取 **小組和頻道**。
- **sharePPTFromOneDrive** -  已選取 **OneDrive**。
- **shareRecording** -共用錄製。
- **shareScreen** -開始或停止螢幕共用。
- **shareShift** -共用班次時所提供的資訊。
- **shareShiftsClicked** -待認領班次的詳細資料。
- **shareTray** - **共用…** 會操作列表中選取。
- **shiftAssigneeClicked** - 顯示特定班次詳細資料的 [班次行事曆] 檢視。
- **shiftDetails** -這可讓您查看班次的詳細資料。
- **shiftDetailsCalendar** -使用者移至班次詳細資料。
- **shiftDetailsMyShifts** - 點選 **[排程]** 索引標籤上的 **[行事曆]**。
- **shiftDetailsTodaysCoworkers** - 在螢幕上的時鐘中，已選取 **[開始]** 或 **[結束休息]** 按鈕。
- **shortCircuitContactCount** -[通訊錄] 與 [連絡人] 獲取的短巡迴連絡人相符的數量。
- **showBanner** - **WiFi 已連結、沒有網際網路** 橫幅出現的次數。
- **showCard** - 點選卡片按鈕。卡片是重要的平臺構造，且需度量其使用方式和模式才能瞭解平臺使用狀況，並持續瞭解用戶端的潛在問題。
- **shownReadReceiptNotice** - 使用者顯示的功能注意事項 (含設定選項)。
- **signIn** - 已在歡迎頁面上選取 **[登入]**，或已點選 **[登入]** 按鈕。
- **signUp** -  已選取 **[建立免費帳戶]** 或 **[免費註冊]**。
- **simultaneousCallForward** - 觸發時機：
  - 已設定同時通話轉接目標。
  - 已啟用同時通話轉接 (已啟用 [找我的來電] 且也已設定振鈴)。
- **skipVerificationForLink** - 使用者選擇略過驗證。
- **smartReply** - 已按下智慧回覆切換按鈕切換按鈕。
- **SMSSendMessage** - 使用者傳送 SMS 訊息。
- **sortChanged** - 當使用者在檢視工作清單下，變更排序次序時觸發。
- **startEditing** - **[編輯]** 按鈕已選取。
- **startPresentPhoto** - 開始呈現相片。
- **startPresentVideo** - 開始呈現影片。
- **startPSTNCall** - 觸發原因：
  - 全域搜尋 (人員) 中的 PSTN 結果。
  - 來自裝置連絡人卡片的 PSTN 通話。
  - 來自通話清單的 PSTN 通話。
  - 使用 DialPad 的 DialPSTN 號碼。
- **startRecording** - 開始錄製。
- **startVoicemailCall** - **[變更語音信箱問候語]** 已選取。
- **static_place_selected** - 使用者可拖動地圖來選取一個靜態位置。
- **statusCheckBoxClicked** - 當工作專案為 [已完成] 或 [未完成] 時觸發。
- **statusMsgCancel** - 使用者取消變更狀態訊息。
- **statusMsgExpiry** - 使用者設定到期時間。
- **statusMsgSet** - 使用者設定新的狀態訊息。
- **statusPageViaContactCard** - 使用者透過連絡人卡片輸入狀態撰寫體驗。
- **statusPageViaHamburger** - 使用者透過 [漢堡] 輸入狀態撰寫體驗。
- **stop_location_sharing_logout** - 使用者登出應用程式。
- **stopMeetingButton** - 使用者在不被允許加入會議的情況下離開會議廳的次數。
- **stoptPresentPhoto** - 停止呈現相片。
- **stopPresentVideo** - 停止呈現影片。
- **stopRecording** -停止錄製。
- **structuredMeetingsBannerDismiss** -使用者關閉通知其會議角色的橫幅。
- **stuckOnConnectingDialInSelected** -  已在選單中選取 **[撥入]**。
- **stuckOnConnectingRetrySelected** -  已在選單中選取 **[重試]**。
- **stuckOnConnectingShownDismissed** -使用者已關閉選單。
- **suggested_place_selected** - 使用者選取建議的位置來共用靜態位置。
- **switchTeamAction** - 使用者在上班中切換小組。 這會在使用者選取要切換到的小組之後觸發。
- **switchTeamsDialogTriggered** - 使用者檢視 **[班次]** 索引標籤。
- **tabActionCopyLink** - 使用者如何探索並使用行動裝置上的索引標籤複製連結。
- **tabActionMoreOptions** - 瞭解索引標籤中的省略號 (**[...]**) 的使用情況。
- **tabActionOpenInBrowser** - 在瀏覽器中開啟的使用情況。若使用者想要在 Teams 外開啟索引標籤，請務必瞭解此內容。
- **tabActionOpenInBrowserFromTab** - 瞭解 [索引標籤] 中的 [在瀏覽器開啟] 的使用情況，以獲得更多選項 (探索性和使用情況)。
- **tabActionOpenInTeams** - 開啟的使用情況。這是瞭解索引標籤是否可以在 Teams 中預設設為 [開啟] 的關鍵所在。
- **tabActionRemove** - 瞭解 [刪除] 選項的可探索性和功能的使用情況。
- **tabActionRename** - 瞭解 [重新命名] 的可探索性和功能的使用情況。
- **tabActionSetting、Android-修正** -使用者如何探索並使用行動裝置上的索引標籤。
- **資料表** - 選取資料表。
- **tabListMoreOptions** - 瞭解索引標籤的更多選項的使用方式。
- **tabOpen** - 注意事項：成功開啟索引標籤，或開啟索引標籤的方式中是否有問題。
- **tabViewed** - 僅限記錄是否傳送的要求為切換，以記入 **[團隊班次]** 選擇器。
- **takePhoto** -拍攝相片。
- **takePhotoPicker** - 在影像選擇器內選取的 **[拍攝照片]**。
- **tapChicletExpand** - 使用者如何預覽行動裝置上的卡片。
- **tapDatePickerHandle** - 展開 [行事曆日期選擇器] 控制項。
- **tapSettings** - 在行動裝置上重新設定應用程式的使用者數。
- **tasksAppLaunchAdaptiveCard** -[工作] 應用程式會從群組聊天中的 [適應卡片] 開啟，請透過 IC3 服務的 URL 檢查應用程式啟動。
- **tasksAppLaunchComposeExtension** - [工作] 應用程式會從群組聊天中的 [撰寫] 擴充功能開啟，透過 MT 服務檢查應用程式啟動。
- **tasksAppLaunchDashboard** -[工作] 應用程式會從儀表板磚或特定方案開啟，請透過 MT 服務檢查應用程式啟動。
- **tasksAppLaunchDashboardSeeAll** -[工作] 應用程式會從儀表板上的儀表板 **[查看全部]** 按鈕開啟，請透過 MT 服務檢查應用程式啟動。
- **tasksAppLaunchDefault** -[工作] 應用程式會從按鈕選單開啟，請透過 MT 服務檢查應用程式啟動。
- **tabCalendarClicked** - 使用者已從小組選擇器中選擇小組。
- **teamChannelChanged** - 當使用者選取並瀏覽至 [方案] 清單中的方案時觸發。僅傳送至 appInsights，而不是 Aria。
- **teamCreate** - 使用者選擇建立新小組的選項。
- **teamEdit** - 使用者編輯其所擁有或管理之小組的某些面向。
- **teamNav** 小組的 [檢視] 功能表選項。
- **teamsDeviceCallResumed** - 藍芽連接到外圍設備的使用者 (行動電話塢站) 會重新啟動保留的通話。
- **teamSelectedClicked** - 當使用者為時程表選取 **[已選取的小組]**。
- **teamShiftPickerClicked** - 當使用者新增新休息項目。 一旦使用者儲存變更，就會記錄事件。
- M **tenantSwitch** - 開啟 [切換租使用者]。TMA (多個租使用者和多個帳戶) 功能的成功度量，可協助主動識別並修正問題，並提供流暢的切換體驗。
- **tenantSwitchUnsupportedError** - 租用戶不支援錯誤 (當使用者看到錯誤時)。MTMA (多個租用戶和多個帳戶) 功能的成功度量，針對帳戶或租使用者切換錯誤提供遙測，所以能主動識別並修正問題，並提供流暢的切換體驗。
- **timeClockClicked** - 使用者可選取 [我的班次] 索引標籤上的 **[上班打卡]** 按鈕。
- **timeOffReasonClicked** - 判斷是否提及休假的原因。
- **timesheetAddClicked** - 當使用者在其休息編輯中新增注意事項時。 一旦使用者儲存變更，就會記錄事件。
 **timesheetBreakAdded** - 新增一個新的時鐘項目。 一旦儲存變更，就會記錄事件。
- **timesheetBreakEdited** - 當使用者確認其時程表時。 當使用者在強制回應中點選 [確認] 時，就會記錄事件。
- **timesheetBreakNoteAdded** - 當使用者刪除其時程表時。 當使用者在強制回應中確認刪除時，就會記錄事件。
- **timesheetClockAdded** - 當使用者選取 [編輯] 時程表時。
- **timesheetClockEdited** 當使用者在已編輯的時程表上選取 [儲存] 時。
- **timesheetConfirmed** - 當使用者在其時程表編輯中新增注意事項時。 一旦使用者儲存變更，就會記錄事件。
- **timesheetDeleted** - 是否使用者設定或不設定班次提醒，以及使用者想在班次開始前收到提醒的分鐘數。
- **timesheetEditClicked** - 使用者組態遙測。
- **timesheetEditSaved** - 使用者從使用者的設定檔中點選時程表，以開啟該使用者的時程表。
- **timesheetNoteAdded** - 查看核准的休假要求。
- **titleChanged** - 當工作專案標題變更時觸發，當每個字元有所變更時觸發。
- **快顯提示** - 已選取應用程式內的快顯提示。
- **toggleChannelsInChat** - 開啟或關閉功能。 整合的聊天和頻道體驗的功能成功度量值。
- **toggleClicked** - 已選取切換。
- **transferNow** - 觸發時機：
  - 使用者選取 **[傳輸]** > **[立即傳輸]**。
  - 傳輸目標設定為 [人員]。
  - 傳輸目標設定為 [電話號碼]。
- **translateFailed** - 翻譯失敗 (離線時除外)。 訊息翻譯功能的功能成功度量值。
- **unansweredCallForward** - 已設定未回復的通話轉接目標。 同時啟用未回復的通話轉接 ([找我的來電] 已啟用，且若已啟用未回復)。
- **unblockCaller** -解除封鎖：
  - 操作列表的連絡人或號碼。
  - 連絡人卡片中的連絡人或號碼。
  - 設定裡的號碼。
- **unblockChat** - 解除封鎖聊天機器人。
- **unpinChannel** -解除釘選頻道。
- **unpinSelf** - 解除將自己釘選在操作列表中。
- **unpinUser** - 解除將使用者釘選在操作列表中。
- **unsafeLink** - 已判斷為不安全的連結。
- **updatePersonalTask** - 確認已成功更新個人工作。
- **updatePlaybackSpeedVoicemail** -語音信箱回放速度值已變更。
- **updateTask** - 確認更新工作動作失敗。
- **updateTaskState** - 確認工作狀態已更新。動作。
- **更新** - 選取 **[更多]** 功能表中的 **[更新]** 按鈕。
- **uploadFile** - 使用者選取 **[從裝置上傳]**。
- **uploadSelectedFile** - 在下列情況下觸發：
  - 成功在頻道中上傳檔案。
  - 成功在聊天中上傳檔案。
  - 在回復視窗中上傳檔案。
  - 成功在群組聊天中上傳檔案。
  - 核心案例的使用方式。
  - 在頻道中開始上傳案例。
  - 在聊天中開始上傳案例。
  - 在頻道中開始上傳案例結尾。
  - 成功將檔案上傳至 **[檔案]** 索引標籤。
  - 如果在檔案上傳過程中，開啟提示。
  - 如果已成功上傳所選檔案。
- **uploadSelectFile** - 成功選取檔案；成功選取 **[上傳檔案]** 按鈕。
- **urgentMessageSelect** - 從優先快顯功能表中選取緊急訊息。
- **urgentMessageSend** - 傳送緊急訊息。
- **url** - URL。
- **urlPreview** - URL 預覽。
- **urlPreviewAdd** -URL 預覽新增。
- **urlPreviewOpen** -URL 預覽開啟。
- **urlPreviewRemove** -已移除 URL 預覽。
- **userConfiguration** - 檢視擱置的休假要求。
- **userJoinedViaShareLink** -使用者已從連結加入會議。
- **userLongPress** - 長按參與者。
- **userProfileOpened** - 使用者選取 **[使用者]** 圖示以開啟使用者設定檔。
- userTimesheetOpened** - 使用者從使用者設定檔中選取時程表，以開啟該人員的時程表。
- **useWifiForAudioDialog** - 當系統提示時，使用者選取 **[確定]** ，而系統管理員已封鎖手機上的音訊和視訊通話。
- **useWifiForVideoDialog** - 觸發時機：
  - 當系統提示時，選取 **[確定]** ，而系統管理員已封鎖手機上的視訊通話。
  - 嘗試在會議中啟用視訊，而系統管理員已在手機上封鎖視訊功能。
  - 當系統提示時，選取 **[確定]** ，而系統管理員已封鎖手機上的視訊會議。
- **videoUserDoubleTap** - 點兩下視訊參與者。
- **viewChannelMembers** - 查看頻道成員清單。
- **viewContactCard** - ContactCard 選取的專案：
  - CallHistory 專案。
  - 語音信箱專案。
  - 通話清單。
- **已檢視** - 使用者已檢視頁面。
- **viewFullAllDayMeetingList** - 行動裝置上的日程檢視。
- **viewLobbyFromBanner** - 使用者從通知橫幅中選取 **[查看會議廳]** 的次數。
- **viewMeetingDetails** - 在 [會議詳細資料] 頁面上選取 **[...]** 功能表。 關於行動裝置行事曆上的 **[更多]** 功能表的使用情況。
- **viewMeetingOccurrence** - 開啟週期性會議實例的會議詳細資料。 在行事曆漏斗圖上遙測以記錄使用者資料，其中行事曆會議詳細資料會扮演重要的角色，可協助驗證選取撥入、Teams 會議、RSVP 等選項。
- **viewMeetingSeries** - 在下列情況中記錄會議系列的成功呈現：
  - 當從實例切換到系列會議詳細資料頁面。
  - 當從 [會議詳細資料] 頁面中選取 **[檢視系列]**。
- **viewOrgChart** - 組織圖的基本使用方式遙測。
- **viewRequests** - 已按下 **[檢視要求]** 按鈕。
- **voiceDataCollectionOptOut** - 使用者按一下橫幅，即能從行動裝置退出錄製。
- **語音信箱- 不做為已指派** - 演講者點選語音信箱專案。
- **whiteboardUsed** - 使用者在白板上解釋 (網頁視圖上的任何動作)。
- **wiki - 不做為已指派** - Wiki 使用情況遙測。
- **poorNetworkBanner** - 顯示網路連線不佳的橫幅。
- **badNetworkBanner** - 顯示網路品質差的橫幅。

### <a name="panelview"></a>PanelView

> [!NOTE]
> 如需 PanelView 事件屬性的詳細資訊，請參閱[隨著 panelview 事件傳送的屬性](#properties-sent-with-panelview-events)。

- **fileDeleteFailed** - 檔案刪除作業失敗時觸發。
- **fileDeleteSuccess** - 檔案刪除作業成功時觸發。
- **filePreview** - 在下列情況下觸發：
  - 在檔案預覽畫面中點選共用選項時。
  - 在檔案預覽畫面中點選複製選項時。
  - 在檔案預覽畫面中點選下載選項時。
  - 成功載入檔案預覽時。
- **file** - 在下列情況下觸發：
  - 在 Teams 應用程式內預覽檔案時。
  - 在 OneDrive 檔案畫面中點選檔案上傳選項時。
  - 在檔案預覽畫面中點選 [複製連結] 選項時。
  - 關閉檔案共用畫面時。
  - 開啟檔案選項功能表時，或點選該功能表中的其中一個選項時。
  - 開啟「通話中」檔案畫面時。
  - 點選檔案以開啟時。
- **filesChannel** - 開啟頻道檔案畫面時觸發。
- **fileSources** - 開啟檔案選項功能表或點選該功能表中的其中一個選項時觸發。
- **filesPersonal** - 在 OneDrive 或最近使用的檔案畫面中載入一批檔案時觸發。
- **fileUploadDeleteTriggered** - 當檔案附件從訊息區域刪除或分離時觸發。
- **fileUploadFailed** - 檔案上傳作業失敗時觸發。
- **fileUploadIndividualNotification** - 當檔案上傳通知的內容變更或與通知互動時觸發。 互動可能包括手勢，例如滑動以關閉通知或點選通知等。
- **fileUploadSuccess** - 檔案上傳作業成功時觸發。
- **fileUploadSummaryNotification** - 當檔案上傳摘要通知的內容變更或與通知互動時觸發。 互動可能包括手勢，例如滑動以關閉通知或點選通知等。
- **meetingFiles** - 開啟會議檔案畫面時觸發。
- **navPersonalFiles** - 執行瀏覽至檔案畫面時觸發。

### <a name="scenario"></a>案例

> [!NOTE]
> 如需 PanelAction 事件屬性的詳細資訊，請參閱[隨著案例事件傳送的屬性](#properties-sent-with-scenario-events)。

- **app_incremental_sync_launch** 確認已成功更新冷啟動的計數。
- **app_incremental_sync_resume** 確認已成功更新暖/熱啟動的計數。
- **app_start_cold** 監視應用程式冷啟動 (僅適用於 Android)。
- **app_start_hot** 監視應用程式熱啟動 (僅適用於 Android)。
- **app_start_warm** 監視應用程式暖啟動 (僅適用於 Android)。
- **chat_add_giphy** - 確認 Giphy GIF 呈現動作成功或失敗。
- **cortanaError** 監視 Cortana 錯誤發生。
- **cortanaView** - 監視 Cortana 畫布顯示。
- **cortanaRestart** 監視 Cortana 重新啟動。
- **cortanaSetNewConversation** 監視 Cortana 設定新的交談。
- **cortanaSpeechRecognization** 監視 Cortana 語音辨識延遲。
- **cortanaStart** 監視 Cortana 後端啟動。
- **cortanaStartListening** 監視 Cortana 開始聆聽。
- **cortanaStopListening** 監視 Cortana 停止聆聽。
- **cortanaThinking** 監視 Cortana 狀態變更為思考 (等待服務的回應)。
- **cortanaTokenRefresh** 監視前景中的 Cortana 權杖重新整理。
- **cortanaWarmingUp** 監視 Cortana 暖機開始 (Cortana 已開啟，但權杖仍在擷取中)。
- **cortana_admin_policy_refresh** - 監視 Cortana 系統管理原則重新整理。
- **cortana_background_token_refresh** - 監視 Cortana 權杖重新整理。
- **cortana_initialization** - 監視 Cortana 初始化步驟。
- **cortana_sdk_events** - 監視 Cortana 相關事件。
- **cortana_skill_action_execution** - 監視 Cortana 動作執行。
- **cortana_skill_action_delay** - 確認延遲動作的開始。
- **cortana_watchdog** - 監視 Cortana 看門狗復原程式。
- **create_default_plan_and_nav_to_view** - 確認已成功建立預設的共用工作清單，以及在動作之後使用者導向結果所需的時間。
- **create_personal_plan_and_nav_to_view** - 確認已成功建立個人工作清單，以及在動作之後使用者導向結果所需的時間。
- **create_personal_task** - 確認已成功建立個人工作專案。
- **create_planner_plan_and_nav_to_view** - 確認已成功建立共用工作清單，以及在動作之後使用者導向結果所需的時間。
- **create_planner_task** - 確認已成功建立共用工作專案。
- **forwardExistingAmsObject** 確認媒體轉送動作成功或失敗。
- **delete_personal_plan** - 確認已成功刪除個人工作清單。
- **delete_personal_task** - 確認已成功刪除個人工作專案。
- **delete_planner_plan** - 確認已成功刪除共用工作清單。
- **delete_planner_task** - 確認已成功刪除共用工作專案。
- **get_sender_sub_scenario** - 取得活動中的寄件者子案例。
- **load_chat_plans_list** - 確認已成功取得聊天方案檢視的 Planner 方案。
- **load_home_page** - 確認已成功取得主要 [常用] 檢視的個人和共用工作清單。
- **load_personal_task_list** - 確認工作清單檢視的個人工作清單之工作已成功取得。
- **load_shared_task_list** - 確認工作清單檢視的共用工作清單之工作已成功取得。
- **load_smart_task_list** - 確認工作清單檢視的智慧工作清單之工作已成功取得。
- **meetingAttachmentRender** - 確認會議附件的呈現。
- **meetingInsightFetch** - 確認會議相關內容的擷取。
- **meetingInsightLocatorRender** - 確認會議相關內容定位器提示的呈現。
- **meetingInsightRender** - 確認會議相關內容的呈現。
- **meetingInsightVisible** - 確認會議相關內容的能見度。
- **open_image** 確認全螢幕影像呈現成功或失敗。
- **rename_personal_plan** - 確認已成功重新命名個人工作清單。
- **rename_planner_plan** - 確認已成功重新命名共用工作清單。
- **save_image** 確認影像儲存動作成功或失敗。
- **share_image** 確認影像共用動作成功或失敗。
- **smart_reply_enabled** - 確認已為目前使用者啟用智慧回覆。
- **smart_reply_received** - 確認已收到智慧回覆建議。
- **smart_reply_banned** - 確認無法為目前使用者顯示智慧回覆。
- **update_planner_task_and_nav_to_view** - 確認已成功更新共用工作專案，以及在動作之後使用者導向結果檢視所需的時間。
- **update_personal_task_and_nav_to_view** - 確認已成功更新個人工作項目，以及在動作之後使用者導向結果檢視所需的時間 
- **updatePlannerTask** - 確認使用者已成功更新共用工作清單中的工作。
- **upload_images** 確認影像上傳動作成功或失敗。
- **upload_voice_messages** 確認語音訊息上傳動作成功或失敗。
- **voiceMessageUpload** 確認語音訊息上傳動作成功或失敗。
- **cancel_channel_meeting** 確認頻道會議的取消作業成功或失敗。
- **cancel_meeting** 確認會議的取消作業成功或失敗。
- **cancel_private_meeting** 確認私人會議的取消作業成功或失敗。
- **edit_channel_meeting** 確認頻道會議的編輯作業成功或失敗。
- **edit_meeting** 確認會議的編輯作業成功或失敗。
- **server_fetch_agenda_view** 確認使用中介層 API 進行行事曆活動的同步處理成功或失敗。
- **server_fetch_date_picker_view** 確認使用 Outlook REST API 進行行事曆活動的同步處理成功或失敗。
- **server_fetch_agenda_view_group** 確認 TFL 群組使用中介層 API 進行行事曆活動的同步處理成功或失敗。
- **server_fetch_date_picker_view_incremental** 確認使用 Outlook REST API 進行行事曆活動的增量同步處理成功或失敗。
- **meeting_details** 確認會議詳細資料同步處理成功或失敗。
- **show_meeting_participants** 確認顯示會議參與者清單成功或失敗。


## <a name="property-lists"></a>屬性清單

### <a name="properties-sent-with-all-events"></a>隨著所有事件傳送的屬性

| 屬性名稱                    | 說明                                                          |
|----------------------------------|----------------------------------------------------------------------|
| EventInfo_Time                   | 事件產生時間                                                |
| EventInfo_Name                   | 事件名稱 - 用來區分事件類型               |
| EventInfo_BaseType/name          | 事件類型 - 用來區分事件中的事件類型   |
| EventInfo_Source                 | 事件產生的來源                                       |
| AppInfo_Language                 | 應用程式語言                                                         |
| AppInfo_ETag                     | 指派給使用者的實驗識別碼                                     |
| DeviceInfo_OsBuild               | OS 的組建版本                                              |
| UserInfo_Mri                     | 輸入使用者識別碼                                                       |
| Session_RunId                    | 工作階段識別碼的類型                                                 |
| DeviceInfo_DetailModel           | 裝置的模型                                                  |
| UserInfo_TimeZone                | 使用者的時區                                                |
| DeviceInfo_OsName                | 裝置作業系統名稱                                                       |
| DeviceInfo_NetworkProvider       | 裝置網路提供者                                              |
| DeviceInfo_Model                 | 裝置型號                                                         |
| DeviceInfo_NetworkType           | 裝置網路類型                                                  |
| UserInfo_Language                | 使用者語言 - 類似於應用程式語言                              |
| client_ring/UserInfo_Ring        | 使用者環可協助將功能釋出給早期採用者           |
| UserInfo_Id                      | 使用者識別碼                                                              |
| UserInfo_TenantId                | 租用戶識別碼                                                            |
| EventInfo_SdkVersion             | 用來產生事件的 SDK 版本                               |
| DeviceInfo_Id                    | 裝置作業系統提供的裝置識別碼                                      |
| eventpriority                    | 活動的優先順序                                                 |
| DeviceInfo_Make                  | 裝置製造商。                                                  |
| AppInfo_Version                  | 應用程式的版本                                                   |
| DeviceInfo_OsVersion             | 裝置作業系統版本                                                    |
| Session_Id/SessionId             | 要求的工作階段識別碼                                            |
| Session_Evinorment              | 工作階段環境                                                  |
| isNetworkIssue                   | 若在服務要求時，發生網路問題，會補擷取資訊 |
| UserRole                         | 租使用者中的使用者角色                                                |
| Tenant_Model                     | 如果帳戶為免費增值或企業版帳戶，則會擷取          |
| licenseType/UserInfo_LicenseType | 指派給使用者的授權類型                                    |
| UserLocale                       | 正在存取的應用程式的地區設定                                |
| Intune_sdkVersion                | Intune SDK 版本                                            |
| Intune_sdkBundleVersion          | 詳細的 Intune SDK 版本                                   |
| AppInfo_Environment              | 正在存取的應用程式的環境                         |

### <a name="properties-sent-with-panelaction-events"></a>隨著面板動作事件傳送的屬性

| 屬性名稱         | 說明                                                        |
|-----------------------|--------------------------------------------------------------------|
| Action_DestinationUri | 透過使用者動作存取之資源的 URI                  |
| Panel_Uri             | 傳送給使用者的面板的 URI                             |
| Action_Gesture        | 使用者在應用程式上執行的手勢類型                       |
| Action_ScenarioType   | 與功能的商務度量相關的功能群組       |
| Panel_Type            | 使用者存取的面板類型                                    |
| Action_Outcome        | 使用者執行的動作結果                            |
| Team_Id               | 使用者執行動作所在的小組識別碼           |
| Module_Type           | 主控使用者動作所在的模組類型                        |
| Module_Name           | 主控使用者動作所在的模組名稱                        |
| Module_Summary        | 主控使用者動作的模組摘要                      |
| Thread_Id             | 使用者存取的執行緒識別碼                         |
| Panel_PreviousUri     | 上一個面板的 URI                                          |
| Panel_Region          | 面板代管在應用程式中的所在地區                       |
| Panel_LaunchMethod    | 啟動面板的方法                        |
| Panel_PreviousType    | 上一個面板的類型                                         |
| Thread_Type           | 使用者存取的執行緒類型                                    |
| Module_State          | 使用者存取的模組狀態                               |
| Action_Scenario       | 與商務度量相關的功能群組內的功能 |
| Panel_LaunchSource    | 所啟動面板的來源資訊                  |
| Tab_Type              | 使用者存取的標籤類型                                   |
| Team_Type             | 使用者存取的小組類型                                      |

### <a name="properties-sent-with-panelview-events"></a>隨著面板檢視事件傳送的屬性

| Panel_Uri          | 傳送給使用者的面板的 URI                   |
|--------------------|----------------------------------------------------------|
| Panel_Type         | 使用者存取的面板類型                          |
| Team_Id            | 使用者執行動作所在的小組識別碼 |
| Thread_Id          | 使用者存取的執行緒識別碼               |
| Panel_PreviousUri  | 上一個面板的 URI                                |
| Panel_Region       | 面板代管在應用程式中的所在地區             |
| Panel_LaunchMethod | 啟動面板的方法              |
| Panel_PreviousType | 上一個面板的類型                               |
| Thread_Type        | 使用者存取的執行緒類型                          |
| Panel_LaunchSource | 所啟動面板的來源資訊        |
| Tab_Type           | 使用者存取的標籤類型                         |
| Team_Type          | 使用者存取的小組類型                            |

### <a name="properties-sent-with-scenario-events"></a>隨著案例事件傳送的屬性

| 屬性名稱        | 說明 |
|----------------------|-------------|
| Scenario_Status      | 案例狀態 - 放棄/確定/錯誤 |
| Scenario_Step        | 當案例包含多個具有不同失敗點的步驟時，此屬性會擷取該步驟的詳細資料 |
| Scenario_StatusCode  | 屬性根據案例成功或失敗來記錄案例的狀態代碼 |

### <a name="properties-sent-with-trace-events"></a>使用追蹤事件傳送的屬性

| 屬性名稱 | 說明                                                                                    |
|---------------|------------------------------------------------------------------------------------------------|
| Trace_message | 包含錯誤字串和可能發生失敗的原因之詳細資料 |
