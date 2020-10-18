---
title: Lync Server 2013：還原 Enterprise Edition 成員伺服器
description: Lync Server 2013：還原 Enterprise Edition 成員伺服器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576049"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="4f18b-103">在 Lync Server 2013 中還原 Enterprise Edition 成員伺服器</span><span class="sxs-lookup"><span data-stu-id="4f18b-103">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f18b-104">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="4f18b-104">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="4f18b-105">如果執行下列其中一個伺服器角色的伺服器失敗，請遵循本主題中的程式來還原伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f18b-105">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="4f18b-106">如果有多部伺服器個別失敗了，請針對各伺服器遵循程序進行。</span><span class="sxs-lookup"><span data-stu-id="4f18b-106">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="4f18b-107">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="4f18b-107">Front End Server</span></span>

  - <span data-ttu-id="4f18b-108">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="4f18b-108">Mediation Server</span></span>

  - <span data-ttu-id="4f18b-109">Director</span><span class="sxs-lookup"><span data-stu-id="4f18b-109">Director</span></span>

  - <span data-ttu-id="4f18b-110">常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="4f18b-110">Persistent Chat Server</span></span>

  - <span data-ttu-id="4f18b-111">Edge Server</span><span class="sxs-lookup"><span data-stu-id="4f18b-111">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4f18b-112">建議您先取得系統的影像複本，再開始還原。</span><span class="sxs-lookup"><span data-stu-id="4f18b-112">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="4f18b-113">您可以使用這個影像做為復原點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="4f18b-113">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="4f18b-114">在您安裝作業系統和 SQL Server 之後，您可能會想要使用影像副本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="4f18b-114">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="4f18b-115">還原成員伺服器</span><span class="sxs-lookup"><span data-stu-id="4f18b-115">To restore a member server</span></span>

1.  <span data-ttu-id="4f18b-116">開始使用具有相同完整功能變數名稱 (FQDN) 為失敗伺服器的全新伺服器，然後安裝作業系統，再還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="4f18b-116">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f18b-117">遵循貴組織的伺服器部署程序執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="4f18b-117">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="4f18b-118">從 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4f18b-118">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="4f18b-119">流覽至 [Lync Server 安裝] 資料夾或媒體，然後啟動位於 \\ setup amd64Setup.exe 的 Lync Server 部署嚮導 \\ \\ 。</span><span class="sxs-lookup"><span data-stu-id="4f18b-119">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="4f18b-120">遵循 [部署精靈] 的指示執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="4f18b-120">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="4f18b-121">執行 [步驟 1: 安裝本機組態存放區]\*\*\*\*，以安裝本機設定檔。</span><span class="sxs-lookup"><span data-stu-id="4f18b-121">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="4f18b-122">執行 **步驟2：安裝或移除 Lync Server 元件** ，以安裝 lync server server role。</span><span class="sxs-lookup"><span data-stu-id="4f18b-122">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="4f18b-123">執行 [步驟 3: 要求、安裝或指派憑證]\*\*\*\*，以指派憑證。</span><span class="sxs-lookup"><span data-stu-id="4f18b-123">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="4f18b-124">執行 [步驟 4: 啟動服務]\*\*\*\*，以啟動伺服器上的服務。</span><span class="sxs-lookup"><span data-stu-id="4f18b-124">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="4f18b-125">如需執行部署嚮導的詳細資訊，請參閱部署檔中您要還原的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="4f18b-125">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

