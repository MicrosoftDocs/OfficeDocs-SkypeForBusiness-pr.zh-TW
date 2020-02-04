---
title: Lync Server 2013：在前端伺服器上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Front End Server
ms:assetid: b6c8e0f9-ec8e-4a4e-a525-756f9cd6b9d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205191(v=OCS.15)
ms:contentKeyID: 48185193
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f70ff3098f11cbb3d3b04602dca9c12a4998a367
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-front-end-server-for-lync-server-2013"></a><span data-ttu-id="cbf0b-102">針對 Lync Server 2013 在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="cbf0b-102">Deploy IP address types on a Front End Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbf0b-103">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="cbf0b-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="cbf0b-104">使用拓撲建立器，執行下列程式中的步驟，在前端伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Front End Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-front-end-server"></a><span data-ttu-id="cbf0b-105">在前端伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="cbf0b-105">To deploy IP address types on a Front End Server</span></span>

1.  <span data-ttu-id="cbf0b-106">在 [**企業版頂層端池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-106">Under **Enterprise Edition Front End pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="cbf0b-107">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="cbf0b-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="cbf0b-108">在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="cbf0b-109">針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="cbf0b-110">**前端伺服器池的 [編輯屬性] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="cbf0b-110">**Edit Properties dialog box for the Front End Server pool**</span></span>
    
    <span data-ttu-id="cbf0b-111">![[前端伺服器編輯內容] 對話方塊](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "[前端伺服器編輯內容] 對話方塊")</span><span class="sxs-lookup"><span data-stu-id="cbf0b-111">![Front End Server Edit Properties dialog box](images/JJ205191.737a9d71-c0bc-4a54-9608-9e028dacc814(OCS.15).png "Front End Server Edit Properties dialog box")</span></span>
    
      - <span data-ttu-id="cbf0b-112">**使用所有已設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="cbf0b-113">如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="cbf0b-114">這是 IP 版本6（IPv6）配置的建議選項。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="cbf0b-115">**將服務使用限制在選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="cbf0b-116">選取此選項以指定要在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="cbf0b-117">如果您選取此選項，您必須輸入 [**主要 IP 位址**] 的值。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-117">If you select this option, you must enter a value for **Primary IP address**.</span></span>
    
      - <span data-ttu-id="cbf0b-118">[**主要 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-118">**Primary IP address**.</span></span> <span data-ttu-id="cbf0b-119">輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="cbf0b-120">輸入的 IP 位址必須符合 [選取網址類別型] 的格式。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="cbf0b-121">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-121">**PSTN IP address**.</span></span> <span data-ttu-id="cbf0b-122">Collocated 中繼伺服器角色不支援安裝其他的網路介面卡（NIC） s 以支援 Lync Server 2013 的 PSTN IP 位址設定。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-122">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="cbf0b-123">如需 Lync Server 2013 支援的 NIC 配置的詳細資訊，請參閱[Lync server 2013 的伺服器硬體平臺](lync-server-2013-server-hardware-platforms.md)。</span><span class="sxs-lookup"><span data-stu-id="cbf0b-123">For more information about supported NIC configurations for Lync Server 2013, see [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

