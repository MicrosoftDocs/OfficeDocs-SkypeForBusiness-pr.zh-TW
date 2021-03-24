---
title: 在商務用 Skype 中管理應用層級回應群組設定
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: 在商務用 Skype Server Enterprise Voice 中管理應用層級回應群組設定，例如「暫停音樂」和「回電設定」。
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103469"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="ff594-103">在商務用 Skype 中管理應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="ff594-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="ff594-104">在商務用 Skype Server Enterprise Voice 中管理應用層級回應群組設定，例如「暫停音樂」和「回電設定」。</span><span class="sxs-lookup"><span data-stu-id="ff594-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="ff594-105">回應群組應用程式的應用層級設定包括預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及通話內容設定。</span><span class="sxs-lookup"><span data-stu-id="ff594-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="ff594-106">您只能為每個集區定義一組應用層級的設定。</span><span class="sxs-lookup"><span data-stu-id="ff594-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="ff594-107">若要查看應用層級設定，請使用 **Get-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff594-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="ff594-108">若要修改應用層級設定，請使用 **Set-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ff594-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="ff594-109">只有在未定義自訂等候音樂的情況下，才會播放呼叫保留的預設音樂。</span><span class="sxs-lookup"><span data-stu-id="ff594-109">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="ff594-110">「呼叫內容」只適用于指派給互動式工作流程的佇列。</span><span class="sxs-lookup"><span data-stu-id="ff594-110">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="ff594-111">如果已啟用呼叫內容，代理程式會在接收來電時，看到如來電者等候時間或工作流程問題和答案等資訊。</span><span class="sxs-lookup"><span data-stu-id="ff594-111">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="ff594-112">修改回應群組的應用層級設定</span><span class="sxs-lookup"><span data-stu-id="ff594-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="ff594-113">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="ff594-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="ff594-114">啟動商務用 Skype Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **商務用 skype 2015**]，然後按一下 [ **商務用 skype 伺服器管理命令** 介面]。</span><span class="sxs-lookup"><span data-stu-id="ff594-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ff594-115">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="ff594-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="ff594-116">例如：</span><span class="sxs-lookup"><span data-stu-id="ff594-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="ff594-117">若要指定用來做為預設等候音樂的音訊檔，您必須先匯入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="ff594-117">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="ff594-118">例如：</span><span class="sxs-lookup"><span data-stu-id="ff594-118">For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="ff594-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ff594-119">See also</span></span>

[<span data-ttu-id="ff594-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff594-120">Get-CsRgsConfiguration</span></span>](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="ff594-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff594-121">Set-CsRgsConfiguration</span></span>](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="ff594-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="ff594-122">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)