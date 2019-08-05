---
title: 啟用不是以 Windows 為基礎的裝置的 QoS
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 瞭解如何針對貴組織中使用 Windows 以外的作業系統的裝置啟用 QoS。
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188530"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="93222-103">在商務用 Skype Server 中啟用 QoS (適用于不以 Windows 為基礎的裝置)</span><span class="sxs-lookup"><span data-stu-id="93222-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="93222-104">當您安裝商務用 Skype Server 時, 貴組織中任何使用 Windows 以外作業系統的裝置, 都不會啟用服務品質 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="93222-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="93222-105">您可以從商務用 Skype ServerManagement Shell 中執行下列命令, 以進行驗證:</span><span class="sxs-lookup"><span data-stu-id="93222-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="93222-106">如果您沒有對媒體設定設定進行任何變更, 您應該會看到類似以下的資訊:</span><span class="sxs-lookup"><span data-stu-id="93222-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="93222-107">如果 EnableQoS 屬性設定為 False (如前面的輸出), 表示沒有針對使用 Windows 以外的作業系統的電腦和裝置啟用服務品質。</span><span class="sxs-lookup"><span data-stu-id="93222-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="93222-108">若要在全域範圍啟用服務品質, 請在商務用 Skype Server Management Shell 中執行下列命令:</span><span class="sxs-lookup"><span data-stu-id="93222-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="93222-109">上述命令可在全域範圍內啟用 QoS;不過, 請務必注意, 媒體配置設定也可以套用到網站範圍。</span><span class="sxs-lookup"><span data-stu-id="93222-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="93222-110">如果您需要為網站啟用服務品質, 您必須在呼叫 CsMediaConfiguration 時包含設定設定的身分識別。</span><span class="sxs-lookup"><span data-stu-id="93222-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="93222-111">例如, 這個命令可為雷蒙德網站啟用 QoS:</span><span class="sxs-lookup"><span data-stu-id="93222-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="93222-112">您是否需要在網站範圍中啟用 QoS？</span><span class="sxs-lookup"><span data-stu-id="93222-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="93222-113">視情況而定。</span><span class="sxs-lookup"><span data-stu-id="93222-113">That depends.</span></span> <span data-ttu-id="93222-114">指派給網站範圍的設定會優先于指派給全域範圍的設定。</span><span class="sxs-lookup"><span data-stu-id="93222-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="93222-115">假設您已在全域範圍啟用 QoS, 但在網站範圍停用 (針對雷德蒙的網站)。</span><span class="sxs-lookup"><span data-stu-id="93222-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="93222-116">在這種情況下, 雷德蒙者網站的服務品質會停用;這是因為 [網站設定] 的優先順序。</span><span class="sxs-lookup"><span data-stu-id="93222-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="93222-117">若要啟用雷德蒙網站的 QoS, 您必須使用套用至該網站的媒體設定設定來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="93222-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="93222-118">如果您想要同時啟用所有媒體設定的 QoS (無論範圍為何), 請在商務用 LSkype Server Management Shell 中執行此命令:</span><span class="sxs-lookup"><span data-stu-id="93222-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="93222-119">您可以透過將 EnableQoS 屬性的值設定為 False, 來停用使用 Windows 以外作業系統的裝置的 QoS。</span><span class="sxs-lookup"><span data-stu-id="93222-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="93222-120">例如：</span><span class="sxs-lookup"><span data-stu-id="93222-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="93222-121">這可讓您在網路的某些部分 (例如, 在雷德蒙的網站) 上實現 QoS, 同時在網路的其他部分停止服務品質。</span><span class="sxs-lookup"><span data-stu-id="93222-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="93222-122">QoS 只能使用 Windows PowerShell 來啟用和停用。</span><span class="sxs-lookup"><span data-stu-id="93222-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="93222-123">在商務用 Skype Server 控制台中無法使用這些選項。</span><span class="sxs-lookup"><span data-stu-id="93222-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


