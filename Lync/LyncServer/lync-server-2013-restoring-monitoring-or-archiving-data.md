---
title: Lync Server 2013：還原監控或封存資料
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring monitoring or archiving data
ms:assetid: 60118526-13bb-4b03-803e-6ffae219d436
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202175(v=OCS.15)
ms:contentKeyID: 51541483
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e908792e8a2563094b11bcce73d4ac6ce6c7121
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511420"
---
# <a name="restoring-monitoring-or-archiving-data-in-lync-server-2013"></a><span data-ttu-id="22e6e-102">在 Lync Server 2013 中還原監控或封存資料</span><span class="sxs-lookup"><span data-stu-id="22e6e-102">Restoring monitoring or archiving data in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22e6e-103">_**主題上次修改日期：** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="22e6e-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="22e6e-104">在失敗後，不需要還原監控和封存資料，就能讓 Lync Server 保持開啟狀態。</span><span class="sxs-lookup"><span data-stu-id="22e6e-104">Restoring monitoring and archiving data is not required to get Lync Server up and running after a failure.</span></span> <span data-ttu-id="22e6e-105">不過，如果監控和封存資料對您的組織來說很重要，您會想要在重新建立資料庫之後還原資料。</span><span class="sxs-lookup"><span data-stu-id="22e6e-105">However, if monitoring and archiving data is critical to your organization, you will want to restore the data after you re-create the databases.</span></span>

<span data-ttu-id="22e6e-106">下列程式說明如何使用 SQL Server Management Studio 來還原封存或監控資料。</span><span class="sxs-lookup"><span data-stu-id="22e6e-106">The following procedure describes how to use SQL Server Management Studio to restore archiving or monitoring data.</span></span>

<div>

## <a name="to-restore-monitoring-or-archiving-data-from-a-backup-file"></a><span data-ttu-id="22e6e-107">從備份檔還原監控或封存資料</span><span class="sxs-lookup"><span data-stu-id="22e6e-107">To restore monitoring or archiving data from a backup file</span></span>

1.  <span data-ttu-id="22e6e-108">以本機電腦上的管理員群組成員或具有同等使用者權限的群組的成員身分，登入您要還原的伺服器。</span><span class="sxs-lookup"><span data-stu-id="22e6e-108">Log on to the server that you are restoring as a member of the Administrators group on the local computer or a group with equivalent user rights.</span></span>

2.  <span data-ttu-id="22e6e-109">開啟 SQL Server Management Studio：按一下 [ **開始**]，依序按一下 [ **所有程式**]、[ **microsoft SQL Server 2012** ] 或 **[microsoft sql Server 2008 R2**]，然後按一下 **[sql server management Studio**]。</span><span class="sxs-lookup"><span data-stu-id="22e6e-109">Open SQL Server Management Studio: click **Start**, click **All Programs**, click **Microsoft SQL Server 2012** or **Microsoft SQL Server 2008 R2**, and then click **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="22e6e-110">在 [連線至伺服器]\*\*\*\* 中，至少提供伺服器的名稱及驗證資訊，以連線至 SQL Server 執行個體。</span><span class="sxs-lookup"><span data-stu-id="22e6e-110">In **Connect to Server**, connect to the SQL Server instance by providing at least the name of the server and the authentication information.</span></span>

4.  <span data-ttu-id="22e6e-111">在 [物件總管]\*\*\*\* 中，以滑鼠右鍵按一下 [資料庫]\*\*\*\*，然後按一下 [還原資料庫]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-111">In **Object Explorer**, right-click **Databases**, and then click **Restore Database**.</span></span>

5.  <span data-ttu-id="22e6e-112">在 [選取頁面]\*\*\*\* 底下，按一下 [一般]\*\*\*\*，然後在 [目的地資料庫]\*\*\*\* 中，選取資料庫名稱，如下所示：</span><span class="sxs-lookup"><span data-stu-id="22e6e-112">Under **Select a page**, click **General**, and then in **To database** select the database name as follows:</span></span>
    
      - <span data-ttu-id="22e6e-113">若為封存資料庫，請選取 [ **LcsLog**]。</span><span class="sxs-lookup"><span data-stu-id="22e6e-113">For an Archiving database, select **LcsLog**.</span></span>
    
      - <span data-ttu-id="22e6e-114">若為詳細通話記錄 (CDR) 資料庫，請選取 [LcsCDR]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-114">For a call detail recording (CDR) database, select **LcsCDR**.</span></span>
    
      - <span data-ttu-id="22e6e-115">若為經驗品質 (QoE) 資料庫，請選取 [QoEMetrics]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-115">For a Quality of Experience (QoE) database, select **QoEMetrics**.</span></span>

6.  <span data-ttu-id="22e6e-116">按一下 [來源裝置]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-116">Click **From device**.</span></span>

7.  <span data-ttu-id="22e6e-117">在 [選取要還原的備份組]\*\*\*\* 底下，按一下備份檔，然後按一下 [還原]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-117">Under **Select the backup sets to restore**, click the backup file, and then click **Restore**.</span></span>

8.  <span data-ttu-id="22e6e-118">在 [選取頁面]\*\*\*\* 底下，按一下 [選項]\*\*\*\*，確認資料檔案路徑及記錄檔路徑在正確的資料夾中，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-118">Under **Select a page**, click **Options**, verify that the data file path and log path are in the correct folder, and then click **OK**.</span></span>

</div>

<div>

## <a name="to-make-sure-that-access-control-lists-acls-are-correct"></a><span data-ttu-id="22e6e-119">確定 (ACLs) 的存取控制清單正確</span><span class="sxs-lookup"><span data-stu-id="22e6e-119">To make sure that access control lists (ACLs) are correct</span></span>

1.  <span data-ttu-id="22e6e-120">依序展開 [資料庫]\*\*\*\*、封存或監控資料庫、[安全性]\*\*\*\* 及 [使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-120">Expand **Databases**, expand the archiving or monitoring database, expand **Security**, and then expand **Users**.</span></span>

2.  <span data-ttu-id="22e6e-121">確認網域群組 RTCComponentUniversalServices 以使用者身分存在。</span><span class="sxs-lookup"><span data-stu-id="22e6e-121">Verify that the domain group RTCComponentUniversalServices exists as a user.</span></span>

3.  <span data-ttu-id="22e6e-122">如果 [ **使用者**] 底下 RTCComponentUniversalServices 不存在，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="22e6e-122">If RTCComponentUniversalServices does not exist under **Users**, do the following:</span></span>
    
    1.  <span data-ttu-id="22e6e-123">以滑鼠右鍵按一下 [使用者]\*\*\*\*，然後按一下 [新增使用者]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-123">Right-click **Users**, and then click **New User**.</span></span>
    
    2.  <span data-ttu-id="22e6e-124">在 **[登入名稱**] 中，輸入遺失的組名 RTCComponentUniversalServices。</span><span class="sxs-lookup"><span data-stu-id="22e6e-124">In **Login name**, type the missing group name, RTCComponentUniversalServices.</span></span>
    
    3.  <span data-ttu-id="22e6e-125">在 [資料庫角色成員資格]\*\*\*\* 底下，選取 [ServerRole]\*\*\*\* 權限，然後按一下 [確定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="22e6e-125">Under **Database role membership**, select the **ServerRole** permission, and then click **OK**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="22e6e-126">您不需要重新啟動封存或監控服務。</span><span class="sxs-lookup"><span data-stu-id="22e6e-126">You do not need to restart the archiving or monitoring service.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

