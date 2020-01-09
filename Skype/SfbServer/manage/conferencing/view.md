---
title: 在商務用 Skype Server 中查看會議原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1c0976e-2bfb-475b-9255-ed6b093d8798
description: 摘要：瞭解如何在商務用 Skype Server 中查看會議原則。
ms.openlocfilehash: 7ea7b5cb9ba54fcf26e5f37b79320466c19d1050
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992188"
---
# <a name="view-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="bace0-103">在商務用 Skype Server 中查看會議原則</span><span class="sxs-lookup"><span data-stu-id="bace0-103">View conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="bace0-104">**摘要：** 瞭解如何在商務用 Skype Server 中查看會議原則。</span><span class="sxs-lookup"><span data-stu-id="bace0-104">**Summary:** Learn how to view conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="bace0-105">您可以使用商務用 Skype Server 的 [控制台] 或使用商務用 Skype Server Management Shell 來查看會議原則。</span><span class="sxs-lookup"><span data-stu-id="bace0-105">You can view conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="view-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="bace0-106">使用商務用 Skype Server 的 [控制台] 來查看會議原則</span><span class="sxs-lookup"><span data-stu-id="bace0-106">View conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="bace0-107">從指派給 CsUserAdministrator 角色或 CsAdministrator 角色的使用者帳戶登入內部部署中的任何電腦。</span><span class="sxs-lookup"><span data-stu-id="bace0-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="bace0-108">開啟商務用 Skype Server 的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="bace0-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="bace0-109">在左側導覽列中，按一下 [**會議**]，然後按一下 [**會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="bace0-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="bace0-110">在 [**會議原則**] 頁面上，按兩下您要查看的會議原則。</span><span class="sxs-lookup"><span data-stu-id="bace0-110">On the **Conferencing Policy** page, double-click the conferencing policy that you would like to view.</span></span>
    
5. <span data-ttu-id="bace0-111">在 [**編輯檔案篩選器**] 中，選取 [**顯示詳細資料**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bace0-111">In **Edit File Filter**, select the **Show Details** check box.</span></span>
    
    <span data-ttu-id="bace0-112">[**編輯會議原則\<]\> -** 已開啟顯示所選原則設定的原則。</span><span class="sxs-lookup"><span data-stu-id="bace0-112">**Edit Conferencing Policy - \<policy\>** opens displaying the settings for the selected policy.</span></span>
    
    <span data-ttu-id="bace0-113">如需設定設定的詳細資訊，請參閱[在商務用 Skype 伺服器中建立會議原則](create-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="bace0-113">For details about configuring the settings, see [Create conferencing policies in Skype for Business Server](create-policies.md).</span></span>
    
## <a name="view-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="bace0-114">使用商務用 Skype Server Management Shell 來查看會議原則</span><span class="sxs-lookup"><span data-stu-id="bace0-114">View conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="bace0-115">若要查看會議原則，請使用**CsConferencingPolicy** Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="bace0-115">To view conferencing policies, use the **Get-CsConferencingPolicy** cmdlet:</span></span>
  
```PowerShell
Get-CsConferencingPolicy
```

<span data-ttu-id="bace0-116">這個 Cmdlet 會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="bace0-116">The cmdlet returns information such as the following:</span></span>
  
<pre>
Identity                                  : Global
AllowIPAudio                              : True
AllowIPVideo                              : True
AllowMultiView                            : True
Description                               :
AllowParticipantControl                   : True
AllowAnnotations                          : True
DisablePowerPointAnnotations              : False
AllowUserToScheduleMeetingsWithAppSharing : True
AllowNonEnterpriseVoiceUsersToDialOut     : False
AllowAnonymousUsersToDialOut              : False
AllowAnonymousParticipantsInMeetings      : True
AllowExternalUsersToSaveContent           : True
AllowExternalUserControl                  : False
AllowExternalUsersToRecordMeeting         : False
AllowPolls                                : True
AllowSharedNotes                          : True
EnableDialInConferencing                  : True
EnableAppDesktopSharing                   : Desktop
AllowConferenceRecording                  : False
EnableP2PRecording                        : False
EnableFileTransfer                        : True
EnableP2PFileTransfer                     : True
EnableP2PVideo                            : True
AllowLargeMeetings                        : False
EnableDataCollaboration                   : True
MaxVideoConferenceResolution              : VGA
MaxMeetingSize                            : 250
AudioBitRateKb                            : 200
VideoBitRateKb                            : 50000
AppSharingBitRateKb                       : 50000
FileTransferBitRateKb                     : 50000
TotalReceiveVideoBitRateKb                : 6000
EnableMultiViewJoin                       : True
</pre>

<span data-ttu-id="bace0-117">如需詳細資訊（包括完整的語法描述及參數清單），請參閱[CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="bace0-117">For more information, including a complete syntax description and list of parameters, see [Get-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps).</span></span>
  

