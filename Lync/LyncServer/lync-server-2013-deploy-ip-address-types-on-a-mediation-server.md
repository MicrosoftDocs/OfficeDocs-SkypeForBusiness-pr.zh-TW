---
title: Lync Server 2013：在中繼伺服器上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on a Mediation Server
ms:assetid: 689ebed5-96ee-4cd4-b7ae-ee2a86a1d9b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204964(v=OCS.15)
ms:contentKeyID: 48184376
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab30a2153dc7dbf5a15557f6eeaf3b6cb65f68f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-a-mediation-server-for-lync-server-2013"></a><span data-ttu-id="3fc2a-102">針對 Lync Server 2013 在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="3fc2a-102">Deploy IP address types on a Mediation Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3fc2a-103">_**主題上次修改日期：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="3fc2a-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="3fc2a-104">使用拓撲建立器，執行下列程式中的步驟，在中繼伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on a Mediation Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-a-mediation-server"></a><span data-ttu-id="3fc2a-105">在中繼伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="3fc2a-105">To deploy IP address types on a Mediation Server</span></span>

  - <span data-ttu-id="3fc2a-106">在拓撲建立器中，在 [**轉送器池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-106">In Topology Builder, under **Mediation pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="3fc2a-107">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="3fc2a-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

  - <span data-ttu-id="3fc2a-108">在 [**編輯屬性**] 對話方塊中，選取您要設定的 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-108">In the **Edit Properties** dialog box, select the IP address type that you want to configure.</span></span> <span data-ttu-id="3fc2a-109">針對雙堆疊設定，請選取 [**啟用 IPv4**並**啟用 IPv6**]，如下圖所示。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-109">For a dual-stack configuration, select **Enable IPv4** and **Enable IPv6**, as shown in the following figure.</span></span>
    
    <span data-ttu-id="3fc2a-110">**中繼伺服器池的 [編輯屬性] 對話方塊**</span><span class="sxs-lookup"><span data-stu-id="3fc2a-110">**Edit Properties dialog box for the Mediation Server pool**</span></span>
    
    <span data-ttu-id="3fc2a-111">![具有 FQDN 的 [Lync Server 一般內容] 頁面](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "具有 FQDN 的 [Lync Server 一般內容] 頁面")</span><span class="sxs-lookup"><span data-stu-id="3fc2a-111">![Lync Server general properties page with FQDN](images/JJ204964.4e650aca-dbff-4a86-b10d-f0162c032539(OCS.15).png "Lync Server general properties page with FQDN")</span></span>
    
      - <span data-ttu-id="3fc2a-112">**使用所有已設定的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-112">**Use all configured IP addresses**.</span></span> <span data-ttu-id="3fc2a-113">如果您想要允許使用電腦上定義的任何 IP 位址，請選取此選項。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-113">Select this option if you want to allow any IP address defined on the computer to be used.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3fc2a-114">這是 IP 版本6（IPv6）配置的建議選項。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-114">This is the recommended option for IP version 6 (IPv6) configurations.</span></span>

        
        </div>
    
      - <span data-ttu-id="3fc2a-115">**將服務使用限制在選取的 IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-115">**Limit service usage to selected IP addresses**.</span></span> <span data-ttu-id="3fc2a-116">選取此選項以指定要在新伺服器上使用的特定位址。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-116">Select this option to specify a specific address to use on the new server.</span></span> <span data-ttu-id="3fc2a-117">如果您選取此選項，您必須輸入 [主要 IP 位址] 的值。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-117">If you select this option, you must enter a value for Primary IP address.</span></span>
    
      - <span data-ttu-id="3fc2a-118">[**主要 IP 位址**]。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-118">**Primary IP address**.</span></span> <span data-ttu-id="3fc2a-119">輸入一個 IP 位址，伺服器會將它用於除公用交換電話網絡（PSTN）以外的所有通訊。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-119">Enter an IP address that the server will use for all communications except public switched telephone network (PSTN).</span></span> <span data-ttu-id="3fc2a-120">輸入的 IP 位址必須符合 [選取網址類別型] 的格式。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-120">The IP address entered must match the format of the select address type.</span></span>
    
      - <span data-ttu-id="3fc2a-121">**PSTN IP 位址**。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-121">**PSTN IP address**.</span></span> <span data-ttu-id="3fc2a-122">在中繼伺服器是獨立的情況中，定義 PSTN IP 位址。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-122">Define a PSTN IP address when a Mediation Server is standalone.</span></span> <span data-ttu-id="3fc2a-123">此位址必須符合所選網址類別型的格式。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-123">This address must match the format of the selected address type.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3fc2a-124">Collocated 中繼伺服器角色不支援安裝其他的網路介面卡（NIC） s 以支援 Lync Server 2013 的 PSTN IP 位址設定。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-124">The installation of additional network interface cards (NIC)s to support the PSTN IP address configuration for Lync Server 2013 is not supported on collocated Mediation Server roles.</span></span> <span data-ttu-id="3fc2a-125">如需 Lync Server 2013 支援的 NIC 配置的詳細資訊，請參閱<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的伺服器硬體平臺</A>。</span><span class="sxs-lookup"><span data-stu-id="3fc2a-125">For more information about supported NIC configurations for Lync Server 2013, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

