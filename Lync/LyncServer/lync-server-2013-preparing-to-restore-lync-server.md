---
title: Lync Server 2013：準備還原 Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing to restore Lync Server
ms:assetid: 857e4e02-908e-433a-96c6-be1795a9cb61
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202179(v=OCS.15)
ms:contentKeyID: 51541490
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd5875dc7e0dd999a1d94e6e7722eeba07c3a37e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-to-restore-lync-server-2013"></a><span data-ttu-id="96567-102">準備還原 Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96567-102">Preparing to restore Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96567-103">_**主題上次修改日期：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="96567-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="96567-104">當您在失敗後開始還原伺服器及資料庫之前，您必須確定下列各項：</span><span class="sxs-lookup"><span data-stu-id="96567-104">Before you begin restoring servers and databases after a failure, you need to determine the following:</span></span>

  - <span data-ttu-id="96567-105">需要還原的專案。</span><span class="sxs-lookup"><span data-stu-id="96567-105">What needs to be restored.</span></span>

  - <span data-ttu-id="96567-106">還原所需的硬體、軟體、資料及工具。</span><span class="sxs-lookup"><span data-stu-id="96567-106">The hardware, software, data, and tools you need for restoration.</span></span>

<div>

## <a name="determining-what-to-restore"></a><span data-ttu-id="96567-107">決定要還原的專案</span><span class="sxs-lookup"><span data-stu-id="96567-107">Determining What to Restore</span></span>

<span data-ttu-id="96567-108">本主題說明如何還原發生在伺服器、集區或中央管理存放區層級的 Lync Server 中斷。</span><span class="sxs-lookup"><span data-stu-id="96567-108">This topic describes how to restore Lync Server outages that occur at the server, pool, or Central Management store level.</span></span> <span data-ttu-id="96567-109">若中央管理存放區失敗，您的 Lync Server 部署仍可運作，但您無法變更任何設定。</span><span class="sxs-lookup"><span data-stu-id="96567-109">If the Central Management store fails, your Lync Server deployment continues to function, but you cannot make any configuration changes.</span></span> <span data-ttu-id="96567-110">如果後端伺服器或 Standard Edition Server 失敗，使用者集區便會停止運作。</span><span class="sxs-lookup"><span data-stu-id="96567-110">If a Back End Server or Standard Edition server fails, the user pool stops functioning.</span></span> <span data-ttu-id="96567-111">如果任何其他伺服器失敗，失敗的程度取決於伺服器執行的伺服器角色，以及伺服器是否主控一或多個資料庫。</span><span class="sxs-lookup"><span data-stu-id="96567-111">If any other server fails, the magnitude of the failure depends on the server role the server is running and whether the server hosts one or more databases.</span></span>

