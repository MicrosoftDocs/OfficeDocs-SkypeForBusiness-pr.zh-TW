---
title: Lync Server 2013：設定現有的中央管理伺服器
description: Lync Server 2013：設定現有的中央管理伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef93281be2537ca5e4a5892a8617500ce54f3c45
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546709"
---
# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="f22f2-103">在 Lync Server 2013 中設定現有的中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="f22f2-103">Configure an existing Central Management Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f22f2-104">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f22f2-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f22f2-105">如果您從現有的 Lync Server 2013 部署重用中央管理伺服器，則必須執行下列所述的程式，以確保 Lync Server 控制台和 Windows PowerShell 正常運作。</span><span class="sxs-lookup"><span data-stu-id="f22f2-105">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="f22f2-106">設定現有的中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="f22f2-106">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="f22f2-107">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="f22f2-107">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f22f2-108">使用 **Update-CsAdminRole** Cmdlet 來更新儲存在中央管理伺服器中的角色型存取控制 (RBAC) 角色。</span><span class="sxs-lookup"><span data-stu-id="f22f2-108">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f22f2-109">除非發生錯誤，否則不會輸出。</span><span class="sxs-lookup"><span data-stu-id="f22f2-109">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

