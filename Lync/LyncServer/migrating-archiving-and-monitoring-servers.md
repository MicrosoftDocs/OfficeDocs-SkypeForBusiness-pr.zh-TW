---
title: 移轉封存和監控伺服器
description: 遷移封存和監控伺服器。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2dabd16fd38dbf463a4bc608fe77368e781571fd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565379"
---
# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="ea7c3-103">移轉封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="ea7c3-103">Migrating Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea7c3-104">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="ea7c3-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="ea7c3-105">如果您已在 Lync Server 2010 環境中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在 Lync Server 2013 環境中部署這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-105">If you deployed Archiving Server and Monitoring Server in your Lync Server 2010 environment, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="ea7c3-106">不過，如果封存和監控功能對您的組織而言很重要，您應該在遷移之前，先在 Lync Server 2013 試驗集區中新增封存和監控功能，以便在遷移程式期間使用該功能。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-106">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your Lync Server 2013 pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="ea7c3-107">移轉過程中，如果您需要存封和監控功能，請記住以下注意事項：</span><span class="sxs-lookup"><span data-stu-id="ea7c3-107">If you want archiving and monitoring functionality during the migration process, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="ea7c3-108">封存資料和監控資料不會移至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-108">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ea7c3-109">您解除委任舊版環境之前所備份的資料，將會是您在 Lync Server 2010 環境中的活動歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-109">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Lync Server 2010 environment.</span></span>

  - <span data-ttu-id="ea7c3-110">Lync Server 2010 版本的封存伺服器和監控伺服器只能與 Lync Server 2010 前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-110">The Lync Server 2010 version of Archiving Server and Monitoring Server can be associated only with a Lync Server 2010 Front End pool.</span></span> <span data-ttu-id="ea7c3-111">在 Lync Server 2013 中，封存與監控不再是伺服器角色，但已整合至 Lync Server 2013 前端集區的服務。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-111">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="ea7c3-112">在舊版和 Lync Server 2013 部署共存期間，您的封存伺服器和監控伺服器的 Lync Server 2010 版本會為位於 Lync Server 2010 集區的使用者收集資料。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-112">During the time that your legacy and Lync Server 2013 deployments coexist, the Lync Server 2010 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2010 pools.</span></span> <span data-ttu-id="ea7c3-113">Lync Server 2013 中的封存與監控會收集位於 Lync Server 2013 集區之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-113">Archiving and Monitoring in Lync Server 2013 gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ea7c3-114">在遷移階段，當您仍然使用舊版 Edge server 與新的 Lync Server 2013 試驗集區時，Lync server 2010 版本的封存伺服器會繼續為位於 lync server 2010 集區中的使用者收集資料，而在 Lync 2013 Server 中封存會收集位於 Lync Server 2013 集區之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-114">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Lync Server 2010 version of Archiving Server continues to gather data for users homed on Lync Server 2010 pools and Archiving in Lync Server 2013 gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="ea7c3-115">如果您使用協力廠商的封存及監控解決方案搭配 Lync Server 2013 中的封存與監控，請洽詢廠商，以瞭解如何在何時和如何將協力廠商解決方案與 Lync Server 2013 整合。</span><span class="sxs-lookup"><span data-stu-id="ea7c3-115">If you use a third-party archiving and monitoring solution in conjunction with Archiving and Monitoring in Lync Server 2013, consult with your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

