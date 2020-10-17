---
title: Lync Server 2013：為不是以 Windows 為基礎的裝置啟用 QoS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e9fe6364e92fc6416a78ec49001e94193ae9731e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500930"
---
# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="21929-102">對不是以 Windows 為基礎的裝置啟用 Lync Server 2013 中的 QoS</span><span class="sxs-lookup"><span data-stu-id="21929-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21929-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21929-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21929-104">當您安裝 Microsoft Lync Server 2013 時，將不會為組織中使用 Windows 以外作業系統的任何裝置啟用 [服務品質 (] QoS) 。</span><span class="sxs-lookup"><span data-stu-id="21929-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="21929-105">您可以從 Lync Server 2013 管理命令介面中執行下列命令，以進行驗證：</span><span class="sxs-lookup"><span data-stu-id="21929-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="21929-106">假設您已對媒體組態設定執行變更，就應該會得到類似下列的資訊：</span><span class="sxs-lookup"><span data-stu-id="21929-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="21929-107">如果 EnableQoS 屬性設定為 False (如先前的輸出所) 表示服務品質未針對使用 Windows 以外之作業系統的電腦和裝置啟用。</span><span class="sxs-lookup"><span data-stu-id="21929-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="21929-108">Lync Phone Edition 裝置預設會啟用 QoS;不過，您可以停用 Lync Phone Edition 的服務品質。</span><span class="sxs-lookup"><span data-stu-id="21929-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="21929-109">若要在全域範圍啟用服務品質，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="21929-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="21929-p103">先前的命令會啟用全域範圍的 QoS；但需要注意的是，媒體組態設定也會套用至網站範圍。若您要為網站啟用服務品質，就必須在呼叫 Set-CsMediaConfiguration 時包含組態設定的識別。例如，此命令會啟用 Redmond 網站的 QoS：</span><span class="sxs-lookup"><span data-stu-id="21929-p103">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope. If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration. For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="21929-p104">您是否需要啟用網站範圍的 QoS？答案是不一定。指派至網站範圍的設定會優先於指派至全域範圍的設定。假設您已啟用全域範圍的 QoS，但停用網站範圍的 QoS (針對 Redmond 網站)。則在此情況中，會因為網站設定優先，而停用 Redmond 網站的服務品質。若要啟用 Redmond 網站的 QoS，就必須使用會套用至網站的媒體組態設定。</span><span class="sxs-lookup"><span data-stu-id="21929-p104">Do you need to enable QoS at the site scope? That depends. Settings assigned to the site scope take precedence over settings assigned to the global scope. Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence. To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="21929-118">如果您想要同時針對所有媒體設定設定啟用 QoS (不論範圍) 然後在 Lync Server 管理命令介面中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="21929-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="21929-119">您可以對使用 Windows 以外之作業系統的裝置停用 QoS，方法是將 EnableQoS 屬性的值設為 False。</span><span class="sxs-lookup"><span data-stu-id="21929-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="21929-120">例如：</span><span class="sxs-lookup"><span data-stu-id="21929-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="21929-121">這使您能夠在網路的某些部分停用服務品質的同時，於網路的其他部分啟用 QoS (例如在 Redmond 網站上)。</span><span class="sxs-lookup"><span data-stu-id="21929-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="21929-122">QoS 只能使用 Windows 來啟用及停用 PowerShell Lync Server 控制台中無法使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="21929-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

