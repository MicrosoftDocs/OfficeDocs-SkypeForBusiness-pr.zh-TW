---
title: 在 Microsoft Lync Phone Edition 裝置上設定服務品質
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service on Microsoft Lync Phone Edition devices
ms:assetid: a6eb2620-a512-4ab6-bdfd-eb76be43bbfe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205137(v=OCS.15)
ms:contentKeyID: 48185004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c69bf438965c536a3ba424699a7109308368397
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534960"
---
# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="2a291-102">在 Lync Server 2013 中設定 Microsoft Lync Phone Edition 裝置上的服務品質</span><span class="sxs-lookup"><span data-stu-id="2a291-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a291-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2a291-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2a291-104">雖然服務品質 (QoS 不會為 Iphone 等裝置啟用) ，但預設為執行 Lync Phone Edition 的裝置啟用 QoS。</span><span class="sxs-lookup"><span data-stu-id="2a291-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="2a291-105"> (這些裝置通常稱為 UC 或整合通訊電話。 ) 若要確認這一點，請從 Lync Server 管理命令介面中執行下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="2a291-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="2a291-106">如果您未對 UC 電話設定設定進行任何變更，就會得到如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="2a291-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="2a291-107">出於服務品質目的，只有其中一項屬性為相關事項： VoiceDiffServTag。</span><span class="sxs-lookup"><span data-stu-id="2a291-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="2a291-108">VoiceDiffServTag 代表指派給 Lync Phone Edition 裝置之語音流量 emanating 的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="2a291-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2a291-109">Lync Server 2013 中已不再支援 Voice8021p 參數。</span><span class="sxs-lookup"><span data-stu-id="2a291-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="2a291-110">參數仍然有效，可與 Microsoft Lync Server 2010 保持回溯相容性;不過，它不會影響 Lync Server 2013 使用的裝置。</span><span class="sxs-lookup"><span data-stu-id="2a291-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="2a291-111">在大部分的網路中，使用 VoiceDiffServTag 40 來標示 Lync Phone Edition 的資料包不會造成任何問題。</span><span class="sxs-lookup"><span data-stu-id="2a291-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="2a291-112">不過，40不是一般用於音訊流量的值;相反地，音訊流量幾乎都是以 DSCP 碼46標示。</span><span class="sxs-lookup"><span data-stu-id="2a291-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="2a291-113">為了維持整個網路的一致性，您可能想要將 UC 電話的 VoiceDiffServTag 屬性變更為46。</span><span class="sxs-lookup"><span data-stu-id="2a291-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="2a291-114">若要這麼做，您可以使用 [Windows PowerShell] 或 [Lync Server] 控制台。</span><span class="sxs-lookup"><span data-stu-id="2a291-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="2a291-115">若要使用 Windows PowerShell 來修改 VoiceDiffServTag 值，請在 Lync Server 管理命令介面中執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="2a291-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="2a291-116">上述命令會修改 UC 電話設定的全域集合。</span><span class="sxs-lookup"><span data-stu-id="2a291-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="2a291-117">不過，請注意，也可以將 UC 電話設定指派給網站範圍。</span><span class="sxs-lookup"><span data-stu-id="2a291-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="2a291-118">若要修改網站範圍的 UC 電話設定設定，您必須指定網站身分識別。</span><span class="sxs-lookup"><span data-stu-id="2a291-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="2a291-119">例如：</span><span class="sxs-lookup"><span data-stu-id="2a291-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="2a291-120">您也可以使用下列命令同時修改所有的 UC 電話設定：</span><span class="sxs-lookup"><span data-stu-id="2a291-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="2a291-121">如果您想要使用 Lync Server 控制台進行此變更，請啟動 [控制台]，然後完成下列程式：</span><span class="sxs-lookup"><span data-stu-id="2a291-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="2a291-122">按一下 [ **用戶端** ]，然後按一下 [ **裝置**設定]。</span><span class="sxs-lookup"><span data-stu-id="2a291-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="2a291-123">在 [ **裝置** 設定] 索引標籤上，按兩下您要修改的設定集合 (例如「 **全域**) 」。</span><span class="sxs-lookup"><span data-stu-id="2a291-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="2a291-124">在 [ **編輯裝置** 設定] 對話方塊中，將 [ \*\*語音服務品質 (QoS) \*\* ] 方塊的值設為 **46** ，然後按一下 [ **認可**]。</span><span class="sxs-lookup"><span data-stu-id="2a291-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="2a291-125">如果您有多個集合，則每個 UC 電話設定集合都需要重複此程式。</span><span class="sxs-lookup"><span data-stu-id="2a291-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="2a291-126">Lync Server 控制台不會允許您同時修改多個設定集合。</span><span class="sxs-lookup"><span data-stu-id="2a291-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="2a291-127">如果您有不是以 Windows 作業系統為基礎的裝置 (例如組織中的 Iphone) ，這些裝置將不會受到變更 VoiceDiffServTag 設定的影響。</span><span class="sxs-lookup"><span data-stu-id="2a291-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="2a291-128">如果您想要在這些裝置上變更 DSCP 值，您將需要參照每種裝置類型的管理手冊。</span><span class="sxs-lookup"><span data-stu-id="2a291-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