### <a name="what-to-restore"></a><span data-ttu-id="96567-112">要還原的專案</span><span class="sxs-lookup"><span data-stu-id="96567-112">What to Restore</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96567-113">若失敗</span><span class="sxs-lookup"><span data-stu-id="96567-113">If this failed</span></span></th>
<th><span data-ttu-id="96567-114">請參閱本節內容：</span><span class="sxs-lookup"><span data-stu-id="96567-114">See this section:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96567-115">Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="96567-115">Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="96567-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">在 Lync Server 2013 中還原 Standard Edition server</a></span><span class="sxs-lookup"><span data-stu-id="96567-116"><a href="lync-server-2013-restoring-a-standard-edition-server.md">Restoring a Standard Edition server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96567-117">中央管理存放區</span><span class="sxs-lookup"><span data-stu-id="96567-117">Central Management store</span></span></p></td>
<td><p><span data-ttu-id="96567-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">在 Lync Server 2013 中還原主控中央管理存放區的伺服器</a></span><span class="sxs-lookup"><span data-stu-id="96567-118"><a href="lync-server-2013-restoring-the-server-hosting-the-central-management-store.md">Restoring the server hosting the Central Management store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96567-119">Enterprise Edition 後端</span><span class="sxs-lookup"><span data-stu-id="96567-119">Enterprise Edition Back End</span></span></p></td>
<td><p><span data-ttu-id="96567-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">在 Lync Server 2013 中還原 Enterprise Edition 後端伺服器</a></span><span class="sxs-lookup"><span data-stu-id="96567-120"><a href="lync-server-2013-restoring-an-enterprise-edition-back-end-server.md">Restoring an Enterprise Edition Back End Server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96567-121">Enterprise Edition 鏡像後端主伺服器</span><span class="sxs-lookup"><span data-stu-id="96567-121">Enterprise Edition Mirrored Back End Primary Server</span></span></p></td>
<td><p><span data-ttu-id="96567-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-主要</a></span><span class="sxs-lookup"><span data-stu-id="96567-122"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - primary</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96567-123">Enterprise Edition 鏡像後端次要伺服器</span><span class="sxs-lookup"><span data-stu-id="96567-123">Enterprise Edition Mirrored Back End Secondary Server</span></span></p></td>
<td><p><span data-ttu-id="96567-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">在 Lync Server 2013 中還原鏡像的 Enterprise Edition 後端伺服器-鏡像</a></span><span class="sxs-lookup"><span data-stu-id="96567-124"><a href="lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md">Restoring a mirrored Enterprise Edition Back End Server in Lync Server 2013 - mirror</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96567-125">任何執行伺服器角色的 Enterprise Edition 伺服器，例如前端伺服器、Edge Server、Director、轉送伺服器或 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="96567-125">Any Enterprise Edition server running a server role, such as a Front End Server, Edge Server, Director, Mediation Server,.or Persistent Chat Server.</span></span></p></td>
<td><p><span data-ttu-id="96567-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">在 Lync Server 2013 中還原 Enterprise Edition 成員伺服器</a></span><span class="sxs-lookup"><span data-stu-id="96567-126"><a href="lync-server-2013-restoring-an-enterprise-edition-member-server.md">Restoring an Enterprise Edition member server in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96567-127">整個 Lync 伺服器集區</span><span class="sxs-lookup"><span data-stu-id="96567-127">An entire Lync Server pool</span></span></p></td>
<td><p><span data-ttu-id="96567-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">在 Lync Server 2013 中還原 Lync Server 集區</a></span><span class="sxs-lookup"><span data-stu-id="96567-128"><a href="lync-server-2013-restoring-a-lync-server-pool.md">Restoring a Lync Server pool in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96567-129">Enterprise Edition 檔存放區</span><span class="sxs-lookup"><span data-stu-id="96567-129">Enterprise Edition File Store</span></span></p></td>
<td><p><span data-ttu-id="96567-130"><a href="lync-server-2013-restoring-a-file-store.md">在 Lync Server 2013 中還原檔存放區</a></span><span class="sxs-lookup"><span data-stu-id="96567-130"><a href="lync-server-2013-restoring-a-file-store.md">Restoring a file store in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96567-131">獨立監控資料庫或封存資料庫</span><span class="sxs-lookup"><span data-stu-id="96567-131">A standalone Monitoring database or Archiving database</span></span></p></td>
<td><p><span data-ttu-id="96567-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">在 Lync Server 2013 中還原監控或封存資料</a></span><span class="sxs-lookup"><span data-stu-id="96567-132"><a href="lync-server-2013-restoring-monitoring-or-archiving-data.md">Restoring monitoring or archiving data in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96567-133">獨立的持久聊天資料庫</span><span class="sxs-lookup"><span data-stu-id="96567-133">A stand-alone Persistent Chat database</span></span></p></td>
<td><p><span data-ttu-id="96567-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">在 Lync Server 2013 中還原 Persistent Chat 資料</a></span><span class="sxs-lookup"><span data-stu-id="96567-134"><a href="lync-server-2013-restoring-persistent-chat-data.md">Restoring Persistent Chat data in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="gathering-hardware-software-and-tools"></a><span data-ttu-id="96567-135">收集硬體、軟體及工具</span><span class="sxs-lookup"><span data-stu-id="96567-135">Gathering Hardware, Software, and Tools</span></span>

