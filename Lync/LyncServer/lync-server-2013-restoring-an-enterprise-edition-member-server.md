---
title: Lync Server 2013： 還原 Enterprise Edition 成員伺服器
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
ms.openlocfilehash: e48af9dd5b35676ee0141b771f8e50e1fbdedae6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="12bc4-102">還原 Lync Server 2013 Enterprise Edition 成員伺服器</span><span class="sxs-lookup"><span data-stu-id="12bc4-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12bc4-103">_**上次修改主題：** 2013年-02-18_</span><span class="sxs-lookup"><span data-stu-id="12bc4-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="12bc4-104">如果執行下列其中一個下列伺服器角色失敗的伺服器，請遵循本主題將伺服器還原程序。</span><span class="sxs-lookup"><span data-stu-id="12bc4-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="12bc4-105">如果有多部伺服器個別失敗了，請針對各伺服器遵循程序進行。</span><span class="sxs-lookup"><span data-stu-id="12bc4-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="12bc4-106">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="12bc4-106">Front End Server</span></span>

  - <span data-ttu-id="12bc4-107">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="12bc4-107">Mediation Server</span></span>

  - <span data-ttu-id="12bc4-108">Director</span><span class="sxs-lookup"><span data-stu-id="12bc4-108">Director</span></span>

  - <span data-ttu-id="12bc4-109">常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="12bc4-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="12bc4-110">Edge Server</span><span class="sxs-lookup"><span data-stu-id="12bc4-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="12bc4-111">我們建議您採取系統映像複本，再開始還原。</span><span class="sxs-lookup"><span data-stu-id="12bc4-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="12bc4-112">在以免還原期間，您可以使用做為回復點，如此圖所示。</span><span class="sxs-lookup"><span data-stu-id="12bc4-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="12bc4-113">您可能要花映像複本之後安裝作業系統和 SQL Server，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="12bc4-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="12bc4-114">還原成員伺服器</span><span class="sxs-lookup"><span data-stu-id="12bc4-114">To restore a member server</span></span>

1.  <span data-ttu-id="12bc4-115">開頭為失敗的伺服器具有相同的完整的網域名稱 (FQDN) 的乾淨或全新伺服器、 安裝作業系統，並再還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="12bc4-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="12bc4-116">遵循貴組織的伺服器部署程序執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="12bc4-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="12bc4-117">使用 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="12bc4-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="12bc4-118">瀏覽至 [Lync Server 安裝資料夾或媒體，並啟動 Lync Server 部署精靈位於\\安裝\\amd64\\Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="12bc4-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="12bc4-119">遵循 [部署精靈] 的指示執行下列作業：</span><span class="sxs-lookup"><span data-stu-id="12bc4-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="12bc4-120">執行 [步驟 1: 安裝本機組態存放區]\*\*\*\*，以安裝本機設定檔。</span><span class="sxs-lookup"><span data-stu-id="12bc4-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="12bc4-121">執行**步驟 2： 安裝或移除 Lync Server 元件**安裝 Lync Server 伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="12bc4-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="12bc4-122">執行 [步驟 3: 要求、安裝或指派憑證]\*\*\*\*，以指派憑證。</span><span class="sxs-lookup"><span data-stu-id="12bc4-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="12bc4-123">執行 [步驟 4: 啟動服務]\*\*\*\*，以啟動伺服器上的服務。</span><span class="sxs-lookup"><span data-stu-id="12bc4-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="12bc4-124">如需執行 [部署精靈的詳細資訊，請參閱部署文件，針對您要還原的伺服器角色。</span><span class="sxs-lookup"><span data-stu-id="12bc4-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

