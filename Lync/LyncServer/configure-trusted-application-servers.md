---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cab126429fc5ec77a2308fdc1e1f8965fdfccb5b
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/07/2019
ms.locfileid: "40977577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="83c4d-102">設定信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="83c4d-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83c4d-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="83c4d-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="83c4d-104">在混合式環境中，如果您建立新的受信任的應用程式伺服器，您必須將下一個躍點池設定為 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="83c4d-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="83c4d-105">在混合式環境中，舊版 Lync Server 2010 池和 Lync Server 2013 池都會出現在下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="83c4d-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="83c4d-106">不支援選取舊版池。</span><span class="sxs-lookup"><span data-stu-id="83c4d-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="83c4d-107">**在建立信任的應用程式伺服器時，選取 Lync Server 2013 做為下一個躍點**</span><span class="sxs-lookup"><span data-stu-id="83c4d-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="83c4d-108">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="83c4d-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="83c4d-109">在左窗格中，以滑鼠右鍵按一下 [**受信任的應用程式伺服器**]，然後按一下 [**新增信任的應用程式**</span><span class="sxs-lookup"><span data-stu-id="83c4d-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="83c4d-110">輸入受信任的應用程式池的 [**池 FQDN** ]，然後選取它將是單一伺服器或多重伺服器。</span><span class="sxs-lookup"><span data-stu-id="83c4d-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="83c4d-111">按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="83c4d-111">Click **Next**.</span></span>

5.  <span data-ttu-id="83c4d-112">在 [**選取下一個躍點]** 頁面上的清單中，選取 [Lync Server 2013 前端] 池。</span><span class="sxs-lookup"><span data-stu-id="83c4d-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="83c4d-113">按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="83c4d-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="83c4d-114">選取頂端節點**Lync Server** ，然後從 [**動作**] 功能表選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="83c4d-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="83c4d-115">確認**信任的應用程式池**已順利建立，且與正確的前端池相關聯。</span><span class="sxs-lookup"><span data-stu-id="83c4d-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

