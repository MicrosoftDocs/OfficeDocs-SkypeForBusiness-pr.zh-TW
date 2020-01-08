---
title: 在 Microsoft Lync Phone Edition 裝置上設定品質服務
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f7f96e90aa07da193f9ffb714fc3437ba46cd8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="7fe00-102">在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質</span><span class="sxs-lookup"><span data-stu-id="7fe00-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe00-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="7fe00-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="7fe00-104">雖然預設不會針對裝置（例如 Iphone）啟用服務品質（QoS），但在執行 Lync Phone Edition 的裝置上預設會啟用 QoS。</span><span class="sxs-lookup"><span data-stu-id="7fe00-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="7fe00-105">（這些裝置通常稱為 [UC] 或 [整合通訊電話]）。若要驗證這一點，請從 Lync Server Management Shell 中執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="7fe00-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="7fe00-106">如果您未對 UC 手機設定設定進行任何變更，則會傳回如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="7fe00-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="7fe00-107">針對服務品質而言，只有下列其中一個屬性是重要的： VoiceDiffServTag。</span><span class="sxs-lookup"><span data-stu-id="7fe00-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="7fe00-108">VoiceDiffServTag 代表指派給 Lync Phone Edition 裝置的語音流量 emanating 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="7fe00-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="7fe00-109">Lync Server 2013 不再支援 Voice8021p 參數。</span><span class="sxs-lookup"><span data-stu-id="7fe00-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="7fe00-110">這個參數仍然有效，可讓您與 Microsoft Lync Server 2010 保持向後相容;不過，它不會影響 Lync Server 2013 使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="7fe00-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="7fe00-111">在大部分的網路中，使用 VoiceDiffServTag 40 來標示 Lync Phone Edition 資料包不會造成任何問題。</span><span class="sxs-lookup"><span data-stu-id="7fe00-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="7fe00-112">不過，40不是通常用於音訊流量的值;相反地，音訊流量幾乎總是以 DSCP 代碼46標示。</span><span class="sxs-lookup"><span data-stu-id="7fe00-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="7fe00-113">為了維持整個網路的一致性，您可能會想要將 UC 手機的 VoiceDiffServTag 屬性變更為46。</span><span class="sxs-lookup"><span data-stu-id="7fe00-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="7fe00-114">若要這樣做，您可以使用 Windows PowerShell 或 Lync Server [控制台]。</span><span class="sxs-lookup"><span data-stu-id="7fe00-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="7fe00-115">若要使用 Windows PowerShell 來修改 VoiceDiffServTag 值，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="7fe00-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="7fe00-116">上述命令會修改 UC 手機設定的全域集合。</span><span class="sxs-lookup"><span data-stu-id="7fe00-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="7fe00-117">但請注意，UC 電話設定也可以指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="7fe00-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="7fe00-118">若要在網站範圍修改 UC 手機設定，您必須指定網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="7fe00-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="7fe00-119">例如：</span><span class="sxs-lookup"><span data-stu-id="7fe00-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="7fe00-120">您也可以使用下列命令，同時修改所有的 UC 手機設定：</span><span class="sxs-lookup"><span data-stu-id="7fe00-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="7fe00-121">如果您想要使用 Lync Server [控制台] 進行這項變更，請啟動 [控制台]，然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="7fe00-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="7fe00-122">按一下 [**用戶端**]，然後按一下 [**裝置配置**]。</span><span class="sxs-lookup"><span data-stu-id="7fe00-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="7fe00-123">在 [**裝置**設定] 索引標籤上，按兩下您要修改的設定集合（例如 [**全域**]）。</span><span class="sxs-lookup"><span data-stu-id="7fe00-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="7fe00-124">在 [**編輯裝置**設定] 對話方塊中，將 [**語音服務品質（QoS）** ] 方塊的值設定為**46** ，然後按一下 [Commit] （**提交**）。</span><span class="sxs-lookup"><span data-stu-id="7fe00-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="7fe00-125">如果您有多個集合，您將需要針對每個 UC 手機設定集合重複此程式。</span><span class="sxs-lookup"><span data-stu-id="7fe00-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="7fe00-126">Lync Server [控制台] 不會讓您同時修改多個設定集合。</span><span class="sxs-lookup"><span data-stu-id="7fe00-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="7fe00-127">如果您的裝置不是以 Windows 作業系統（例如 Iphone）為基礎，這些裝置將不會受到變更 VoiceDiffServTag 設定的影響。</span><span class="sxs-lookup"><span data-stu-id="7fe00-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="7fe00-128">如果您想要變更這些裝置上的 DSCP 值，您需要參照每個裝置類型的系統管理手冊。</span><span class="sxs-lookup"><span data-stu-id="7fe00-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

