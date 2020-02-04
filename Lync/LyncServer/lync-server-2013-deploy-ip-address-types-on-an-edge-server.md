---
title: Lync Server 2013：在 Edge Server 上部署 IP 位址類型
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy IP address types on an Edge Server
ms:assetid: 6e2fe7e8-6e90-4d1a-8fc5-e3be92c46571
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204984(v=OCS.15)
ms:contentKeyID: 48184435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ece4b55f42958916876539f05b951e862e0d493f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="a23f1-102">針對 Lync Server 2013 在 Edge Server 上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="a23f1-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a23f1-103">_**主題上次修改日期：** 2012-06-14_</span><span class="sxs-lookup"><span data-stu-id="a23f1-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="a23f1-104">使用拓撲建立器，執行下列程式中的步驟，在 Edge 伺服器上部署 IP 位址類型。</span><span class="sxs-lookup"><span data-stu-id="a23f1-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="a23f1-105">在邊緣伺服器上部署 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="a23f1-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="a23f1-106">在 [拓撲建立器] 的 [**邊緣池**] 底下，以滑鼠右鍵按一下池中的伺服器，然後選取 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="a23f1-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="a23f1-107">（或者，選取伺服器，然後從 [**動作**] 功能表按一下 [**編輯屬性**]。）</span><span class="sxs-lookup"><span data-stu-id="a23f1-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="a23f1-108">在 [**編輯屬性**] 視窗中，選取您要支援的 IP 位址設定。</span><span class="sxs-lookup"><span data-stu-id="a23f1-108">In the **Edit Properties** window, select the IP address configuration that you want to support.</span></span> <span data-ttu-id="a23f1-109">下圖顯示內部介面與外部介面的雙堆疊設定。</span><span class="sxs-lookup"><span data-stu-id="a23f1-109">The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="a23f1-110">**雙堆疊邊緣伺服器內部介面**</span><span class="sxs-lookup"><span data-stu-id="a23f1-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="a23f1-111">![[Lync Server 一般內容] 頁面](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "[Lync Server 一般內容] 頁面")</span><span class="sxs-lookup"><span data-stu-id="a23f1-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="a23f1-112">**雙堆疊邊緣伺服器外部介面**</span><span class="sxs-lookup"><span data-stu-id="a23f1-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="a23f1-113">![[Lync Server 下一個躍點/外部組態] 頁面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "[Lync Server 下一個躍點/外部組態] 頁面")</span><span class="sxs-lookup"><span data-stu-id="a23f1-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="a23f1-114">針對您選取的每個網址類別型，您必須提供適當的內部和外部地址。</span><span class="sxs-lookup"><span data-stu-id="a23f1-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

