---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c52bf0791a149625732d3f700a09a92017fa87ca
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="94c9b-102">移轉封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="94c9b-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94c9b-103">_**主題上次修改日期：** 2012年-10-02_</span><span class="sxs-lookup"><span data-stu-id="94c9b-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="94c9b-104">如果您在 Lync Server 2010 環境中部署封存伺服器及監控伺服器，您可以在移轉您的前端集區後部署 [Lync Server 2013 環境上的這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="94c9b-104">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="94c9b-105">如果貴組織的關鍵封存和監控功能，不過，您應該新增封存和監控至 Lync Server 2013 試驗集區，以便在遷移過程中功能可供使用移轉之前。</span><span class="sxs-lookup"><span data-stu-id="94c9b-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="94c9b-106">移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：</span><span class="sxs-lookup"><span data-stu-id="94c9b-106">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="94c9b-107">封存資料和監控資料不會移至 Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="94c9b-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="94c9b-108">您解除委任舊版環境之前所備份的資料，將會是您在 Lync Server 2010 環境中的活動歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="94c9b-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="94c9b-109">封存伺服器及監控伺服器的 Lync Server 2010 版本可以只與 Lync Server 2010 前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="94c9b-109">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="94c9b-110">在 Lync Server 2013 中，封存和監控不再伺服器角色，但服務整合到 Lync Server 2013 前端集區。</span><span class="sxs-lookup"><span data-stu-id="94c9b-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="94c9b-111">在您的舊版和 Lync Server 2013 部署共存期間，封存伺服器及監控伺服器的 Lync Server 2010 版本會收集使用者的資料位於 Lync Server 2010 集區。</span><span class="sxs-lookup"><span data-stu-id="94c9b-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="94c9b-112">封存和監控 Lync Server 2013 中的收集使用者的資料位於 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="94c9b-112">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94c9b-113">移轉時仍使用舊版 Edge server 與試驗集區，Lync Server 2010 版本的封存伺服器將持續收集使用者的資料位於 Lync Server 2010 集區新 Lync Server 2013 和 Lync Server 2013 中的封存的階段蒐集使用者的資料位於 Lync Server 2013 集區。</span><span class="sxs-lookup"><span data-stu-id="94c9b-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="94c9b-114">如果您使用第三方封存與監控解決方案搭配封存和監控 Lync Server 2013 中的，請洽詢您的廠商需何時和如何需要與 Lync Server 2013 整合的協力廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="94c9b-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

