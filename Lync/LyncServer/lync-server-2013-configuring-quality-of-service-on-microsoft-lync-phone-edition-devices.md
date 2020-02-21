---
title: Microsoft Lync Phone Edition 裝置上設定服務品質
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
ms.openlocfilehash: 7e154df7c71b32e9f5f1c1440707511bc91c3117
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-on-microsoft-lync-phone-edition-devices-in-lync-server-2013"></a><span data-ttu-id="4210a-102">在 Lync Server 2013 的 Microsoft Lync Phone Edition 裝置上設定服務品質</span><span class="sxs-lookup"><span data-stu-id="4210a-102">Configuring Quality of Service on Microsoft Lync Phone Edition devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4210a-103">_**主題上次修改日期：** 2012年-11-01_</span><span class="sxs-lookup"><span data-stu-id="4210a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4210a-104">雖然例如 Iphone 裝置的預設不會啟用服務品質 (QoS)，執行 Lync Phone Edition 裝置的預設會啟用 QoS。</span><span class="sxs-lookup"><span data-stu-id="4210a-104">Although Quality of Service (QoS) is not enabled by default for devices such as iPhones, QoS is enabled by default for devices running Lync Phone Edition.</span></span> <span data-ttu-id="4210a-105">（在這些裝置是通常稱為 UC 或整合通訊的電話。）若要確認此，請執行 Lync Server 管理命令介面中的從下列 Windows PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="4210a-105">(These devices are commonly referred to as UC or Unified Communication phones.) To verify this, run the following Windows PowerShell command from within the Lync Server Management Shell:</span></span>

    Get-CsUCPhoneConfiguration

<span data-ttu-id="4210a-106">如果您不具有 UC 電話組態設定進行任何變更然後您會得到如下所示的資訊：</span><span class="sxs-lookup"><span data-stu-id="4210a-106">If you have not made any changes to your UC phone configuration settings then you will get back information that looks like this:</span></span>

    Identity             : Global
    CalendarPollInterval : 00:03:00
    EnforcePhoneLock     : True
    PhoneLockTimeout     : 00:10:00
    MinPhonePinLength    : 6
    SIPSecurityMode      : High
    VoiceDiffServTag     : 40
    Voice8021p           : 0
    LoggingLevel         : Off

<span data-ttu-id="4210a-107">以服務品質來說，只有其中一個這些屬性會感興趣的： VoiceDiffServTag。</span><span class="sxs-lookup"><span data-stu-id="4210a-107">For Quality of Service purposes, only one of these properties is of interest: VoiceDiffServTag.</span></span> <span data-ttu-id="4210a-108">VoiceDiffServTag 代表指派給 emanating 從 Lync Phone Edition 裝置的語音流量的 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="4210a-108">The VoiceDiffServTag represents the DSCP value assigned to voice traffic emanating from a Lync Phone Edition device.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4210a-109">Lync Server 2013 中已不再支援 Voice8021p 參數。</span><span class="sxs-lookup"><span data-stu-id="4210a-109">The Voice8021p parameter is no longer supported in Lync Server 2013.</span></span> <span data-ttu-id="4210a-110">參數是仍適用於與 Microsoft Lync Server 2010; 回溯相容性不過，它就與 Lync Server 2013 搭配使用的裝置上沒有作用。</span><span class="sxs-lookup"><span data-stu-id="4210a-110">The parameter is still valid for backward compatibility with Microsoft Lync Server 2010; however, it has no effect on devices used with Lync Server 2013.</span></span>



</div>

