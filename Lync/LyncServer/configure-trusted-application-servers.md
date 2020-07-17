---
title: 設定信任的應用程式伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure trusted application servers
ms:assetid: 20c3815f-3048-4940-8c0f-cdfcd0801d5d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204735(v=OCS.15)
ms:contentKeyID: 48183592
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb71833e782378f0d959fcbfcf5647235252e594
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-trusted-application-servers"></a><span data-ttu-id="59c9f-102">設定信任的應用程式伺服器</span><span class="sxs-lookup"><span data-stu-id="59c9f-102">Configure trusted application servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59c9f-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="59c9f-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="59c9f-104">在混合環境中，如果您建立新的受信任應用程式伺服器，則必須將下一個躍點集區設定為 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="59c9f-104">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Lync Server 2013 pool.</span></span> <span data-ttu-id="59c9f-105">在混合環境中，舊的 Lync Server 2010 集區和 Lync Server 2013 集區會出現在下拉式清單中。</span><span class="sxs-lookup"><span data-stu-id="59c9f-105">In a mixed environment, both the legacy Lync Server 2010 pool and the Lync Server 2013 pool appear in the drop down list.</span></span> <span data-ttu-id="59c9f-106">但不支援選取舊版集區。</span><span class="sxs-lookup"><span data-stu-id="59c9f-106">Selecting the legacy pool is not supported.</span></span>

<span data-ttu-id="59c9f-107">**在建立信任的應用程式伺服器時，選取 [Lync Server 2013] 做為下一個躍點**</span><span class="sxs-lookup"><span data-stu-id="59c9f-107">**Select Lync Server 2013 as next hop when creating a Trusted application server**</span></span>

1.  <span data-ttu-id="59c9f-108">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="59c9f-108">Open Topology Builder.</span></span>

2.  <span data-ttu-id="59c9f-109">在左側窗格中，用滑鼠右鍵按一下 **[信任的應用程式伺服器]**，然後按一下 **[新增信任的應用程式集區]**。</span><span class="sxs-lookup"><span data-stu-id="59c9f-109">In the left pane, right click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>

3.  <span data-ttu-id="59c9f-110">輸入信任的應用程式集區的 [**集區 FQDN** ]，並選取其將為單一伺服器或多部伺服器。</span><span class="sxs-lookup"><span data-stu-id="59c9f-110">Enter the **Pool FQDN** of the trusted application pool and select whether it will be a single-server or multiple-server.</span></span>

4.  <span data-ttu-id="59c9f-111">按 [下一步]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59c9f-111">Click **Next**.</span></span>

5.  <span data-ttu-id="59c9f-112">在 [**選取下一個躍點]** 頁面上，從清單中選取 [Lync Server 2013 前端集區]。</span><span class="sxs-lookup"><span data-stu-id="59c9f-112">On the **Select the next hop** page, from the list, select the Lync Server 2013 Front End pool.</span></span>

6.  <span data-ttu-id="59c9f-113">按一下 [完成]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="59c9f-113">Click **Finish**.</span></span>

7.  <span data-ttu-id="59c9f-114">選取頂端節點 [ **Lync Server** ]，然後從 [**動作**] 功能表中選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="59c9f-114">Select the top node **Lync Server** and from the **Action** menu, select **Publish**.</span></span>
    
    <span data-ttu-id="59c9f-115">確認已成功建立**信任的應用程式集**區，且該集區與正確的前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="59c9f-115">Verify the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

