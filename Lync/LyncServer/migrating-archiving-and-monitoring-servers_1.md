---
title: 移轉封存和監控伺服器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43b7c7509dcf678967db651900c67cdfb3d26685
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a><span data-ttu-id="32cdd-102">移轉封存和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="32cdd-102">Migrating Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32cdd-103">_**主題上次修改日期：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="32cdd-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="32cdd-104">如果您已在 Office 通訊伺服器 2007 R2 中部署封存伺服器和監控伺服器，您可以在遷移前端集區之後，在 Lync Server 2013 環境中部署這些伺服器。</span><span class="sxs-lookup"><span data-stu-id="32cdd-104">If you deployed Archiving Server and Monitoring Server in your Office Communications Server 2007 R2, you can deploy these servers in your Lync Server 2013 environment after you migrate your Front End pools.</span></span> <span data-ttu-id="32cdd-105">不過，如果封存和監控功能對您的組織而言很重要，您應該先在試驗集區中新增封存與監控，以在遷移程式期間使用該功能。</span><span class="sxs-lookup"><span data-stu-id="32cdd-105">If archiving and monitoring functionality are critical to your organization, however, you should add archiving and monitoring to your pilot pool before you migrate so that the functionality is available during the migration process.</span></span>

<span data-ttu-id="32cdd-106">若希望在移轉共存階段期間繼續提供封存及監控功能，請牢記下列注意事項：</span><span class="sxs-lookup"><span data-stu-id="32cdd-106">If you want archiving and monitoring functionality during the migration and coexistence phase, keep the following considerations in mind:</span></span>

  - <span data-ttu-id="32cdd-107">封存資料和監控資料不會移至 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="32cdd-107">Archiving data and monitoring data are not moved to the Lync Server 2013 deployment.</span></span> <span data-ttu-id="32cdd-108">解除委任舊版環境之前所備份的資料，將會是 Office 通訊伺服器 2007 R2 中的活動歷史。</span><span class="sxs-lookup"><span data-stu-id="32cdd-108">The data you back up prior to decommissioning the legacy environment will be your history of activity in the Office Communications Server 2007 R2.</span></span>

  - <span data-ttu-id="32cdd-109">Office 通訊伺服器 2007 R2 版本的封存伺服器和監控伺服器只能與 Office 通訊伺服器 2007 R2 前端集區相關聯。</span><span class="sxs-lookup"><span data-stu-id="32cdd-109">The Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server can be associated only with a Office Communications Server 2007 R2 Front End pool.</span></span> <span data-ttu-id="32cdd-110">在 Lync Server 2013 中，封存與監控不再是伺服器角色，但已整合至 Lync Server 2013 前端集區的服務。</span><span class="sxs-lookup"><span data-stu-id="32cdd-110">In Lync Server 2013, Archiving and Monitoring are no longer server roles, but services integrated into the Lync Server 2013 Front End pool.</span></span>

  - <span data-ttu-id="32cdd-111">在舊版和 Lync Server 2013 部署共存期間，您的 Office 通訊伺服器 2007 R2 版本的封存伺服器和監控伺服器會為位於 Office 通訊伺服器 2007 R2 pool 的使用者收集資料。</span><span class="sxs-lookup"><span data-stu-id="32cdd-111">During the time that your legacy and Lync Server 2013 deployments coexist, the Office Communications Server 2007 R2 version of Archiving Server and Monitoring Server gather data for users homed on Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="32cdd-112">Lync Server 2013 版本的封存伺服器和監控伺服器會收集位於 Lync Server 2013 集區之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="32cdd-112">The Lync Server 2013 version of Archiving Server and Monitoring Server gather data for users homed on Lync Server 2013 pools.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32cdd-113">在遷移階段，當您仍然使用舊版 Edge server 搭配新的 Lync Server 2013 試驗集區時，Office 通訊伺服器 2007 R2 版本的封存伺服器會繼續收集位於 Office 通訊伺服器 2007 R2 集區之使用者的資料，而 Lync Server 2013 版本的封存伺服器便會收集位於 Lync Server 2013 集區之使用者的資料。</span><span class="sxs-lookup"><span data-stu-id="32cdd-113">During the phase of migration when you are still using your legacy Edge server with the new Lync Server 2013 pilot pool, the Office Communications Server 2007 R2 version of Archiving Server continues to gather data for users homed on Office Communications Server 2007 R2 pools and the Lync Server 2013 version of Archiving Server gathers data for users homed on Lync Server 2013 pools.</span></span>

    
    </div>

  - <span data-ttu-id="32cdd-114">如果您使用協力廠商封存與監控解決方案與封存伺服器和監控伺服器搭配使用，請與您的廠商聯繫，以瞭解如何與 Lync Server 2013 整合協力廠商解決方案。</span><span class="sxs-lookup"><span data-stu-id="32cdd-114">If you use a third-party archiving and monitoring solution in conjunction with Archiving Server and Monitoring Server, talk to your vendor about when and how you need to integrate the third-party solution with Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

