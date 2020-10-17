---
title: Lync Server 2013：管理應用層級回應群組設定
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
ms.openlocfilehash: af64929beba67b29b4588bae12a5a45c9de64460
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498340"
---
# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="29e54-102">在 Lync Server 2013 中管理應用層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="29e54-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29e54-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="29e54-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="29e54-104">回應群組應用程式的應用層級設定包括預設的等候音樂設定、預設的等候音樂音訊檔、代理程式回電寬限時間，以及通話內容設定。</span><span class="sxs-lookup"><span data-stu-id="29e54-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="29e54-105">您只能為每個集區定義一組應用層級的設定。</span><span class="sxs-lookup"><span data-stu-id="29e54-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="29e54-106">若要查看應用層級設定，請使用 **Get-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29e54-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="29e54-107">若要修改應用層級設定，請使用 **Set-CsRgsConfiguration** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="29e54-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="29e54-108">只有在未定義自訂等候音樂的情況下，才會播放呼叫保留的預設音樂。</span><span class="sxs-lookup"><span data-stu-id="29e54-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="29e54-109">「呼叫內容」只適用于指派給互動式工作流程的佇列。</span><span class="sxs-lookup"><span data-stu-id="29e54-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="29e54-110">如果已啟用呼叫內容，代理程式會在接收來電時，看到如來電者等候時間或工作流程問題和答案等資訊。</span><span class="sxs-lookup"><span data-stu-id="29e54-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="29e54-111">修改回應群組的應用層級設定</span><span class="sxs-lookup"><span data-stu-id="29e54-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="29e54-112">以 RTCUniversalServerAdmins 群組成員的身分登入，或是以支援回應群組之其中一個預先定義的系統管理角色的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="29e54-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="29e54-113">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="29e54-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="29e54-114">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="29e54-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="29e54-115">例如：</span><span class="sxs-lookup"><span data-stu-id="29e54-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="29e54-116">若要指定用來做為預設等候音樂的音訊檔，您必須先匯入音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="29e54-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="29e54-117">例如：</span><span class="sxs-lookup"><span data-stu-id="29e54-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="29e54-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="29e54-118">See Also</span></span>


[<span data-ttu-id="29e54-119">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="29e54-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="29e54-120">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="29e54-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="29e54-121">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="29e54-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