<span data-ttu-id="4210a-111">在大部分的網路中，標示為 40 VoiceDiffServTag 與 Lync Phone Edition 封包應該不會造成任何問題。</span><span class="sxs-lookup"><span data-stu-id="4210a-111">In most networks, marking Lync Phone Edition packets with a VoiceDiffServTag of 40 should not cause any problems.</span></span> <span data-ttu-id="4210a-112">不過，40 不是通常用於音訊流量; 值相反地，DSCP 程式碼 46 幾乎都已標示音訊的流量。</span><span class="sxs-lookup"><span data-stu-id="4210a-112">However, 40 is not the value typically used for audio traffic; instead, audio traffic is almost always marked with the DSCP code 46.</span></span> <span data-ttu-id="4210a-113">為了維持整個網路的一致性，您可能想要變更為 [46 UC 電話的 VoiceDiffServTag 屬性。</span><span class="sxs-lookup"><span data-stu-id="4210a-113">In order to maintain consistency throughout your network, you might want to change the VoiceDiffServTag property of your UC phones to 46.</span></span>

<span data-ttu-id="4210a-114">若要這樣做，您可以使用 Windows PowerShell 或 Lync Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="4210a-114">To do that, you can use either Windows PowerShell or the Lync Server Control Panel.</span></span> <span data-ttu-id="4210a-115">若要使用 Windows PowerShell 修改 VoiceDiffServTag 值，執行從 Lync Server 管理命令介面中的下列命令：</span><span class="sxs-lookup"><span data-stu-id="4210a-115">To modify the VoiceDiffServTag value by using Windows PowerShell, run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="4210a-116">上述命令會修改全域 UC 電話組態設定的集合。</span><span class="sxs-lookup"><span data-stu-id="4210a-116">The preceding command modifies the global collection of UC phone configuration settings.</span></span> <span data-ttu-id="4210a-117">不過請注意，也可以將 UC 電話設定指派至網站範圍。</span><span class="sxs-lookup"><span data-stu-id="4210a-117">Note, however, that UC phone settings can also be assigned to the site scope.</span></span> <span data-ttu-id="4210a-118">若要修改在網站範圍的 UC 電話組態設定，您必須指定身分識別的網站。</span><span class="sxs-lookup"><span data-stu-id="4210a-118">To modify UC phone configuration settings at the site scope, you must specify the site Identity.</span></span> <span data-ttu-id="4210a-119">例如：</span><span class="sxs-lookup"><span data-stu-id="4210a-119">For example:</span></span>

    Set-CsUCPhoneConfiguration -Identity "site:Redmond" -VoiceDiffServTag 46

<span data-ttu-id="4210a-120">您也可以使用下列命令同時修改所有 UC 電話組態設定：</span><span class="sxs-lookup"><span data-stu-id="4210a-120">You can also use the following command to simultaneously modify all your UC phone configuration settings:</span></span>

    Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -VoiceDiffServTag 46

<span data-ttu-id="4210a-121">如果您想要使用 Lync Server Control Panel 此變更，然後啟動 [控制台]，然後完成下列程序：</span><span class="sxs-lookup"><span data-stu-id="4210a-121">If you prefer to make this change using Lync Server Control Panel, then start the Control Panel and then complete the following procedure:</span></span>

1.  <span data-ttu-id="4210a-122">按一下 [**用戶端**，然後按一下 [**裝置組態**。</span><span class="sxs-lookup"><span data-stu-id="4210a-122">Click **Clients** and then click **Device Configuration**.</span></span>

2.  <span data-ttu-id="4210a-123">在 [**裝置組態**] 索引標籤中，按兩下您想要修改 （例如，**全域**） 設定的集合。</span><span class="sxs-lookup"><span data-stu-id="4210a-123">On the **Device Configuration** tab, double-click the collection of settings you want to modify (for example, **Global**).</span></span>

3.  <span data-ttu-id="4210a-124">在 [**編輯裝置設定**] 對話方塊中，將**語音服務品質 (QoS)** ] 方塊的值設定為 [ **46** ，然後按一下 [**認可]**。</span><span class="sxs-lookup"><span data-stu-id="4210a-124">In the **Edit Device Configuration** dialog box, set the value of the **Voice Quality of Service (QoS)** box to **46** and then click **Commit**.</span></span>

<span data-ttu-id="4210a-125">如果您有多個您想要重複此程序，針對每個集合的 UC 電話設定的集合。</span><span class="sxs-lookup"><span data-stu-id="4210a-125">If you have multiple collections you will need to repeat this process for each collection of UC phone settings.</span></span> <span data-ttu-id="4210a-126">Lync Server 控制台不允許您同時修改多個設定集合。</span><span class="sxs-lookup"><span data-stu-id="4210a-126">Lync Server Control Panel will not allow you to simultaneously modify multiple setting collections.</span></span>

<span data-ttu-id="4210a-127">如果您有不採用 Windows 作業系統 （例如 Iphone) 在組織中的裝置這些裝置不會受到變更 VoiceDiffServTag 設定的影響。</span><span class="sxs-lookup"><span data-stu-id="4210a-127">If you have devices that are not based on the Windows operating system (such as iPhones) in your organization these devices will not be affected by changing the VoiceDiffServTag setting.</span></span> <span data-ttu-id="4210a-128">如果您想要變更這些裝置上的 DSCP 值必須為每個裝置類型參照的管理手冊。</span><span class="sxs-lookup"><span data-stu-id="4210a-128">If you want to change DSCP values on those devices you will need to refer to the administration manual for each of your device types.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

