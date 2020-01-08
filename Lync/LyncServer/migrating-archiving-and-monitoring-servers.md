---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901961ad7456dfd8b0340cba03ff44a9e77a147f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="b9ca5-102">移轉封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="b9ca5-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9ca5-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="b9ca5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="b9ca5-104">如果您在 Lync Server 2010 環境中部署了 [封存伺服器] 和 [監視伺服器]，您可以在您遷移前端池之後，將這些伺服器部署在 Lync Server 2013 環境中。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="b9ca5-105">不過，如果封存和監控功能對您的組織而言是至關重要的，您應該先在您的 Lync Server 2013 試驗區中新增封存和監控，以便在遷移過程中使用這些功能。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="b9ca5-106">如果您想要在遷移期間進行封存與監控，請記住下列考慮事項：</span><span class="sxs-lookup"><span data-stu-id="b9ca5-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="b9ca5-107">存檔資料和監視資料不會移至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="b9ca5-108">您在解除舊版環境之前備份的資料將是 Lync Server 2010 環境中的活動歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="b9ca5-109">Lync Server 2010 版本的封存伺服器和監視伺服器只能與 Lync Server 2010 前端池相關聯。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="b9ca5-110">在 Lync Server 2013 中，[封存及監視] 不再是伺服器角色，但已整合至 Lync Server 2013 前端池的服務。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="b9ca5-111">在舊版和 Lync Server 2013 部署期間共存期間，Lync Server 2010 版本的封存伺服器與監視伺服器會針對駐留在 Lync Server 2010 池的使用者收集資料。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="b9ca5-112">Lync Server 2013 中的 [封存與監控] 可收集駐留在 Lync Server 2013 池的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9ca5-113">在遷移階段，當您仍將舊版 Edge 伺服器與新的 Lync Server 2013 試驗池結合使用時，Lync Server 2010 版本的封存伺服器會繼續針對駐留在 lync server 2010 中的使用者收集資料，並在 Lync Server 2013 中歸檔收集駐留在 Lync Server 2013 池的使用者資料。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="b9ca5-114">如果您在 Lync Server 2013 與 [封存與監控] 結合使用協力廠商的 [封存與監控] 解決方案，請諮詢您的供應商，瞭解您需要何時以及如何將協力廠商解決方案整合到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b9ca5-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

