---
title: Lync Server 2013：網路地區
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Network regions
ms:assetid: 1818e9d2-bbb7-420a-93ea-4c3da3a55ad3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687979(v=OCS.15)
ms:contentKeyID: 49733567
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 541beafe32dcfbe830573ae5954f81ee7febe8de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48505490"
---
# <a name="network-regions-in-lync-server-2013"></a><span data-ttu-id="ad365-102">Lync Server 2013 中的網路地區</span><span class="sxs-lookup"><span data-stu-id="ad365-102">Network regions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad365-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="ad365-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="ad365-104">「網路區域」\*\* 是用於通話許可控制、E9-1-1 及媒體旁路設定的網路中樞或骨幹。</span><span class="sxs-lookup"><span data-stu-id="ad365-104">*Network regions* are the network hubs or backbones used in the configuration of call admission control, E9-1-1, and media bypass.</span></span> <span data-ttu-id="ad365-105">使用下列程序可以檢視、建立或修改網路區域。</span><span class="sxs-lookup"><span data-stu-id="ad365-105">Use the following procedures to view, create, or modify network regions.</span></span> <span data-ttu-id="ad365-106">例如，您已為一個語音功能建立網路區域，便不需要建立新的網路區域；其他的進階 Enterprise Voice 功能會使用那些相同的網路區域。</span><span class="sxs-lookup"><span data-stu-id="ad365-106">For example, if you have already created network regions for one Voice feature, you do not need to create new network regions; other advanced Enterprise Voice features will use those same network regions.</span></span> <span data-ttu-id="ad365-107">不過，您必須修改現有的網路區域定義，以套用功能特定的設定。</span><span class="sxs-lookup"><span data-stu-id="ad365-107">You may, however, need to modify an existing network region definition to apply feature-specific settings.</span></span> <span data-ttu-id="ad365-108">例如，您已為 E9-1-1 (其不需要相關的中央網站) 建立網路區域，而您接著要部署通話許可控制，您便必須修改網路區域定義來指定中央網站。</span><span class="sxs-lookup"><span data-stu-id="ad365-108">For example, if you have created network regions for E9-1-1 (which do not require an associated central site) and you then deploy call admission control, you need to modify the network region definitions to specify a central site.</span></span> <span data-ttu-id="ad365-109">如需詳細資訊，請參閱 [在 Lync Server 2013 中設定 CAC 的網路地區](lync-server-2013-configure-network-regions-for-cac.md)。</span><span class="sxs-lookup"><span data-stu-id="ad365-109">For details, see [Configure network regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad365-110">網路地區定義的任何功能特定需求都記載在功能的部署主題中。</span><span class="sxs-lookup"><span data-stu-id="ad365-110">Any feature-specific requirements for network region definitions are documented in the Deployment topics for the feature.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ad365-111">本章節內容</span><span class="sxs-lookup"><span data-stu-id="ad365-111">In This Section</span></span>

  - [<span data-ttu-id="ad365-112">在 Lync Server 2013 中查看網路地區資訊</span><span class="sxs-lookup"><span data-stu-id="ad365-112">Viewing network region information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-region-information.md)

  - [<span data-ttu-id="ad365-113">在 Lync Server 2013 中建立或修改網路地區</span><span class="sxs-lookup"><span data-stu-id="ad365-113">Creating or modifying network regions in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-network-regions.md)

  - [<span data-ttu-id="ad365-114">在 Lync Server 2013 中刪除現有的網路地區</span><span class="sxs-lookup"><span data-stu-id="ad365-114">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)

</div>

<div>

## <a name="reference"></a><span data-ttu-id="ad365-115">參考</span><span class="sxs-lookup"><span data-stu-id="ad365-115">Reference</span></span>

[<span data-ttu-id="ad365-116">在 Lync Server 2013 中部署高級 Enterprise Voice 功能</span><span class="sxs-lookup"><span data-stu-id="ad365-116">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

