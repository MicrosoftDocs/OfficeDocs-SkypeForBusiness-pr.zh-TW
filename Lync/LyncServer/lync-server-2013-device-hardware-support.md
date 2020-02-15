---
title: Lync Server 2013 裝置硬體支援
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device hardware support
ms:assetid: ba07ca91-32b4-49cf-801c-47a2d1d96e18
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412908(v=OCS.15)
ms:contentKeyID: 48185222
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0b4b0f24523044169ae3274ae4d0ff16ae9ff67
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044985"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="b10bb-102">Lync Server 2013 中的裝置硬體支援</span><span class="sxs-lookup"><span data-stu-id="b10bb-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b10bb-103">_**主題上次修改日期：** 2012年-12-14_</span><span class="sxs-lookup"><span data-stu-id="b10bb-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="b10bb-104">特定硬體設定必須在就緒，才能部署 IP 電話和類比裝置。</span><span class="sxs-lookup"><span data-stu-id="b10bb-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="b10bb-105">執行 Lync Phone Edition 的 IP 電話支援連結層探索通訊協定媒體端點探索 (LLDP-MED) 與 Power 乙太網路 (PoE) 上。</span><span class="sxs-lookup"><span data-stu-id="b10bb-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="b10bb-106">若要利用 LLDP-MED，參數必須支援 IEEE802.1AB 與 ANSI/TIA-1057年。</span><span class="sxs-lookup"><span data-stu-id="b10bb-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="b10bb-107">若要利用 PoE，參數必須支援 PoE802.3AF 或 802.3at。</span><span class="sxs-lookup"><span data-stu-id="b10bb-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="b10bb-108">若要啟用 LLDP-MED，管理員必須使用交換器主控台視窗來啟用 LLDP，並設定 LLDP-MED 網路原則使用正確的語音 VLAN id。</span><span class="sxs-lookup"><span data-stu-id="b10bb-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="b10bb-109">此外，如果您的部署包含類比裝置，您必須設定類比閘道使用 Lync Server，而且閘道必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="b10bb-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="b10bb-110">類比電話配接器 (ATA)</span><span class="sxs-lookup"><span data-stu-id="b10bb-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="b10bb-111">PSTN 類比閘道</span><span class="sxs-lookup"><span data-stu-id="b10bb-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="b10bb-112">內含 PSTN 類比閘道的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="b10bb-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="b10bb-113">內含可以 ATA 通訊之 PSTN 閘道的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="b10bb-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="b10bb-114">若要了解如何設定類比閘道，請參閱 「 規劃要部署類比裝置 」 在[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)Lync Server 2010 TechNet Library 中。</span><span class="sxs-lookup"><span data-stu-id="b10bb-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="b10bb-115">（類比裝置的運作方式相同 Lync Server 2013 的 Lync Server 2010 中一樣。）</span><span class="sxs-lookup"><span data-stu-id="b10bb-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b10bb-116">如果交換器支援此您可以設定指定切換為增強型 9-1-1 (E9-1-1)。</span><span class="sxs-lookup"><span data-stu-id="b10bb-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

