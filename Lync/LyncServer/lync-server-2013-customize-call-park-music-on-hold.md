---
title: Lync Server 2013：在保留時自訂通話寄存音樂
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Customize Call Park music on hold
ms:assetid: 3d78e6f9-a4ae-49f4-a89f-4515acb49dac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688031(v=OCS.15)
ms:contentKeyID: 49733621
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62983c10033ddc350b39a123c62fa31c132bb9c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="customize-call-park-music-on-hold-in-lync-server-2013"></a><span data-ttu-id="46acb-102">在 Lync Server 2013 中自訂通話寄存音樂暫停</span><span class="sxs-lookup"><span data-stu-id="46acb-102">Customize Call Park music on hold in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46acb-103">_**主題上次修改日期：** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="46acb-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="46acb-104">您可以指定自己的音樂檔案，以供等候音樂使用，而不是 Lync Server 2013 隨附的預設音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="46acb-104">You can specify your own music file to use for music on hold, instead of the default music file that ships with Lync Server 2013.</span></span> <span data-ttu-id="46acb-105">若要在保留時自訂音樂，請使用**CsCallParkServiceMusicOnHoldFile** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="46acb-105">To customize music on hold, use the **Set-CsCallParkServiceMusicOnHoldFile** cmdlet.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46acb-106">如果您自訂 [等候音樂] 並想要在多個網站上擁有相同的音樂，您必須針對每個執行通話駐留應用程式的網站設定音樂檔案。</span><span class="sxs-lookup"><span data-stu-id="46acb-106">If you customize music on hold and want the same music for multiple sites, you must configure the music file for each site that runs the Call Park application.</span></span>



</div>

<div>

## <a name="to-customize-the-music-file"></a><span data-ttu-id="46acb-107">自訂音樂檔案</span><span class="sxs-lookup"><span data-stu-id="46acb-107">To customize the music file</span></span>

1.  <span data-ttu-id="46acb-108">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="46acb-108">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="46acb-109">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="46acb-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="46acb-110">用盡</span><span class="sxs-lookup"><span data-stu-id="46acb-110">Run:</span></span>
    
        Set-CsCallParkServiceMusicOnHoldFile -Service <ServiceID where the Call Park application resides> -Content <Byte[]>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="46acb-111">使用<STRONG>CsService</STRONG> Cmdlet 來識別服務。</span><span class="sxs-lookup"><span data-stu-id="46acb-111">Use the <STRONG>Get-CsService</STRONG> cmdlet to identify the service.</span></span> <span data-ttu-id="46acb-112">如需詳細資訊，請參閱<A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">CsService</A>。</span><span class="sxs-lookup"><span data-stu-id="46acb-112">For details, see <A href="https://docs.microsoft.com/powershell/module/skype/Get-CsService">Get-CsService</A>.</span></span>

    
    </div>
    
    <span data-ttu-id="46acb-113">下列範例顯示如何取得檔案的內容（soothingmusic）作為位元組陣列，並將它指派給變數。</span><span class="sxs-lookup"><span data-stu-id="46acb-113">The following example shows how to obtain the contents of a file, soothingmusic.wma, as a byte array and assign it to a variable.</span></span> <span data-ttu-id="46acb-114">然後，音訊檔案會指派為 [通話駐留] 的 [音樂保留] 檔案。</span><span class="sxs-lookup"><span data-stu-id="46acb-114">Then the audio file is assigned as the music-on-hold file for Call Park.</span></span> <span data-ttu-id="46acb-115">如需詳細資訊，請參閱[設定 CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)。</span><span class="sxs-lookup"><span data-stu-id="46acb-115">For details, see [Set-CsCallParkServiceMusicOnHoldFile](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile).</span></span>
    
        $a = Get-Content -ReadCount 0 -Encoding byte "C:\MoHFiles\soothingmusic.wma"
        Set-CsCallParkServiceMusicOnHoldFile -Service Redmond1-applicationserver-1 -Content $a

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="46acb-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="46acb-116">See Also</span></span>


[<span data-ttu-id="46acb-117">Set-CsCallParkServiceMusicOnHoldFile</span><span class="sxs-lookup"><span data-stu-id="46acb-117">Set-CsCallParkServiceMusicOnHoldFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkServiceMusicOnHoldFile)  
[<span data-ttu-id="46acb-118">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="46acb-118">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

