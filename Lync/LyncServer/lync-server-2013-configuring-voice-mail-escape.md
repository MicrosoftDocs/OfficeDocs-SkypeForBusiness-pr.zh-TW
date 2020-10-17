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
ms.openlocfilehash: 7c3faf28bdd85f32de1560d35aaf35392fef9746
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516950"
---
# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="634ba-102">在 Lync Server 2013 中設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="634ba-102">Configuring voice mail escape in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="634ba-103">_**主題上次修改日期：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="634ba-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="634ba-104">當使用者設定同時響鈴的行動電話時，如果行動電話關閉、電池計量不足或超出範圍，則通常會將來電者路由傳送至使用者的個人語音信箱。</span><span class="sxs-lookup"><span data-stu-id="634ba-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="634ba-105">使用 Lync Server 2013，使用者可以選擇要將與業務相關的電話路由傳送至公司語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="634ba-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="634ba-106">具體而言，您可以設定 timer，如果在所定義的時間範圍內，來電者的語音信箱接聽來電，Lync Server 會中斷與電信公司的語音信箱系統的連線 (和使用者的個人語音信箱) ，而使用者在公司系統中的剩餘端點會繼續振鈴。</span><span class="sxs-lookup"><span data-stu-id="634ba-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="634ba-107">如此一來，來電者就會自動路由傳送至使用者的公司語音信箱。</span><span class="sxs-lookup"><span data-stu-id="634ba-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="634ba-108">使用下列參數，在語音原則層級上使用 Lync Server 管理命令介面 Cmdlet， **Set-CsVoicePolicy**執行此設定。</span><span class="sxs-lookup"><span data-stu-id="634ba-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="634ba-109">設定語音信箱轉義</span><span class="sxs-lookup"><span data-stu-id="634ba-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="634ba-110">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="634ba-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="634ba-111">指定下列要 **Set-CsVoicePolicy**的參數：</span><span class="sxs-lookup"><span data-stu-id="634ba-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="634ba-112">**EnableVoicemailEscapeTimer** -啟用或停用轉義計時器。</span><span class="sxs-lookup"><span data-stu-id="634ba-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="634ba-113">**PSTNVoicemailEscapeTimer** -指定超時值，以毫秒為單位。</span><span class="sxs-lookup"><span data-stu-id="634ba-113">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="634ba-114">預設值為1500毫秒，值的範圍為0毫秒到8000毫秒。</span><span class="sxs-lookup"><span data-stu-id="634ba-114">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="634ba-115">範例</span><span class="sxs-lookup"><span data-stu-id="634ba-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="634ba-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="634ba-116">See Also</span></span>


[<span data-ttu-id="634ba-117">在 Lync Server 2013 中設定語音原則和 PSTN 使用方式記錄，以授權呼叫功能和許可權</span><span class="sxs-lookup"><span data-stu-id="634ba-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

