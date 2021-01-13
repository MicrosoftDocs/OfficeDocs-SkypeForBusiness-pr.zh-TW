---
title: 為不是以 Windows 為基礎的裝置啟用 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 瞭解如何為組織中使用 Windows 以外作業系統的裝置啟用 QoS。
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814173"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="a23a1-103">在不是以 Windows 為基礎的裝置上啟用商務用 Skype Server 中的 QoS</span><span class="sxs-lookup"><span data-stu-id="a23a1-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="a23a1-104">當您安裝商務用 Skype Server、服務品質 (QoS) 將不會為組織中使用 Windows 以外作業系統的任何裝置啟用。</span><span class="sxs-lookup"><span data-stu-id="a23a1-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="a23a1-105">您可以在商務用 Skype ServerManagement 命令介面中執行下列命令，以進行驗證：</span><span class="sxs-lookup"><span data-stu-id="a23a1-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="a23a1-106">假設您未對媒體設定設定進行任何變更，您應該會收到類似以下的資訊：</span><span class="sxs-lookup"><span data-stu-id="a23a1-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="a23a1-107">如果 EnableQoS 屬性設定為 False (如先前的輸出所) 表示服務品質未針對使用 Windows 以外之作業系統的電腦和裝置啟用。</span><span class="sxs-lookup"><span data-stu-id="a23a1-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="a23a1-108">若要在全域範圍啟用服務品質，請從商務用 Skype Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a23a1-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="a23a1-109">先前的命令會啟用全域範圍的 QoS；但需要注意的是，媒體組態設定也會套用至網站範圍。</span><span class="sxs-lookup"><span data-stu-id="a23a1-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="a23a1-110">如果您需要啟用網站的服務品質，您必須在呼叫 CsMediaConfiguration 時包含設定設定的身分識別。</span><span class="sxs-lookup"><span data-stu-id="a23a1-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="a23a1-111">例如，此命令會啟用 Redmond 網站的 QoS：</span><span class="sxs-lookup"><span data-stu-id="a23a1-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="a23a1-112">您是否需要啟用網站範圍的 QoS？</span><span class="sxs-lookup"><span data-stu-id="a23a1-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="a23a1-113">答案是不一定。</span><span class="sxs-lookup"><span data-stu-id="a23a1-113">That depends.</span></span> <span data-ttu-id="a23a1-114">指派至網站範圍的設定會優先於指派至全域範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="a23a1-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="a23a1-115">假設您已在全域範圍啟用 QoS，但在 Redmond 網站) 的網站範圍 (停用。</span><span class="sxs-lookup"><span data-stu-id="a23a1-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="a23a1-116">在此情況下，會停用 Redmond 網站的服務品質;這是因為網站設定會優先。</span><span class="sxs-lookup"><span data-stu-id="a23a1-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="a23a1-117">若要啟用 Redmond 網站的 QoS，您必須使用套用至該網站的媒體設定設定來執行。</span><span class="sxs-lookup"><span data-stu-id="a23a1-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="a23a1-118">如果您想要同時針對所有媒體設定設定啟用 QoS (不論範圍) ，請從 LSkype for Business Server Management Shell 中執行此命令：</span><span class="sxs-lookup"><span data-stu-id="a23a1-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="a23a1-119">您可以對使用 Windows 以外之作業系統的裝置停用 QoS，方法是將 EnableQoS 屬性的值設為 False。</span><span class="sxs-lookup"><span data-stu-id="a23a1-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="a23a1-120">例如：</span><span class="sxs-lookup"><span data-stu-id="a23a1-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="a23a1-121">這使您能夠在網路的某些部分停用服務品質的同時，於網路的其他部分啟用 QoS (例如在 Redmond 網站上)。</span><span class="sxs-lookup"><span data-stu-id="a23a1-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="a23a1-122">僅能使用 Windows PowerShell 來啟用及停用 QoS。</span><span class="sxs-lookup"><span data-stu-id="a23a1-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="a23a1-123">在商務用 Skype Server [控制台] 中無法使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="a23a1-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="a23a1-124">IOS 版本6.17 和更新版本的商務用 Skype 用戶端現在支援 QoS。</span><span class="sxs-lookup"><span data-stu-id="a23a1-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="a23a1-125">此 QoS 功能僅適用于直接註冊到受管理網路上內部 Skype for business 或 Lync 集區伺服器的商務用 Skype 用戶端和 IP 電話裝置。</span><span class="sxs-lookup"><span data-stu-id="a23a1-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="a23a1-126">QoS 不適用於透過網際網路路由傳送的流量。</span><span class="sxs-lookup"><span data-stu-id="a23a1-126">QoS is not applicable for traffic routed over the Internet.</span></span>



