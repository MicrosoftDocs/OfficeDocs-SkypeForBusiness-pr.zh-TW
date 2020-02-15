---
title: Lync Server 2013： 管理應用程式層級回應群組設定
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
ms.openlocfilehash: a1dccc404350e10b61ea0917c0bd6b6d7e44b333
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="4fe4f-102">管理 Lync Server 2013 中的應用程式層級回應群組設定</span><span class="sxs-lookup"><span data-stu-id="4fe4f-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4fe4f-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="4fe4f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4fe4f-104">回應群組應用程式的應用程式層級設定包含預設的等候音樂上保留設定、 預設的等候音樂上保留音訊檔案、 代理人回電寬限期，以及來電內容設定。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="4fe4f-105">您可以定義只有一組每個集區的應用程式層級設定。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="4fe4f-106">若要檢視應用程式層級設定，請使用**Get-csrgsconfiguration**指令程式。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="4fe4f-107">若要修改的應用程式層級設定，請使用**Set-csrgsconfiguration** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="4fe4f-108">當通話處於保留狀態，只有當不定義任何自訂等候音樂，就會播放預設等候音樂。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-108">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined.</span></span> <span data-ttu-id="4fe4f-109">呼叫內容是僅供指派給互動式工作流程的佇列。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-109">Call context is available only for queues assigned to interactive workflows.</span></span> <span data-ttu-id="4fe4f-110">如果啟用來電內容時，代理程式可以看到資訊，例如來電者時收到通話時的等待時間或工作流程的問題和解答。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-110">If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="4fe4f-111">若要修改回應群組應用程式層級設定</span><span class="sxs-lookup"><span data-stu-id="4fe4f-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="4fe4f-112">以 RTCUniversalServerAdmins 群組成員身分或其中一個預先定義的系統管理角色支援回應群組的成員身分登入。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="4fe4f-113">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="4fe4f-114">在命令列中執行：</span><span class="sxs-lookup"><span data-stu-id="4fe4f-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="4fe4f-115">例如：</span><span class="sxs-lookup"><span data-stu-id="4fe4f-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="4fe4f-116">若要指定要當成預設等候音樂音訊檔，您必須先匯入的音訊檔案。</span><span class="sxs-lookup"><span data-stu-id="4fe4f-116">To specify an audio file to use as the default music on hold, you need to import the audio file first.</span></span> <span data-ttu-id="4fe4f-117">例如：</span><span class="sxs-lookup"><span data-stu-id="4fe4f-117">For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4fe4f-118">請參閱</span><span class="sxs-lookup"><span data-stu-id="4fe4f-118">See Also</span></span>


[<span data-ttu-id="4fe4f-119">Get-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="4fe4f-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="4fe4f-120">Set-csrgsconfiguration</span><span class="sxs-lookup"><span data-stu-id="4fe4f-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="4fe4f-121">Import-csrgsaudiofile</span><span class="sxs-lookup"><span data-stu-id="4fe4f-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

