---
title: Lync Server 2013：設定通話駐留設定
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Call Park settings
ms:assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425886(v=OCS.15)
ms:contentKeyID: 48183922
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b99bc06f22490013dd14dc8527bd3eb88938380
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-park-settings-in-lync-server-2013"></a><span data-ttu-id="ff058-102">在 Lync Server 2013 中設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="ff058-102">Configure Call Park settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff058-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="ff058-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="ff058-104">如果您不想要使用預設的通話駐留設定，可以進行自訂。</span><span class="sxs-lookup"><span data-stu-id="ff058-104">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="ff058-105">當您安裝通話駐留應用程式時，系統會預設設定全域設定。</span><span class="sxs-lookup"><span data-stu-id="ff058-105">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="ff058-106">您可以修改全域設定，也可以指定網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="ff058-106">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="ff058-107">使用 **New-CsCpsConfiguration** Cmdlet 可建立新的網站特定設定。</span><span class="sxs-lookup"><span data-stu-id="ff058-107">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="ff058-108">使用 **Set-CsCpsConfiguration** Cmdlet 可修改現有設定。</span><span class="sxs-lookup"><span data-stu-id="ff058-108">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ff058-109">建議您至少設定 <STRONG>OnTimeoutURI</STRONG> 選項，作為當駐留通話逾時且回撥失敗時的後援目的地。</span><span class="sxs-lookup"><span data-stu-id="ff058-109">At a minimum, we recommend that you configure the <STRONG>OnTimeoutURI</STRONG> option for the fallback destination to use when a parked call times out and ringback fails.</span></span>



</div>

<span data-ttu-id="ff058-110">使用 **New-CsCpsConfiguration** Cmdlet 或 **Set-CsCpsConfiguration** Cmdlet 進行下列任何一項設定：</span><span class="sxs-lookup"><span data-stu-id="ff058-110">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff058-111">此選項：</span><span class="sxs-lookup"><span data-stu-id="ff058-111">This option:</span></span></th>
<th><span data-ttu-id="ff058-112">指定：</span><span class="sxs-lookup"><span data-stu-id="ff058-112">Specifies this:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff058-113"><strong>CallPickupTimeoutThreshold</strong></span><span class="sxs-lookup"><span data-stu-id="ff058-113"><strong>CallPickupTimeoutThreshold</strong></span></span></p></td>
<td><p><span data-ttu-id="ff058-114">從駐留通話之後到回撥原先接聽該通話的電話之前，需經過的時間長度。</span><span class="sxs-lookup"><span data-stu-id="ff058-114">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p>
<p><span data-ttu-id="ff058-p102">此值必須以 hh:mm:ss 格式輸入，以指定小時、分鐘和秒數。最小值為 10 秒，最大值為 10 分鐘。預設值為 00:01:30。</span><span class="sxs-lookup"><span data-stu-id="ff058-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff058-118"><strong>EnableMusicOnHold</strong></span><span class="sxs-lookup"><span data-stu-id="ff058-118"><strong>EnableMusicOnHold</strong></span></span></p></td>
<td><p><span data-ttu-id="ff058-119">駐留通話時是否對來電者播放音樂。</span><span class="sxs-lookup"><span data-stu-id="ff058-119">Whether music plays for a caller while a call is parked.</span></span></p>
<p><span data-ttu-id="ff058-p103">值為 True 或 False。預設為 True。</span><span class="sxs-lookup"><span data-stu-id="ff058-p103">Values are True or False. The default is True.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff058-122"><strong>MaxCallPickupAttempts</strong></span><span class="sxs-lookup"><span data-stu-id="ff058-122"><strong>MaxCallPickupAttempts</strong></span></span></p></td>
<td><p><span data-ttu-id="ff058-p104">在將駐留通話轉接至 <strong>OnTimeoutURI</strong> 指定的後援統一資源識別元 (URI) 之前，需將駐留通話回撥至當初接聽該通話的次數。預設值為 1。</span><span class="sxs-lookup"><span data-stu-id="ff058-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for <strong>OnTimeoutURI</strong>. The default is 1.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff058-125"><strong>OnTimeoutURI</strong></span><span class="sxs-lookup"><span data-stu-id="ff058-125"><strong>OnTimeoutURI</strong></span></span></p></td>
<td><p><span data-ttu-id="ff058-126">在超過 <strong>MaxCallPickupAttempts</strong> 時，將未接聽的駐留通話路由至的使用者或回應群組的 SIP 位址。</span><span class="sxs-lookup"><span data-stu-id="ff058-126">The SIP address of the user or response group to which an unanswered parked call is routed when <strong>MaxCallPickupAttempts</strong> is exceeded.</span></span></p>
<p><span data-ttu-id="ff058-p105">值必須是以字串 sip: 開頭的 SIP URI。例如，sip:bob@contoso.com。預設沒有轉接位址。</span><span class="sxs-lookup"><span data-stu-id="ff058-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-configure-call-park-settings"></a><span data-ttu-id="ff058-130">設定通話駐留設定</span><span class="sxs-lookup"><span data-stu-id="ff058-130">To configure Call Park settings</span></span>

1.  <span data-ttu-id="ff058-131">以[Lync server 2013 的委派設定許可權](lync-server-2013-delegate-setup-permissions.md)中所述，登入安裝了 Lync Server 管理命令介面的電腦，以作為 RTCUniversalServerAdmins 群組的成員或必要的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="ff058-131">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="ff058-132">啟動 Lync Server 管理命令介面：依序按一下 [**開始**]、[**所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="ff058-132">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="ff058-133">執行：</span><span class="sxs-lookup"><span data-stu-id="ff058-133">Run:</span></span>
    
        New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="ff058-134">使用 <STRONG>Get-CsSite</STRONG> Cmdlet 來識別網站。</span><span class="sxs-lookup"><span data-stu-id="ff058-134">Use the <STRONG>Get-CsSite</STRONG> cmdlet to identify the site.</span></span> <span data-ttu-id="ff058-135">如需詳細資訊，請參閱 Lync Server 管理命令介面檔。</span><span class="sxs-lookup"><span data-stu-id="ff058-135">For details, see Lync Server Management Shell documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="ff058-136">例如：</span><span class="sxs-lookup"><span data-stu-id="ff058-136">For example:</span></span>
    
        New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ff058-137">請參閱</span><span class="sxs-lookup"><span data-stu-id="ff058-137">See Also</span></span>


[<span data-ttu-id="ff058-138">在 Lync Server 2013 中自訂通話駐留的等候音樂</span><span class="sxs-lookup"><span data-stu-id="ff058-138">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)  


[<span data-ttu-id="ff058-139">New-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff058-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCpsConfiguration)  
[<span data-ttu-id="ff058-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="ff058-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCpsConfiguration)  
[<span data-ttu-id="ff058-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="ff058-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

