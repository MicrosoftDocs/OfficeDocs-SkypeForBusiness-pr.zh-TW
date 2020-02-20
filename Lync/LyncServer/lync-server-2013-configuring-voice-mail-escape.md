---
title: Lync Server 2013： 設定語音信箱逸出
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
ms.openlocfilehash: 43e5ec9a9f932b9c8970886daf439bae6934d36b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-mail-escape-in-lync-server-2013"></a><span data-ttu-id="81efc-102">在 Lync Server 2013 中設定語音信箱逸出</span><span class="sxs-lookup"><span data-stu-id="81efc-102">Configuring voice mail escape in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81efc-103">_**上次修改主題：** 2013年-02-22_</span><span class="sxs-lookup"><span data-stu-id="81efc-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="81efc-104">當使用者設定行動電話同時響鈴時，來電者將通常會路由傳送至使用者的個人語音信箱如果行動電話已關機、 電池電力耗盡或超出範圍。</span><span class="sxs-lookup"><span data-stu-id="81efc-104">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user’s personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="81efc-105">與 Lync Server 2013 中，使用者可以選擇將業務相關的通話路由傳送至其公司的語音信箱系統。</span><span class="sxs-lookup"><span data-stu-id="81efc-105">With Lync Server 2013, users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="81efc-106">具體而言，可以設定計時器，而且如果所定義的時間範圍內的電信業者的語音信箱接聽電話，Lync Server 會從電信業者的語音郵件系統 （和使用者的個人語音信箱），中斷時剩餘的使用者端點公司系統中的繼續執行響鈴。</span><span class="sxs-lookup"><span data-stu-id="81efc-106">Specifically, a timer can be configured, and if the call is answered by the carrier’s voice mail within the range of time defined, Lync Server will disconnect from the carrier’s voice mail system (and the user’s personal voice mail), while the user’s remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="81efc-107">如此一來，來電者會自動路由傳送至使用者的企業語音信箱。</span><span class="sxs-lookup"><span data-stu-id="81efc-107">This way, the caller is automatically routed to the user’s corporate voice mail.</span></span>

<span data-ttu-id="81efc-108">此設定是在語音原則層級，使用下列參數使用 Lync Server 管理命令介面 cmdlet **Set-csvoicepolicy**，在執行。</span><span class="sxs-lookup"><span data-stu-id="81efc-108">This configuration is performed using the Lync Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

<div>

## <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="81efc-109">若要設定語音信箱逸出</span><span class="sxs-lookup"><span data-stu-id="81efc-109">To configure voice mail escape</span></span>

1.  <span data-ttu-id="81efc-110">啟動 Lync Server 管理命令介面： 按一下 [**開始]**，按一下 [**所有程式]**、 [ **Microsoft Lync Server 2013**]，然後按一下**Lync Server 管理命令介面**。</span><span class="sxs-lookup"><span data-stu-id="81efc-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="81efc-111">指定要**Set-csvoicepolicy**的下列參數：</span><span class="sxs-lookup"><span data-stu-id="81efc-111">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
      - <span data-ttu-id="81efc-112">**EnableVoicemailEscapeTimer** -啟用或停用逸出計時器。</span><span class="sxs-lookup"><span data-stu-id="81efc-112">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
      - <span data-ttu-id="81efc-113">**PSTNVoicemailEscapeTimer** -以毫秒為單位指定的逾時值。</span><span class="sxs-lookup"><span data-stu-id="81efc-113">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds.</span></span> <span data-ttu-id="81efc-114">預設值為 1500年毫秒，且值可介於 0 毫秒到 8000 （毫秒）。</span><span class="sxs-lookup"><span data-stu-id="81efc-114">The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

</div>

<div>

## <a name="example"></a><span data-ttu-id="81efc-115">範例</span><span class="sxs-lookup"><span data-stu-id="81efc-115">Example</span></span>

    Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
    
    Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="81efc-116">請參閱</span><span class="sxs-lookup"><span data-stu-id="81efc-116">See Also</span></span>


[<span data-ttu-id="81efc-117">設定語音原則和 PSTN 使用方式記錄，以授權撥號功能及 Lync Server 2013 中的權限</span><span class="sxs-lookup"><span data-stu-id="81efc-117">Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

