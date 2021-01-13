---
title: Skype 室系統帳戶的會議原則
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4dd8be28-5156-411b-8ccd-eff7f75cb897
description: 閱讀此主題以瞭解如何為 Skype 室系統帳戶指派會議原則。
ms.openlocfilehash: 3fb462168bd4121f5feef365f881ed9f02620e25
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812723"
---
# <a name="conferencing-policy-for-skype-room-system-accounts"></a>Skype 室系統帳戶的會議原則
 
閱讀此主題以瞭解如何為 Skype 室系統帳戶指派會議原則。
  
## <a name="conferencing-policy-features"></a>會議原則功能

指派給 Skype 室系統帳戶的會議原則必須具有某些特性。 在大多數情況下，Skype 會議室系統用戶端會加入排程會議，因此會議召集人的會議原則會影響會議。 不過，在商務用 Skype Server 中，某些功能取決於參與者的設定。 例如，如果參與者的原則允許最大的影片解析度為1080p，即使召集人的原則不允許，參與者還是會在會議中體驗這項較高解析度的視頻功能。 下表說明在組織中為 Skype 會議室系統帳戶設定會議原則時，應注意的一些設定。 
  
|功能  <br/> |值  <br/> |留言  <br/> |
|:-----|:-----|:-----|
|AllowIPAudio  <br/> |TRUE  <br/> |對於 Skype 會議室系統音訊，必須為 true  <br/> |
|AllowIPVideo  <br/> |TRUE  <br/> |若要在 [立即開會] 中運作 (點對點) 白板會話，請設為 true。  <br/> |
|AllowMultiView  <br/> |TRUE  <br/> |允許 Skype 會議室系統呈現多重查看、多個影片資料流程  <br/> |
|AllowParticipantControl  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowAnnotations  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|DisablePowerPointAnnotations  <br/> |假  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowUserToScheduleMeetingsWithAppSharing  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowNonEnterpriseVoiceUsersToDialOut  <br/> |假  <br/> |取決於帳戶是否為 Enterprise Voice (EV) 啟用 (請參閱啟用商務用 Skype 的商務用 Skype 室系統帳戶」區段)   <br/> |
|AllowAnonymousUsersToDialOut  <br/> |假  <br/> |取決於帳戶是否為 Enterprise Voice (EV) enabled  <br/> |
|AllowAnonymousParticipantsInMeetings  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowExternalUsersToSaveContent  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowExternalUserControl  <br/> |假  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowExternalUsersToRecordMeeting  <br/> |假  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowPolls  <br/> |TRUE  <br/> |在 [立即開會] 中 N/A (點對點) 會議，但 Skype 會議室系統可以在會議室的正面回應投票  <br/> |
|AllowSharedNotes  <br/> |TRUE  <br/> |在 [立即開會] 中 N/A (點對點) 會議，但 Skype 會議室系統可以在會議室的正面回應投票  <br/> |
|EnableDialInConferencing  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|EnableAppDesktopSharing  <br/> |桌上型電腦  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AllowConferenceRecording  <br/> |假  <br/> |適用于 Skype 會議室系統的 N/A。 如果為 TRUE，遠端一方可以記錄  <br/> |
|EnableP2PRecording  <br/> |假  <br/> |適用于 Skype 會議室系統的 N/A。 如果為 TRUE，遠端一方可以記錄  <br/> |
|EnableFileTransfer  <br/> |TRUE  <br/> |不適用  <br/> |
|EnableP2PFileTransfer  <br/> |TRUE  <br/> |不適用  <br/> |
|EnableP2PVideo  <br/> |TRUE  <br/> |可讓 Skype 聊天室系統用戶端參與對等的視頻會話  <br/> |
|AllowLargeMeetings  <br/> |假  <br/> |不適用  <br/> |
|EnableDataCollaboration  <br/> |TRUE  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|MaxVideoConferenceResolution  <br/> |Vga  <br/> |由商務用 Skype Server 忽略，Skype 會議室系統會使用 HD1080  <br/> |
|MaxMeetingSize  <br/> |250  <br/> |影響 (Skype 會議室系統中的「立即開會」) 白板會話  <br/> |
|AudioBitRateKb  <br/> |200  <br/> |請參閱表格結尾的記事\*  <br/> |
|VideoBitRateKb  <br/> |5000  <br/> |這是允許的輸出影片位元速率上限。 如果) 以此位元速率使用 RoundTable，Skype 會議室系統可以隨 pano (傳送 1 1080 資料流程。 \*  <br/> |
|AppSharingBitRateKb  <br/> |5000  <br/> |請參閱表格結尾的記事\*  <br/> |
|FileTransferBitRateKb  <br/> |5000  <br/> |不適用  <br/> |
|TotalReceiveVideoBitRateKb  <br/> |20000  <br/> |建議您盡可能將此設定設為最高。 有效的頻寬取決於會議時間的網路狀況。\*  <br/> |
|EnableMultiViewJoin  <br/> |TRUE  <br/> |適用于 Skype 會議室系統必須是 TRUE，以確保多 view 影片資料流程  <br/> |
   
* 如需有關頻寬規劃的詳細資訊，請參閱 [媒體流量的網路頻寬需求](../../plan-your-deployment/network-requirements/network-requirements.md#network-bandwidth-requirements-for-media-traffic)。
  
> [!NOTE]
> 如果 Skype 會議室系統用戶端嘗試加入以 Lync Server 2010 集區為宿主的使用者組織的排程會議，則會議召集人的會議原則可能會使 Skype 會議室系統用戶端無法執行共同作業。 
  
## <a name="meeting-authentication"></a>會議驗證

當使用者使用會議加入連結加入限制的會議時，Skype 會議室系統會提示使用者進行驗證。例如，在 Outlook 中已設定會議會議廳選項的會議。 在自訂的會議上，此設定永遠為開啟，且一定會提示使用者。 不過，如果是不受限制的會議，使用者可以加入會議，但不進行驗證。 
  
下列命令可讓系統管理員要求所有會議（包括不受限制的會議）進行驗證： 
  
```powershell
Set-CsMeetingConfiguration -RequireRoomSystemsAuthorization $TRUE
```

根據預設，RequireRoomSystemsAuthorization 為 FALSE。 
  

