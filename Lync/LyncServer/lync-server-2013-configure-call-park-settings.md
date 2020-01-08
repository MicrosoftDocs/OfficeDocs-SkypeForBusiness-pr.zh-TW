---
title: Lync Server 2013：設定通話駐留設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9acbd44acf2ca78042452d2c1f52d4c5fa26056f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="5ac4e-102">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="5ac4e-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac4e-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="5ac4e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="5ac4e-104">如果您不想使用預設的通話駐留設定，您可以進行自訂。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="5ac4e-105">當您安裝 [通話駐留] 應用程式時，系統會根據預設設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="5ac4e-106">您可以修改全域設定，也可以指定網站專用的設定。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="5ac4e-107">使用**新的 CsCpsConfiguration** Cmdlet 來建立新的網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="5ac4e-108">使用**CsCpsConfiguration** Cmdlet 來修改現有的設定。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5ac4e-109">我們建議您針對備用目的地設定<STRONG>OnTimeoutURI</STRONG>選項，以便在停用通話超時和 ringback 失敗時使用。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="5ac4e-110">使用**新的 CsCpsConfiguration** Cmdlet 或**CsCpsConfiguration** Cmdlet 來設定下列任何設定：</span><span class="sxs-lookup"><span data-stu-id="5ac4e-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac4e-111">此選項：</span><span class="sxs-lookup"><span data-stu-id="5ac4e-111">This option:</span></span></th>
<th><span data-ttu-id="5ac4e-112">指定：</span><span class="sxs-lookup"><span data-stu-id="5ac4e-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac4e-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="5ac4e-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="5ac4e-114">通話結束之後，在撥打電話給接聽電話的電話之前所經過的時間長度。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="5ac4e-115">此值必須以 hh： mm： ss 格式輸入，以指定小時、分鐘和秒。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-115">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds.</span></span> <span data-ttu-id="5ac4e-116">最小值為10秒，最大值為10分鐘。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-116">The minimum value is 10 seconds, and the maximum value is 10 minutes.</span></span> <span data-ttu-id="5ac4e-117">預設值為00:01:30。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-117">The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac4e-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="5ac4e-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="5ac4e-119">通話停用時，是否會在來電者中播放音樂。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="5ac4e-120">值為 True 或 False。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-120">Values are True or False.</span></span> <span data-ttu-id="5ac4e-121">預設值為 True。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-121">The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac4e-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="5ac4e-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="5ac4e-123">寄存來電在轉寄到指定給<strong>OnTimeoutURI</strong>的回退統一資源識別項（URI）之前，響鈴給應答電話的次數。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-123">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>.</span></span> <span data-ttu-id="5ac4e-124">預設值為1。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-124">The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac4e-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="5ac4e-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="5ac4e-126">在超過<strong>MaxCallPickupAttempts</strong>時傳送未應答之暫停呼叫的使用者或回應群組的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="5ac4e-127">Value 必須是以 [字串 SIP：] 開頭的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-127">Value must be a SIP URI beginning with the string sip:.</span></span> <span data-ttu-id="5ac4e-128">例如，sip:bob@contoso.com。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-128">For example, sip:bob@contoso.com.</span></span> <span data-ttu-id="5ac4e-129">預設值為 [沒有轉寄位址]。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-129">The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="5ac4e-130">若要設定通話寄存設定</span><span class="sxs-lookup"><span data-stu-id="5ac4e-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="5ac4e-131">登入 Lync Server 管理命令介面安裝為 RTCUniversalServerAdmins 群組的成員的電腦，或使用[Lync server 2013 中委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述的必要使用者許可權。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="5ac4e-132">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="5ac4e-133">用盡</span><span class="sxs-lookup"><span data-stu-id="5ac4e-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="5ac4e-134">使用<STRONG>CsSite</STRONG> Cmdlet 來識別網站。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="5ac4e-135">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="5ac4e-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="5ac4e-136">例如：</span><span class="sxs-lookup"><span data-stu-id="5ac4e-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5ac4e-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="5ac4e-137">See Also</span></span>


[<span data-ttu-id="5ac4e-138">在 Lync Server 2013 中自訂通話寄存音樂暫停</span><span class="sxs-lookup"><span data-stu-id="5ac4e-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="5ac4e-139">新-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ac4e-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="5ac4e-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="5ac4e-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="5ac4e-141">CsSite</span><span class="sxs-lookup"><span data-stu-id="5ac4e-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

