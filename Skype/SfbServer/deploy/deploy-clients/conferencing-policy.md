---
title: Skype 會議室系統帳戶的會議原則
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 若要瞭解如何指派 Skype 會議室系統帳戶的會議原則，請閱讀本主題。
ms.openlocfilehash: 20115ee2ab361a0bc15bf2053feb3f70bbe6f7ef
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775366"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 會議室系統帳戶的會議原則
 
若要瞭解如何指派 Skype 會議室系統帳戶的會議原則，請閱讀本主題。
  
## <a name="conferencing-policy-features"></a>會議原則功能

指派給 Skype 房間系統帳戶的會議原則必須具有特定的特性。 在大多數情況下，Skype 會議室系統用戶端會加入排程會議，因此會議召集人的會議原則會影響會議。 不過，在商務用 Skype Server 中，某些功能會視參與者的設定而定。 例如，如果參與者的原則允許最大的視頻解析度為1080p，即使召集人原則不允許，參與者也會在會議中體驗到這個較高解析度的視頻功能。 下表說明您在組織中設定 Skype 會議室系統帳戶的會議原則時，應注意的幾個設定。 
  
|功能  <br/> |值  <br/> |評論  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |滿足  <br/> |Skype 會議室系統音訊必須是 true  <br/> |
|AllowIPVideo  <br/> |滿足  <br/> |必須為 true，才能在 Skype 會議室系統中的 [立即開會] （ad hoc）白板會話中運作  <br/> |
|AllowMultiView  <br/> |滿足  <br/> |允許 Skype 會議室系統轉譯多個視圖、多個視頻資料流程  <br/> |
|AllowParticipantControl  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowAnnotations  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|DisablePowerPointAnnotations  <br/> |虛假  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |虛假  <br/> |取決於帳戶是否已啟用企業語音（EV）（請參閱在商務用 Skype 中啟用 Skype 會議室系統帳戶）  <br/> |
|AllowAnonymousUsersToDialOut  <br/> |虛假  <br/> |取決於帳戶是否已啟用企業語音（EV）  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowExternalUsersToSaveContent  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowExternalUserControl  <br/> |虛假  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |虛假  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowPolls  <br/> |滿足  <br/> |[立即開會] （臨時）會議中的 N/A，但 Skype 會議室系統可以在會議室前的畫面上回應投票  <br/> |
|AllowSharedNotes  <br/> |滿足  <br/> |[立即開會] （臨時）會議中的 N/A，但 Skype 會議室系統可以在會議室前的畫面上回應投票  <br/> |
|EnableDialInConferencing  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|EnableAppDesktopSharing  <br/> |桌面  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AllowConferenceRecording  <br/> |虛假  <br/> |適用于 Skype 室系統的 N/A。 如果為 TRUE，則遠端方可以記錄  <br/> |
|EnableP2PRecording  <br/> |虛假  <br/> |適用于 Skype 室系統的 N/A。 如果為 TRUE，則遠端方可以記錄  <br/> |
|EnableFileTransfer  <br/> |滿足  <br/> |N/A  <br/> |
|EnableP2PFileTransfer  <br/> |滿足  <br/> |N/A  <br/> |
|EnableP2PVideo  <br/> |滿足  <br/> |讓 Skype 會議室系統用戶端參與對等的視頻會話  <br/> |
|AllowLargeMeetings  <br/> |虛假  <br/> |N/A  <br/> |
|EnableDataCollaboration  <br/> |滿足  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|MaxVideoConferenceResolution  <br/> |採用  <br/> |已被商務用 Skype Server 忽略，Skype 室系統會使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影響 Skype 會議室系統中的 [立即開會] （ad hoc）白板會議  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |請參閱表格結尾的記事\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |這是所允許的最大輸出視頻位元速率。 Skype 會議室系統可以傳送 1 1080 串流以及 pano （如果使用的是圓桌會議），以此位元速率傳送。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |請參閱表格結尾的記事\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |N/A  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |我們建議您盡可能將此設定為最高。 有效的頻寬取決於會議時的網路狀況。\*  <br/> |
|EnableMultiViewJoin  <br/> |滿足  <br/> |必須是適用于 Skype 會議室系統的 TRUE，才能確保多個視圖的影片串流  <br/> |
   
* 如需有關頻寬規劃的詳細資訊，請參閱[媒體流量的網路頻寬需求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 會議室系統用戶端嘗試加入由駐留在 Lync Server 2010 文件庫的使用者所組織的排程會議，會議召集人的會議原則可以防止 Skype 會議室系統用戶端執行共同作業。 
  
## <a name="meeting-authentication"></a>會議驗證

當 Skype 會議室系統使用會議加入連結加入受限制的會議時，系統會提示使用者進行驗證;例如，已在 Outlook 中設定 [會議廳] 選項的會議。 針對自訂的會議，此設定總是開啟，且系統總是提示使用者。 不過，對於不受限制的會議，使用者可以加入沒有驗證的會議。 
  
下列命令可讓系統管理員對所有會議都要求驗證，包括不受限制的會議： 
  
```
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

根據預設，RequireRoomSystemsAuthorization 是 FALSE。 
  

