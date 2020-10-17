---
title: 升級或更新後端伺服器或 Standard Edition server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3afeee91457b2d10f506be81a146643a4598c9f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506640"
---
# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="d5947-102">在 Lync Server 2013 中升級或更新後端伺服器或 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="d5947-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d5947-103">_**主題上次修改日期：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d5947-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d5947-104">本主題說明如何在 Enterprise Edition 後端伺服器或 Standard Edition server 上安裝更新。</span><span class="sxs-lookup"><span data-stu-id="d5947-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="d5947-105">如果後端伺服器停機至少30分鐘，則使用者可能會進入復原模式。</span><span class="sxs-lookup"><span data-stu-id="d5947-105">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode.</span></span> <span data-ttu-id="d5947-106">當升級完成且後端伺服器重新連接至集區中的前端伺服器後，使用者會傳回完整功能。</span><span class="sxs-lookup"><span data-stu-id="d5947-106">When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality.</span></span> <span data-ttu-id="d5947-107">如果升級所需的時間少於30分鐘，使用者將不會受到影響。</span><span class="sxs-lookup"><span data-stu-id="d5947-107">If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="d5947-108">更新後端伺服器或 Standard Edition server</span><span class="sxs-lookup"><span data-stu-id="d5947-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="d5947-109">以 CsAdministrator 角色成員身分登入您要升級的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d5947-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="d5947-110">下載更新，並將其解壓縮至本機硬碟。</span><span class="sxs-lookup"><span data-stu-id="d5947-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="d5947-111">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d5947-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="d5947-112">停止 Lync Server 服務。</span><span class="sxs-lookup"><span data-stu-id="d5947-112">Stop Lync Server services.</span></span> <span data-ttu-id="d5947-113">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d5947-113">At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="d5947-114">停止全球資訊網服務。</span><span class="sxs-lookup"><span data-stu-id="d5947-114">Stop the World Wide Web service.</span></span> <span data-ttu-id="d5947-115">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d5947-115">At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="d5947-116">關閉所有的 Lync Server 管理命令介面視窗。</span><span class="sxs-lookup"><span data-stu-id="d5947-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="d5947-117">安裝更新。</span><span class="sxs-lookup"><span data-stu-id="d5947-117">Install the update.</span></span>

8.  <span data-ttu-id="d5947-118">啟動 Lync Server 管理命令介面：依序按一下 [ **開始**]、[ **所有程式**]、[ **Microsoft Lync server 2013**]，然後按一下 [ **Lync server 管理命令**介面]。</span><span class="sxs-lookup"><span data-stu-id="d5947-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="d5947-119">停用 Lync Server 服務以捕獲通用群組件快取 (GAC) – d 元件。</span><span class="sxs-lookup"><span data-stu-id="d5947-119">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies.</span></span> <span data-ttu-id="d5947-120">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d5947-120">At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="d5947-121">重新啟動全球資訊網服務。</span><span class="sxs-lookup"><span data-stu-id="d5947-121">Restart the World Wide Web service.</span></span> <span data-ttu-id="d5947-122">在命令列中輸入：</span><span class="sxs-lookup"><span data-stu-id="d5947-122">At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="d5947-123">執行下列其中一項，將 LyncServerUpdateInstaller.exe 所做的變更套用至 SQL Server 資料庫：</span><span class="sxs-lookup"><span data-stu-id="d5947-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="d5947-124">如果這是 Enterprise Edition 後端伺服器，且此伺服器上沒有組合資料庫（例如封存或監控資料庫），請在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5947-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="d5947-125">如果這是 Enterprise Edition 後端伺服器，且此伺服器上有組合資料庫，請在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5947-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="d5947-126">如果這是 Standard Edition server，請在命令列輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="d5947-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

