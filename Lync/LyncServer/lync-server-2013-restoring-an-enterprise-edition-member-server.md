---
title: Lync Server 2013：還原企業版成員伺服器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83f0283dc6525dbb75ce74809bd88f4e962a9aec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a><span data-ttu-id="974c3-102">在 Lync Server 2013 中還原企業版成員伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-102">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="974c3-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="974c3-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="974c3-104">如果執行下列其中一個伺服器角色的伺服器失敗，請遵循本主題中的程式來還原伺服器。</span><span class="sxs-lookup"><span data-stu-id="974c3-104">If a server running one of the following server roles fails, follow the procedure in this topic to restore the server.</span></span> <span data-ttu-id="974c3-105">如果多個伺服器獨立失敗，請依照每個伺服器的程式執行。</span><span class="sxs-lookup"><span data-stu-id="974c3-105">If multiple servers fail independently, follow the procedure for each server.</span></span>

  - <span data-ttu-id="974c3-106">前端伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-106">Front End Server</span></span>

  - <span data-ttu-id="974c3-107">中繼伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-107">Mediation Server</span></span>

  - <span data-ttu-id="974c3-108">Director</span><span class="sxs-lookup"><span data-stu-id="974c3-108">Director</span></span>

  - <span data-ttu-id="974c3-109">常設聊天室伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-109">Persistent Chat Server</span></span>

  - <span data-ttu-id="974c3-110">Edge 伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-110">Edge Server</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="974c3-111">我們建議您先取得系統的影像複本，然後再開始還原。</span><span class="sxs-lookup"><span data-stu-id="974c3-111">We recommend that you take an image copy of the system before you start restoration.</span></span> <span data-ttu-id="974c3-112">您可以使用這個影像做為復原點，以防還原期間發生的問題。</span><span class="sxs-lookup"><span data-stu-id="974c3-112">You can use this image as a rollback point, in case something goes wrong during restoration.</span></span> <span data-ttu-id="974c3-113">您可能會想要在安裝作業系統與 SQL Server 之後拍攝影像複本，並還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="974c3-113">You might want to take the image copy after you install the operating system and SQL Server, and restore or reenroll the certificates.</span></span>



</div>

<div>

## <a name="to-restore-a-member-server"></a><span data-ttu-id="974c3-114">若要還原成員伺服器</span><span class="sxs-lookup"><span data-stu-id="974c3-114">To restore a member server</span></span>

1.  <span data-ttu-id="974c3-115">從有與失敗伺服器相同的完整功能變數名稱（FQDN）開始，清除或新伺服器，安裝作業系統，然後還原或重新註冊證書。</span><span class="sxs-lookup"><span data-stu-id="974c3-115">Start with a clean or new server that has the same fully qualified domain name (FQDN) as the failed server, install the operating system, and then restore or reenroll the certificates.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="974c3-116">遵循貴組織的伺服器部署程式來執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="974c3-116">Follow your organization's server deployment procedures to perform this step.</span></span>

    
    </div>

2.  <span data-ttu-id="974c3-117">從是 RTCUniversalServerAdmins 群組成員的使用者帳戶，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="974c3-117">From a user account that is a member of the RTCUniversalServerAdmins group, log on to the server that you are restoring.</span></span>

3.  <span data-ttu-id="974c3-118">流覽至 Lync Server 安裝資料夾或媒體，然後啟動位於\\安裝程式\\Amd64\\setup.exe 的 lync server 部署嚮導。</span><span class="sxs-lookup"><span data-stu-id="974c3-118">Browse to the Lync Server installation folder or media, and start the Lync Server Deployment Wizard located at \\setup\\amd64\\Setup.exe.</span></span>

4.  <span data-ttu-id="974c3-119">遵循 [部署嚮導] 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="974c3-119">Follow the Deployment Wizard to do the following:</span></span>
    
    1.  <span data-ttu-id="974c3-120">執行**步驟1：安裝本機配置存放區**以安裝本機配置檔案。</span><span class="sxs-lookup"><span data-stu-id="974c3-120">Run **Step 1: Install Local Configuration Store** to install the local configuration files.</span></span>
    
    2.  <span data-ttu-id="974c3-121">執行**步驟2：設定或移除 Lync Server 元件**以安裝 lync server server 角色。</span><span class="sxs-lookup"><span data-stu-id="974c3-121">Run **Step 2: Setup or Remove Lync Server Components** to install the Lync Server server role.</span></span>
    
    3.  <span data-ttu-id="974c3-122">執行**步驟3：要求、安裝或指派憑證**來指派憑證。</span><span class="sxs-lookup"><span data-stu-id="974c3-122">Run **Step 3: Request, Install or Assign Certificates** to assign the certificates.</span></span>
    
    4.  <span data-ttu-id="974c3-123">執行**步驟4：啟動服務**以在伺服器上啟動服務。</span><span class="sxs-lookup"><span data-stu-id="974c3-123">Run **Step 4: Start Services** to start services on the server.</span></span>
    
    <span data-ttu-id="974c3-124">如需執行 [部署嚮導] 的詳細資訊，請參閱您要還原之伺服器角色的部署檔。</span><span class="sxs-lookup"><span data-stu-id="974c3-124">For details about running the Deployment Wizard, see the Deployment documentation for the server role that you are restoring.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

