---
title: 重設通話許可控制
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cf7067ba3d130c264ead39ed9d2c044a037960f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="103f4-102">重設通話許可控制</span><span class="sxs-lookup"><span data-stu-id="103f4-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="103f4-103">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="103f4-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="103f4-104">如果 Lync Server 2010 前端池是託管呼叫許可控制（CAC），您必須先將 CAC 主機託管到 Lync Server 2013 池，才能移除 Lync Server 2010 前端池。</span><span class="sxs-lookup"><span data-stu-id="103f4-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="103f4-105">若要重設 CAC</span><span class="sxs-lookup"><span data-stu-id="103f4-105">To reset CAC</span></span>

1.  <span data-ttu-id="103f4-106">開啟拓撲建立器。</span><span class="sxs-lookup"><span data-stu-id="103f4-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="103f4-107">以滑鼠右鍵按一下網站節點，然後按一下 [**編輯屬性**]。</span><span class="sxs-lookup"><span data-stu-id="103f4-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="103f4-108">在 [**呼叫許可控制設定**] 底下，請確認已選取 [**啟用撥號許可控制**]。</span><span class="sxs-lookup"><span data-stu-id="103f4-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="103f4-109">在 [前端池] 底下，**若要執行 [呼叫許可控制] （CAC）**，請選取要裝載 CAC 的 Lync Server 2013 池，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="103f4-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="103f4-110">發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="103f4-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

