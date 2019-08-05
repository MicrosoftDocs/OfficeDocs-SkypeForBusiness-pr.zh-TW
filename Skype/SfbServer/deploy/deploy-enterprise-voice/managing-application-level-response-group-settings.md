---
title: 管理商務用 Skype 中的應用層級回應群組設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 在商務用 Skype Server Enterprise Voice 中管理應用程式層級回應群組設定, 例如 [音樂封存] 和 [ringback 設定]。
ms.openlocfilehash: 500ed8942fb859ce41340c94d0568e9e87b1c3d6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191128"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="0cb12-103">管理商務用 Skype 中的應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="0cb12-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="0cb12-104">在商務用 Skype Server Enterprise Voice 中管理應用程式層級回應群組設定, 例如 [音樂封存] 和 [ringback 設定]。</span><span class="sxs-lookup"><span data-stu-id="0cb12-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0cb12-105">回應群組應用程式的應用程式層級設定包括預設的 [以音樂為保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期], 以及 [通話內容] 設定。</span><span class="sxs-lookup"><span data-stu-id="0cb12-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="0cb12-106">每個 pool 只能定義一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="0cb12-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="0cb12-107">若要查看應用程式層級的設定, 請使用**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0cb12-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="0cb12-108">若要修改應用程式層級的設定, 請使用**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0cb12-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="0cb12-109">只有在已定義 [保留自訂的音樂] 時, 才會播放預設的 [等候音樂] 狀態。</span><span class="sxs-lookup"><span data-stu-id="0cb12-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="0cb12-110">只有在指派給互動式工作流程的佇列中, 才能使用呼叫內容。</span><span class="sxs-lookup"><span data-stu-id="0cb12-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="0cb12-111">如果已啟用呼叫內容, 則代理程式可以在收到來電時, 看到來電者等候時間或工作流程問題與解答等資訊。</span><span class="sxs-lookup"><span data-stu-id="0cb12-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="0cb12-112">修改回應群組的應用層級設定</span><span class="sxs-lookup"><span data-stu-id="0cb12-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="0cb12-113">以 RTCUniversalServerAdmins 群組成員的身分登入, 或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="0cb12-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="0cb12-114">啟動商務用 Skype Server 管理命令介面: 按一下 [**開始**], 按一下 [**所有程式**], 按一下 [**商務用 skype 2015**], 然後按一下 [**商務用 skype Server management Shell**]。</span><span class="sxs-lookup"><span data-stu-id="0cb12-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0cb12-115">在命令列上執行:</span><span class="sxs-lookup"><span data-stu-id="0cb12-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="0cb12-116">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb12-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="0cb12-117">若要將音訊檔案指定為保留預設的音樂, 您必須先匯入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="0cb12-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="0cb12-118">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb12-118">For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="0cb12-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="0cb12-119">See also</span></span>

[<span data-ttu-id="0cb12-120">CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cb12-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="0cb12-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="0cb12-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="0cb12-122">匯入-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="0cb12-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
