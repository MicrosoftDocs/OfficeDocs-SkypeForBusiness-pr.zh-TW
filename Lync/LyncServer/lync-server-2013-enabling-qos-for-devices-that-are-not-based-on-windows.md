---
title: Lync Server 2013：啟用不是以 Windows 為基礎的裝置的 QoS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: QoS for devices that are not based on Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d993a6905dfad9f5f2eda10a48553f2ae29b58ef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-qos-in-lync-server-2013-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="81bfa-102">針對不是以 Windows 為基礎的裝置啟用 Lync Server 2013 中的 QoS</span><span class="sxs-lookup"><span data-stu-id="81bfa-102">Enabling QoS in Lync Server 2013 for devices that are not based on Windows</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81bfa-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="81bfa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="81bfa-104">當您安裝 Microsoft Lync Server 2013 時，系統將不會針對您組織中使用 Windows 以外的作業系統的任何裝置啟用服務品質（QoS）。</span><span class="sxs-lookup"><span data-stu-id="81bfa-104">When you install Microsoft Lync Server 2013, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="81bfa-105">您可以從 Lync Server 2013 管理命令介面中執行下列命令，以進行驗證：</span><span class="sxs-lookup"><span data-stu-id="81bfa-105">You can verify this by running the following command from within the Lync Server 2013 Management Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="81bfa-106">假設您沒有對媒體設定設定進行任何變更，您應該會看到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="81bfa-106">Assuming you have not made any changes to your media configuration settings you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="81bfa-107">如果 EnableQoS 屬性設定為 False （如前面的輸出），表示沒有針對使用 Windows 以外的作業系統的電腦和裝置啟用服務品質。</span><span class="sxs-lookup"><span data-stu-id="81bfa-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span> <span data-ttu-id="81bfa-108">預設會啟用 Lync Phone 版裝置的 QoS;不過，您可以停用 Lync Phone Edition 的服務品質。</span><span class="sxs-lookup"><span data-stu-id="81bfa-108">QoS is enabled by default for Lync Phone Edition devices; however, it is possible to disable Quality of Service for Lync Phone Edition.</span></span>

<span data-ttu-id="81bfa-109">若要在全域範圍啟用服務品質，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="81bfa-109">To enable Quality of Service at the global scope, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="81bfa-110">上述命令可在全域範圍內啟用 QoS;不過，請務必注意，媒體配置設定也可以套用到網站範圍。</span><span class="sxs-lookup"><span data-stu-id="81bfa-110">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="81bfa-111">如果您需要為網站啟用服務品質，您必須在呼叫 CsMediaConfiguration 時包含設定設定的身分識別。</span><span class="sxs-lookup"><span data-stu-id="81bfa-111">If you need to enable Quality of Service for a site you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="81bfa-112">例如，這個命令可為雷蒙德網站啟用 QoS：</span><span class="sxs-lookup"><span data-stu-id="81bfa-112">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True

<div>


> [!NOTE]  
> <span data-ttu-id="81bfa-113">您是否需要在網站範圍中啟用 QoS？</span><span class="sxs-lookup"><span data-stu-id="81bfa-113">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="81bfa-114">視情況而定。</span><span class="sxs-lookup"><span data-stu-id="81bfa-114">That depends.</span></span> <span data-ttu-id="81bfa-115">指派給網站範圍的設定會優先于指派給全域範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="81bfa-115">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="81bfa-116">假設您已在全域範圍啟用 QoS，但在網站範圍停用（針對雷德蒙的網站）。在這種情況下，雷德蒙者網站的服務品質將會停用;這是因為 [網站設定] 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="81bfa-116">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site.) In that case, Quality of Service will be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="81bfa-117">若要啟用雷德蒙網站的 QoS，您必須使用套用至該網站的媒體設定設定來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="81bfa-117">To enable QoS for the Redmond site you will have to do so using the media configuration settings applied to that site.</span></span>



</div>

<span data-ttu-id="81bfa-118">如果您想要同時啟用所有媒體設定的 QoS （無論範圍為何），請在 Lync Server 管理命令介面中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="81bfa-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope) then run this command from within the Lync Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="81bfa-119">您可以透過將 EnableQoS 屬性的值設定為 False，來停用使用 Windows 以外作業系統的裝置的 QoS。</span><span class="sxs-lookup"><span data-stu-id="81bfa-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="81bfa-120">例如：</span><span class="sxs-lookup"><span data-stu-id="81bfa-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="81bfa-121">這可讓您在網路的某些部分（例如，在雷德蒙的網站）上實現 QoS，同時在網路的其他部分停止服務品質。</span><span class="sxs-lookup"><span data-stu-id="81bfa-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="81bfa-122">QoS 只能使用 Windows PowerShell 來啟用和停用這些選項無法在 Lync Server [控制台] 中使用。</span><span class="sxs-lookup"><span data-stu-id="81bfa-122">QoS can only be enabled and disabled by using Windows PowerShell These options are not available in the Lync Server Control Panel.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

