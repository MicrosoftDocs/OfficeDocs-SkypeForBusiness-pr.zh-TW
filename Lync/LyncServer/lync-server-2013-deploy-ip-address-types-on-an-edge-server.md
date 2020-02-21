---
title: Lync Server 2013： 部署 Edge Server 上的 IP 位址類型
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
ms.openlocfilehash: 400a7ab688b3fae4c7bded753341d4d04d0fd835
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-ip-address-types-on-an-edge-server-for-lync-server-2013"></a><span data-ttu-id="904db-102">部署 Lync Server 2013 Edge Server 上的 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="904db-102">Deploy IP address types on an Edge Server for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="904db-103">_**主題上次修改日期：** 2012年-06-14_</span><span class="sxs-lookup"><span data-stu-id="904db-103">_**Topic Last Modified:** 2012-06-14_</span></span>

<span data-ttu-id="904db-104">使用拓撲產生器，請執行下列程序部署 Edge Server 上的 IP 位址類型中的步驟。</span><span class="sxs-lookup"><span data-stu-id="904db-104">Using Topology Builder, perform the steps in the following procedure to deploy IP address types on an Edge Server.</span></span>

<div>

## <a name="to-deploy-ip-address-types-on-an-edge-server"></a><span data-ttu-id="904db-105">部署 Edge Server 上的 IP 位址類型</span><span class="sxs-lookup"><span data-stu-id="904db-105">To deploy IP address types on an Edge Server</span></span>

1.  <span data-ttu-id="904db-106">在拓撲產生器] 中 [ **Edge 集區]**，以滑鼠右鍵按一下集區中的伺服器，然後選取 [**編輯屬性**。</span><span class="sxs-lookup"><span data-stu-id="904db-106">In Topology Builder, under **Edge pools**, right-click the server within a pool, and then select **Edit Properties**.</span></span> <span data-ttu-id="904db-107">（或者，選取伺服器，並再從 [**動作**] 功能表中按一下 [**編輯內容**。）</span><span class="sxs-lookup"><span data-stu-id="904db-107">(Alternatively, select the server, and then click **Edit Properties** from the **Action** menu.)</span></span>

2.  <span data-ttu-id="904db-p102">在 **[編輯內容]** 視窗中，選取您要支援的 IP 位址設定。下列圖例展示內部介面與外部介面的雙重堆疊設定。</span><span class="sxs-lookup"><span data-stu-id="904db-p102">In the **Edit Properties** window, select the IP address configuration that you want to support. The following figures show a dual stack configuration for the internal interface and the external interface.</span></span>
    
    <span data-ttu-id="904db-110">**雙重堆疊的 Edge Server 內部介面**</span><span class="sxs-lookup"><span data-stu-id="904db-110">**Dual stacked Edge Server internal interface**</span></span>
    
    <span data-ttu-id="904db-111">![Lync Server 一般內容] 頁面](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server 一般內容] 頁面")</span><span class="sxs-lookup"><span data-stu-id="904db-111">![Lync Server general properties page](images/JJ204984.5b0883ee-b9f2-4a21-91a9-3286d0beb63b(OCS.15).png "Lync Server general properties page")</span></span>
    
    <span data-ttu-id="904db-112">**雙重堆疊的 Edge Server 外部介面**</span><span class="sxs-lookup"><span data-stu-id="904db-112">**Dual stacked Edge Server external interface**</span></span>
    
    <span data-ttu-id="904db-113">![Lync Server 下一個躍點/外部設定] 頁面](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server 下一個躍點/外部設定] 頁面")</span><span class="sxs-lookup"><span data-stu-id="904db-113">![Lync Server next hop/external configuration page](images/JJ204984.2aa00ce2-ba50-40aa-bbf1-78636016daf9(OCS.15).png "Lync Server next hop/external configuration page")</span></span>

3.  <span data-ttu-id="904db-114">您必須針對所選取的每個位址類型提供適當的內部及外部位址。</span><span class="sxs-lookup"><span data-stu-id="904db-114">For each address type that you select, you must supply appropriate internal and external addresses.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

