---
title: Lync Server 2013 裝置硬體支援
description: Lync Server 2013 裝置硬體支援。
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
ms.openlocfilehash: cd03936d35fbc3a639a3ba4596a4357e8e379719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575659"
---
# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="d5c4b-103">Lync Server 2013 中的裝置硬體支援</span><span class="sxs-lookup"><span data-stu-id="d5c4b-103">Device hardware support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5c4b-104">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="d5c4b-104">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="d5c4b-105">在您部署 IP 電話和類比裝置之前，必須準備好特定的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-105">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="d5c4b-106">執行 Lync Phone Edition 的 IP 電話支援連結層探索 Protocol-Media 端點探索 (LLDP-MED) 及 Power over Ethernet (PoE) 。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-106">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="d5c4b-107">若要利用 LLDP-MED，參數必須支援 IEEE 802.1 AB 和 ANSI/TIA-1057。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-107"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="d5c4b-108">為了利用 PoE，交換器必須支援 PoE 802.3 AF 或 802.3 at。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-108">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="d5c4b-109">若要啟用 LLDP-MED，管理員必須使用切換主控台視窗來啟用 LLDP，並使用正確的語音 VLAN 識別碼來設定 LLDP-MED 網路原則。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-109">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="d5c4b-110">此外，如果您的部署包含類比裝置，您必須設定模擬閘道以使用 Lync Server，而閘道必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d5c4b-110">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="d5c4b-111">類比電話配接器 (ATA)</span><span class="sxs-lookup"><span data-stu-id="d5c4b-111">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="d5c4b-112">PSTN 類比閘道</span><span class="sxs-lookup"><span data-stu-id="d5c4b-112">A PSTN analog gateway</span></span>

  - <span data-ttu-id="d5c4b-113">內含 PSTN 類比閘道的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="d5c4b-113">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="d5c4b-114">內含可以 ATA 通訊之 PSTN 閘道的 Survivable Branch Appliance</span><span class="sxs-lookup"><span data-stu-id="d5c4b-114">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="d5c4b-115">若要瞭解如何設定類比閘道，請參閱 [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) Lync Server 2010 TechNet 文件庫中的「規劃部署類比裝置」。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-115">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [https://go.microsoft.com/fwlink/p/?LinkId=268537](https://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="d5c4b-116"> (類比裝置在 Lync server 2013 中的運作方式與 Lync Server 2010 中相同。 ) </span><span class="sxs-lookup"><span data-stu-id="d5c4b-116">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d5c4b-117">您可以為增強型 9-1-1 (E9-1-1) 設定參數，如果切換器支援此功能。</span><span class="sxs-lookup"><span data-stu-id="d5c4b-117">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

