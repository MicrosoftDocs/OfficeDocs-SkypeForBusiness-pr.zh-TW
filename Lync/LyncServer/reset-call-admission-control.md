---
title: 重設通話許可控制
description: 重設通話許可控制。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4539cda453de6249be3a9b9b61521ecf478cb70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551239"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="4c916-103">重設通話許可控制</span><span class="sxs-lookup"><span data-stu-id="4c916-103">Reset call admission control</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c916-104">_**主題上次修改日期：** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="4c916-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="4c916-105">如果 Lync Server 2010 前端集區裝載通話許可控制 (CAC) ，您必須將 CAC 主控裝載至 Lync Server 2013 集區，才能移除 Lync Server 2010 前端集區。</span><span class="sxs-lookup"><span data-stu-id="4c916-105">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="4c916-106">重設 CAC</span><span class="sxs-lookup"><span data-stu-id="4c916-106">To reset CAC</span></span>

1.  <span data-ttu-id="4c916-107">開啟拓撲產生器。</span><span class="sxs-lookup"><span data-stu-id="4c916-107">Open Topology Builder.</span></span>

2.  <span data-ttu-id="4c916-108">以滑鼠右鍵按一下網站節點，然後按一下 **[編輯屬性]**。</span><span class="sxs-lookup"><span data-stu-id="4c916-108">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="4c916-109">在 **[通話許可控制設定]** 下方，確定已選取 **[啟用通話許可控制]**。</span><span class="sxs-lookup"><span data-stu-id="4c916-109">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="4c916-110">在 [前端集區] 下， \*\* (CAC) \*\*中，選取要裝載 CAC 的 Lync Server 2013 集區，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4c916-110">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="4c916-111">發行拓撲。</span><span class="sxs-lookup"><span data-stu-id="4c916-111">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