<span data-ttu-id="96567-136">當您還原伺服器時，您必須從新的或全新的電腦開始。</span><span class="sxs-lookup"><span data-stu-id="96567-136">When you restore a server, you need to start with a new or clean computer.</span></span> <span data-ttu-id="96567-137">此外，您必須具備下列可用的硬體和軟體：</span><span class="sxs-lookup"><span data-stu-id="96567-137">Additionally, you must have the following hardware and software available:</span></span>

  - <span data-ttu-id="96567-138">具有相同完整功能變數名稱 (FQDN) 伺服器失敗的乾淨或新伺服器。</span><span class="sxs-lookup"><span data-stu-id="96567-138">A clean or new server with the same fully qualified domain name (FQDN) as the server that failed.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="96567-139">當您安裝作業系統時，請確定您未刪除 Active Directory 網域服務中的電腦帳戶，並確認已保留帳戶的群組許可權。</span><span class="sxs-lookup"><span data-stu-id="96567-139">When you install the operating system, make sure that you do not delete the computer account in Active Directory Domain Services, and verify that the group permissions for the account are retained.</span></span>

    
    </div>

  - <span data-ttu-id="96567-140">作業系統的安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="96567-140">Installation software for the operating system.</span></span> <span data-ttu-id="96567-141">若要安裝作業系統，請使用伺服器部署程式和組織建立的設定。</span><span class="sxs-lookup"><span data-stu-id="96567-141">To install the operating system, use the server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="96567-142">當您還原服務時，您應該會有這些程式和設定需求可供使用。</span><span class="sxs-lookup"><span data-stu-id="96567-142">You should have these procedures and configuration requirements available when you restore service.</span></span>

  - <span data-ttu-id="96567-143">SQL Server 2012 或 SQL Server 2008 R2 的安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="96567-143">Installation software for SQL Server 2012 or SQL Server 2008 R2.</span></span> <span data-ttu-id="96567-144">若要安裝資料庫伺服器，請使用適當版本的 SQL Server，以及組織所建立的資料庫伺服器部署程式和設定。</span><span class="sxs-lookup"><span data-stu-id="96567-144">To install a database server, use the appropriate version of SQL Server and the database server deployment procedures and configurations established by your organization.</span></span> <span data-ttu-id="96567-145">當您還原服務時，您應該會有這些程式和設定需求可供使用。</span><span class="sxs-lookup"><span data-stu-id="96567-145">You should have these procedures and configuration requirements available when you restore service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96567-146">安裝本機設定存放區時，Lync Server 部署嚮導會在每個 Standard Edition 伺服器和任何其他 Lync Server 伺服器上自動安裝 SQL Server 2012 Express，除非您已在伺服器上預先安裝 SQL Server 2012 或 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="96567-146">The Lync Server Deployment Wizard automatically installs SQL Server 2012 Express on each Standard Edition server and on any other Lync Server server when a local configuration store is installed, unless you have preinstalled SQL Server 2012 or SQL Server 2008 R2 on the server.</span></span>

    
    </div>

  - <span data-ttu-id="96567-147">用來製作系統映射的軟體。</span><span class="sxs-lookup"><span data-stu-id="96567-147">Software for taking system images.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="96567-148">建議您在安裝作業系統和 SQL Server 之後，在您開始還原之前，取得系統的影像複本，如此一來，您就可以使用此映射做為回退點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="96567-148">We recommend that you take an image copy of the system after you install the operating system and SQL Server, and before you start restoration, so that you can use this image as a rollback point in case something goes wrong during restoration.</span></span>

    
    </div>

  - <span data-ttu-id="96567-149">Lync Server 2013 安裝軟體。</span><span class="sxs-lookup"><span data-stu-id="96567-149">Lync Server 2013 installation software.</span></span> <span data-ttu-id="96567-150">Lync Server 部署嚮導位於 Lync Server 安裝資料夾或 media at \\ setup \\ amd64 \\Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="96567-150">The Lync Server Deployment Wizard is located in the Lync Server installation folder or media at \\setup\\amd64\\Setup.exe.</span></span>

