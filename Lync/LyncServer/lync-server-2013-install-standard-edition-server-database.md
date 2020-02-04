---
title: Lync Server 2013：安裝 Standard Edition Server 資料庫
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="d202c-102">安裝 Lync Server 2013 的 Standard Edition Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="d202c-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d202c-103">_**主題上次修改日期：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d202c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d202c-104">將標準版伺服器設定為基礎結構中的唯一伺服器，讓總部使用者與其他伺服器安裝不同，因為 [**部署嚮導]** 中有專門用來設定初始伺服器的選項。</span><span class="sxs-lookup"><span data-stu-id="d202c-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="d202c-105">若要安裝標準版伺服器</span><span class="sxs-lookup"><span data-stu-id="d202c-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="d202c-106">登入您要將標準版伺服器安裝為本機系統管理員或對等網域的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d202c-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="d202c-107">如果您尚未準備 Active Directory 網域服務，請先執行這些程式。</span><span class="sxs-lookup"><span data-stu-id="d202c-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="d202c-108">如需詳細資訊，請參閱[準備 Lync Server 2013 的 Active Directory 網域服務](lync-server-2013-preparing-active-directory-domain-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d202c-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="d202c-109">在 Lync Server 部署嚮導中，按一下 [**準備第一個標準版 Server**]。</span><span class="sxs-lookup"><span data-stu-id="d202c-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="d202c-110">在 [**準備單一標準版伺服器**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d202c-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="d202c-111">在 [**執行命令**] 頁面上，SQL Server 2012 Express 已安裝為中央管理儲存。</span><span class="sxs-lookup"><span data-stu-id="d202c-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="d202c-112">已建立必要的防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="d202c-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="d202c-113">完成資料庫與必備軟體的安裝後，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d202c-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d202c-114">初始安裝可能需要一些時間，且 [命令輸出摘要] 畫面沒有顯示更新。</span><span class="sxs-lookup"><span data-stu-id="d202c-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="d202c-115">這是由 SQL Server Express 的安裝所造成。</span><span class="sxs-lookup"><span data-stu-id="d202c-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="d202c-116">如果您需要監視資料庫的安裝，請使用 [工作管理員] 來監視設定。</span><span class="sxs-lookup"><span data-stu-id="d202c-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="d202c-117">如果您尚未安裝 [管理工具]，請在 [Lync Server 部署嚮導] 頁面上，按一下 [**安裝拓撲**建立器]。</span><span class="sxs-lookup"><span data-stu-id="d202c-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="d202c-118">如需詳細資訊，請參閱[安裝 Lync Server 2013 系統管理工具](lync-server-2013-install-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="d202c-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="d202c-119">確認 [準備 Active Directory]、「準備第一個標準版 server」和「安裝拓撲建立器」旁邊有綠色的核取記號。</span><span class="sxs-lookup"><span data-stu-id="d202c-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

