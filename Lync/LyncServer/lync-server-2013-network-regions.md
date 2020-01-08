---
title: Lync Server 2013：網路區域
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9a2fd8ce5de11f592d010615ddee9c253913c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="9015a-102">Lync Server 2013 的網路區域</span><span class="sxs-lookup"><span data-stu-id="9015a-102">Network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9015a-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9015a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9015a-104">*網路區域*是網路中樞或 backbones，用於設定通話許可控制、E9-1 及媒體旁路。</span><span class="sxs-lookup"><span data-stu-id="9015a-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="9015a-105">使用下列程式來查看、建立或修改網路區。</span><span class="sxs-lookup"><span data-stu-id="9015a-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="9015a-106">例如，如果您已為單一語音功能建立網路區域，就不需要建立新的網路區域;其他高級企業語音功能將會使用相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="9015a-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="9015a-107">不過，您可能需要修改現有的網路區域定義，才能套用特定功能的設定。</span><span class="sxs-lookup"><span data-stu-id="9015a-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="9015a-108">例如，如果您已建立 E9 的網路區域（不需要關聯的中央網站），而您想要部署 [呼叫許可控制]，您必須修改網路區域定義，以指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="9015a-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="9015a-109">如需詳細資訊，請參閱[在 Lync Server 2013 中設定 CAC 的網路區域](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="9015a-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9015a-110">此功能的部署主題中記錄了網路區域定義的任何特定功能需求。</span><span class="sxs-lookup"><span data-stu-id="9015a-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="9015a-111">本節內容</span><span class="sxs-lookup"><span data-stu-id="9015a-111">In This Section</span></span>

  - [<span data-ttu-id="9015a-112">在 Lync Server 2013 中查看網路區域資訊</span><span class="sxs-lookup"><span data-stu-id="9015a-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="9015a-113">在 Lync Server 2013 中建立或修改網路區域</span><span class="sxs-lookup"><span data-stu-id="9015a-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="9015a-114">在 Lync Server 2013 中刪除現有的網路區域</span><span class="sxs-lookup"><span data-stu-id="9015a-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="9015a-115">參考</span><span class="sxs-lookup"><span data-stu-id="9015a-115">Reference</span></span>

[<span data-ttu-id="9015a-116">在 Lync Server 2013 中部署高級企業語音功能</span><span class="sxs-lookup"><span data-stu-id="9015a-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

