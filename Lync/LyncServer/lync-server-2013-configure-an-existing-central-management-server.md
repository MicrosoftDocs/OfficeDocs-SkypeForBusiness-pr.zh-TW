---
title: Lync Server 2013：設定現有的中央管理伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an existing Central Management Server
ms:assetid: d715b24a-1256-4a7c-a5ef-1cee41d6b733
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205315(v=OCS.15)
ms:contentKeyID: 48185584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eec9193d8c40a26179c5dfe1f142740abdda8bc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-existing-central-management-server-in-lync-server-2013"></a><span data-ttu-id="92bef-102">在 Lync Server 2013 中設定現有的中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="92bef-102">Configure an existing Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92bef-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="92bef-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="92bef-104">如果您重複使用現有 Lync Server 2013 部署的中央管理伺服器，您必須執行以下所述的程式，以確保 Lync Server 控制台和 Windows PowerShell 正常運作。</span><span class="sxs-lookup"><span data-stu-id="92bef-104">If you reuse a Central Management Server from an existing Lync Server 2013 deployment, you must run the procedure described below to make sure that Lync Server Control Panel and Windows PowerShell function correctly.</span></span>

<div>

## <a name="to-configure-an-existing-central-management-server"></a><span data-ttu-id="92bef-105">若要設定現有的中央管理伺服器</span><span class="sxs-lookup"><span data-stu-id="92bef-105">To configure an existing Central Management Server</span></span>

1.  <span data-ttu-id="92bef-106">啟動 Lync Server 管理命令介面：按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="92bef-106">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="92bef-107">使用**CsAdminRole** Cmdlet 來更新儲存在中央管理伺服器的角色式存取控制（RBAC）角色。</span><span class="sxs-lookup"><span data-stu-id="92bef-107">Use the **Update-CsAdminRole** cmdlet to update the role-based access control (RBAC) roles stored in the Central Management Server.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="92bef-108">除非出現錯誤，否則不會出現任何輸出。</span><span class="sxs-lookup"><span data-stu-id="92bef-108">No output is expected unless there is an error.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

