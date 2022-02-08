---
title: Skype 會議室系統帳戶的會議原則
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 閱讀此主題以瞭解如何為 Skype 的會議室系統帳戶指派會議原則。
ms.openlocfilehash: 2bbe7f9ca07e8c17aaf0c03693fbeca7eede2457
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394395"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 會議室系統帳戶的會議原則
 
閱讀此主題以瞭解如何為 Skype 的會議室系統帳戶指派會議原則。
  
## <a name="conferencing-policy-features"></a>會議原則功能

指派給 Skype 房間系統帳戶的會議原則必須具有某些特性。 在大部分情況下，Skype 的會議室系統用戶端加入排程的會議，因此會議召集人的會議原則會影響會議。 不過，在商務用 Skype Server 中，某些功能取決於參與者的設定。 例如，如果參與者的原則允許最大的影片解析度為1080p，即使召集人的原則不允許，參與者還是會在會議中體驗這項較高解析度的視頻功能。 下表說明為組織中 Skype 會議室系統帳戶設定會議原則時，應注意的一些設定。 
  
|功能  <br/> |值  <br/> |註解  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |Skype 房間系統音訊必須為 true  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |若要在 [立即開會] 中運作的 Skype 會議室系統音訊 () Skype 會議室系統中的特定白板會話，則必須是 true。  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |可讓 Skype 房間系統呈現多個視圖、多個影片資料流程  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|DisablePowerPointAnnotations  <br/> |假  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |假  <br/> |取決於帳戶是否企業語音 (EV) 啟用 (請參閱啟用 Skype 的會議室系統帳戶商務用 Skype 區段)   <br/> |
|AllowAnonymousUsersToDialOut  <br/> |假  <br/> |取決於帳戶是否企業語音 (EV) 啟用  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowExternalUserControl  <br/> |假  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |假  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |在 [立即開會] 中 N/A (點對點) 會議，但是 Skype 的會議室系統可以在會議室的正面回應投票。  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |在 [立即開會] 中 N/A (點對點) 會議，但是 Skype 的會議室系統可以在會議室的正面回應投票。  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|EnableAppDesktopSharing  <br/> |電腦  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AllowConferenceRecording  <br/> |假  <br/> |Skype 會議室系統的 N/A。 如果為 TRUE，遠端一方可以記錄  <br/> |
|EnableP2PRecording  <br/> |假  <br/> |Skype 會議室系統的 N/A。 如果為 TRUE，遠端一方可以記錄  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不適用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不適用  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |讓 Skype 的會議室系統用戶端參與對等的視頻會話  <br/> |
|AllowLargeMeetings  <br/> |假  <br/> |不適用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|MaxVideoConferenceResolution  <br/> |VGA  <br/> |商務用 Skype Server 忽略，Skype 會議室系統會使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影響 Skype 會議室系統中的 [立即開會] (特定) 白板會話  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |請參閱表格結尾的記事\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |這是允許的輸出影片位元速率上限。 Skype 會議室系統可以傳送 1 1080 資料流程與 pano (如果 RoundTable) 以此位元速率使用。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |請參閱表格結尾的記事\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不適用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |建議您盡可能將此設定設為最高。 有效的頻寬取決於會議時間的網路狀況。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |Skype 房間系統必須為 TRUE，以確保多 view 影片資料流程  <br/> |
   
* 如需有關頻寬規劃的詳細資訊，請參閱 [媒體流量的網路頻寬需求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 的會議室系統用戶端嘗試加入以 Lync Server 2010 集區為宿主的使用者組織的排程會議，則會議召集人的會議原則可以防止 Skype 會議室系統用戶端執行共同作業。 
  
## <a name="meeting-authentication"></a>會議驗證

當使用者使用會議加入連結加入限制的會議時，Skype 會議室系統會提示使用者進行驗證; 例如，已在 Outlook 中設定會議會議廳選項的會議。 在自訂的會議上，此設定永遠為開啟，且一定會提示使用者。 不過，如果是不受限制的會議，使用者可以加入會議，但不進行驗證。 
  
下列命令可讓系統管理員要求所有會議（包括不受限制的會議）進行驗證： 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

根據預設，RequireRoomSystemsAuthorization 為 FALSE。 
  

