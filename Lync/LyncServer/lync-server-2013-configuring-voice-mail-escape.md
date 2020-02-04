---
title: Lync Server 2013：設定語音信箱轉義
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice mail escape
ms:assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688157(v=OCS.15)
ms:contentKeyID: 49733761
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c32d3bbc39d8f18e30153193c1e722db1ec9d50e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="b2d97-102">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="b2d97-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2d97-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="b2d97-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="b2d97-104">當使用者設定同時撥打至行動電話時，如果行動電話關閉、不使用電池電源或超出範圍，通常會將呼叫者路由到使用者的個人語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b2d97-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="b2d97-105">使用 Lync Server 2013，使用者可以選擇要將商務相關通話路由至其公司語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="b2d97-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="b2d97-106">具體來說，您可以設定計時器，並在已定義的時間範圍內，由承運人的語音信箱來應答通話，Lync Server 會中斷與載波語音信箱系統（與使用者的個人語音信箱）的連線，而使用者的剩餘公司系統中的端點持續撥打。</span><span class="sxs-lookup"><span data-stu-id="b2d97-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="b2d97-107">如此一來，來電者就會自動路由到使用者的公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="b2d97-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="b2d97-108">此設定是在語音原則層級使用 Lync Server Management Shell Cmdlet （ **CsVoicePolicy**）執行，並使用下列參數。</span><span class="sxs-lookup"><span data-stu-id="b2d97-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="b2d97-109">若要設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="b2d97-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="b2d97-110">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="b2d97-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b2d97-111">指定下列參數來**設定-CsVoicePolicy**：</span><span class="sxs-lookup"><span data-stu-id="b2d97-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="b2d97-112">**EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。</span><span class="sxs-lookup"><span data-stu-id="b2d97-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="b2d97-113">**PSTNVoicemailEscapeTimer** -指定超時值（以毫秒為單位）。</span><span class="sxs-lookup"><span data-stu-id="b2d97-113">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="b2d97-114">預設值為1500毫秒，值的範圍可以是0毫秒到8000毫秒。</span><span class="sxs-lookup"><span data-stu-id="b2d97-114">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="b2d97-115">範例</span><span class="sxs-lookup"><span data-stu-id="b2d97-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2d97-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="b2d97-116">See Also</span></span>


[<span data-ttu-id="b2d97-117">在 Lync Server 2013 中設定用於授權撥號功能和權限的語音原則和 PSTN 使用方式記錄</span><span class="sxs-lookup"><span data-stu-id="b2d97-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

