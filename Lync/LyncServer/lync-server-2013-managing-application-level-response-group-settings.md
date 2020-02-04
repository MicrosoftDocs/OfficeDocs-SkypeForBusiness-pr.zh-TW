---
title: Lync Server 2013：管理應用程式層級回應群組設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffce659c2c4dc6c91ba4e4935b72c15e4cef4da5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="630b3-102">管理 Lync Server 2013 中的應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="630b3-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="630b3-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="630b3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="630b3-104">回應群組應用程式的應用程式層級設定包括預設的 [以音樂為保留] 設定、預設的 [音樂保留] 音訊檔案、[代理程式 ringback 寬限期]，以及 [通話內容] 設定。</span><span class="sxs-lookup"><span data-stu-id="630b3-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="630b3-105">每個 pool 只能定義一組應用層級設定。</span><span class="sxs-lookup"><span data-stu-id="630b3-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="630b3-106">若要查看應用程式層級的設定，請使用**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="630b3-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="630b3-107">若要修改應用程式層級的設定，請使用**CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="630b3-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="630b3-108">只有在已定義 [保留自訂的音樂] 時，才會播放預設的 [等候音樂] 狀態。</span><span class="sxs-lookup"><span data-stu-id="630b3-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="630b3-109">只有在指派給互動式工作流程的佇列中，才能使用呼叫內容。</span><span class="sxs-lookup"><span data-stu-id="630b3-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="630b3-110">如果已啟用呼叫內容，則代理程式可以在收到來電時，看到來電者等候時間或工作流程問題與解答等資訊。</span><span class="sxs-lookup"><span data-stu-id="630b3-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="630b3-111">修改回應群組的應用層級設定</span><span class="sxs-lookup"><span data-stu-id="630b3-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="630b3-112">以 RTCUniversalServerAdmins 群組成員的身分登入，或以支援回應群組的預先定義之系統管理角色的成員的身分登入。</span><span class="sxs-lookup"><span data-stu-id="630b3-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="630b3-113">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="630b3-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="630b3-114">在命令列上執行：</span><span class="sxs-lookup"><span data-stu-id="630b3-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="630b3-115">例如：</span><span class="sxs-lookup"><span data-stu-id="630b3-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="630b3-116">若要將音訊檔案指定為保留預設的音樂，您必須先匯入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="630b3-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="630b3-117">例如：</span><span class="sxs-lookup"><span data-stu-id="630b3-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="630b3-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="630b3-118">See Also</span></span>


[<span data-ttu-id="630b3-119">CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="630b3-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="630b3-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="630b3-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="630b3-121">匯入-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="630b3-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