<span data-ttu-id="96567-151">在還原期間，您可以使用下列工具：</span><span class="sxs-lookup"><span data-stu-id="96567-151">During restoration, you use the following tools:</span></span>

  - <span data-ttu-id="96567-152">Lync Server 管理命令介面 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="96567-152">Lync Server Management Shell cmdlets</span></span>

  - <span data-ttu-id="96567-153">Import-CsUserData</span><span class="sxs-lookup"><span data-stu-id="96567-153">Import-CsUserData</span></span>

  - <span data-ttu-id="96567-154">還原 Windows 資料夾的工具</span><span class="sxs-lookup"><span data-stu-id="96567-154">Tools for restoring Windows folders</span></span>

  - <span data-ttu-id="96567-155">拓撲產生器</span><span class="sxs-lookup"><span data-stu-id="96567-155">Topology Builder</span></span>

  - <span data-ttu-id="96567-156">SQL Server 資料庫公用程式，例如 SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="96567-156">SQL Server database utilities, such as SQL Server Management Studio</span></span>

</div>

<div>

## <a name="preparing-to-restore-a-server"></a><span data-ttu-id="96567-157">準備還原伺服器</span><span class="sxs-lookup"><span data-stu-id="96567-157">Preparing to Restore a Server</span></span>

<span data-ttu-id="96567-158">在還原伺服器之前，您必須執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="96567-158">Before you restore the server, you must perform the following steps:</span></span>

1.  <span data-ttu-id="96567-159">安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="96567-159">Install the operating system.</span></span>

2.  <span data-ttu-id="96567-160">如果伺服器是後端伺服器，請安裝 SQL Server 2012 或 SQL Server 2008 R2。</span><span class="sxs-lookup"><span data-stu-id="96567-160">If the server is a Back End Server, install SQL Server 2012 or SQL Server 2008 R2.</span></span>

3.  <span data-ttu-id="96567-161">還原或重新註冊憑證。</span><span class="sxs-lookup"><span data-stu-id="96567-161">Restore or reenroll your certificates.</span></span> <span data-ttu-id="96567-162">如需憑證的詳細資訊，請參閱 [Lync Server 2013： data](lync-server-2013-backup-and-restoration-requirements-data.md)中的「其他備份需求」的備份和還原需求。</span><span class="sxs-lookup"><span data-stu-id="96567-162">For details about certificates, see "Additional Backup Requirements" in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md).</span></span>

4.  <span data-ttu-id="96567-163">開始還原之前，請先取得系統的映射，以做為回退點，以防還原期間發生問題。</span><span class="sxs-lookup"><span data-stu-id="96567-163">Take an image of the system before starting restoration to use as a rollback point, in case something goes wrong during restoration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96567-164">Lync Server 部署嚮導和本主題中的程式所述的指令程式和相關主題，設定所有必要的存取控制清單 (ACLs) 。</span><span class="sxs-lookup"><span data-stu-id="96567-164">The Lync Server Deployment Wizard and cmdlets described in the procedures in this topic, and related topics, set all required access control lists (ACLs).</span></span>



</div>

<span data-ttu-id="96567-165">確認您要還原之元件所需的硬體和軟體是否可供您開始還原。</span><span class="sxs-lookup"><span data-stu-id="96567-165">Verify that the hardware and the software that you need for the components that you plan to restore are available before you start restoration.</span></span> <span data-ttu-id="96567-166">安裝作業系統和 SQL Server 之後，您可以從遠端執行下列還原程式中的大部分步驟。</span><span class="sxs-lookup"><span data-stu-id="96567-166">After you install the operating system and SQL Server, most of the steps in the following restoration procedures can be run remotely.</span></span> <span data-ttu-id="96567-167">例外狀況會注明在程式中。</span><span class="sxs-lookup"><span data-stu-id="96567-167">The exceptions are noted in the procedures.</span></span>

<span data-ttu-id="96567-168">您也應該將組織的備份及還原計劃及最後一次備份中的資訊，例如本文的工作表中的資訊 (如需詳細資訊，請參閱 [Lync Server 2013) 的備份與還原工作表](lync-server-2013-backup-and-restoration-worksheets.md) （在您開始還原之前）。</span><span class="sxs-lookup"><span data-stu-id="96567-168">You should also have your organization's backup and restoration plan and the information from your last backup, such as the information in the worksheets in this document (for details, see [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)), available before you begin restoration.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

