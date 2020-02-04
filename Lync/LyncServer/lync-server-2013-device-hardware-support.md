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
ms.openlocfilehash: ea720eda982ab20333e56de268085a706ab2cdc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-hardware-support-in-lync-server-2013"></a><span data-ttu-id="01aea-102">Lync Server 2013 中的裝置硬體支援</span><span class="sxs-lookup"><span data-stu-id="01aea-102">Device hardware support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="01aea-103">_**主題上次修改日期：** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="01aea-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="01aea-104">在部署 IP 電話和類比裝置之前，必須先進行特定的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="01aea-104">Specific hardware configurations must be in place before you deploy IP phones and analog devices.</span></span>

<span data-ttu-id="01aea-105">執行 Lync 手機版的 IP 電話支援連結層探索通訊協定-媒體端點探索（LLDP-MED-V）和乙太網上電（PoE）。</span><span class="sxs-lookup"><span data-stu-id="01aea-105">IP phones running Lync Phone Edition support Link Layer Discovery Protocol-Media Endpoint Discovery (LLDP-MED) and Power over Ethernet (PoE).</span></span><span data-ttu-id="01aea-106">若要充分利用 LLDP-MED-V，交換器必須支援 IEEE 802.1 AB 和 ANSI/TIA-1057。</span><span class="sxs-lookup"><span data-stu-id="01aea-106"> To take advantage of LLDP-MED, the switch must support IEEE802.1AB and ANSI/TIA-1057.</span></span> <span data-ttu-id="01aea-107">若要充分利用 PoE，交換器必須支援 PoE 802.3 AF 或 802.3 at。</span><span class="sxs-lookup"><span data-stu-id="01aea-107">To take advantage of PoE, the switch must support PoE802.3AF or 802.3at.</span></span>

<span data-ttu-id="01aea-108">若要啟用 LLDP，系統管理員必須使用 [切換主控台] 視窗來啟用 LLDP，並使用正確的語音 VLAN 識別碼設定 LLDP-MED-V 網路原則。</span><span class="sxs-lookup"><span data-stu-id="01aea-108">To enable LLDP-MED, the administrator must enable LLDP by using the switch console window and set the LLDP-MED network policy with the correct voice VLAN ID.</span></span>

<span data-ttu-id="01aea-109">此外，如果您的部署包含類比裝置，您必須將模擬閘道設定為使用 Lync Server，且閘道必須是下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="01aea-109">In addition, if your deployment includes analog devices, you must configure the analog gateway to use Lync Server, and the gateway must be one of the following:</span></span>

  - <span data-ttu-id="01aea-110">類比電話配接器（ATA）</span><span class="sxs-lookup"><span data-stu-id="01aea-110">An analog telephone adapter (ATA)</span></span>

  - <span data-ttu-id="01aea-111">PSTN 類比閘道</span><span class="sxs-lookup"><span data-stu-id="01aea-111">A PSTN analog gateway</span></span>

  - <span data-ttu-id="01aea-112">包含 PSTN 模擬閘道的 Survivable 分支裝置</span><span class="sxs-lookup"><span data-stu-id="01aea-112">A Survivable Branch Appliance that includes a PSTN analog gateway</span></span>

  - <span data-ttu-id="01aea-113">Survivable 分支裝置，其中包含可與 ATA 通訊的 PSTN 閘道</span><span class="sxs-lookup"><span data-stu-id="01aea-113">A Survivable Branch Appliance that includes a PSTN gateway that communicates with an ATA</span></span>

<span data-ttu-id="01aea-114">若要瞭解如何設定類比閘道，請參閱 Lync Server 2010 TechNet 文件庫[http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537)中的「規劃以部署類比裝置」。</span><span class="sxs-lookup"><span data-stu-id="01aea-114">To learn how to configure an analog gateway, see "Planning to Deploy Analog Devices" at [http://go.microsoft.com/fwlink/p/?LinkId=268537](http://go.microsoft.com/fwlink/p/?linkid=268537) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="01aea-115">（類比裝置在 lync server 2013 中的運作方式與在 Lync Server 2010 中一樣。）</span><span class="sxs-lookup"><span data-stu-id="01aea-115">(Analog devices work the same way in Lync Server 2013 as they do in Lync Server 2010.)</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="01aea-116">如果交換器支援此功能，您可以將開關設定為增強9-1-1 （E9-1-1）。</span><span class="sxs-lookup"><span data-stu-id="01aea-116">You can configure the switch for Enhanced 9-1-1 (E9-1-1), if the switch supports this.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

