---
title: SQL Server Reporting Services (不符合必要條件)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
ROBOTS: NOINDEX, NOFOLLOW
description: 如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。
ms.openlocfilehash: 657c1b203dd5d01fedde9ad0c5b08c6775f4bd4e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118902"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="81073-104">SQL Server Reporting Services (不符合必要條件)</span><span class="sxs-lookup"><span data-stu-id="81073-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="81073-p102">如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。</span><span class="sxs-lookup"><span data-stu-id="81073-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="81073-107">若要解決此問題，請確定您已將監控伺服器加入至網域，該伺服器已在拓撲產生器中定義，而且拓撲已經發佈。</span><span class="sxs-lookup"><span data-stu-id="81073-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="81073-108">Sql server 上也必須提供 SQL Server Reporting Services，並將其安裝為 SQL Server 上的監控伺服器資料庫中的功能。</span><span class="sxs-lookup"><span data-stu-id="81073-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="81073-109">如需詳細資訊，請參閱 [在商務用 Skype Server 中安裝監視報告](../../../deploy/deploy-monitoring/install-monitoring-reports.md) 及 [部署監控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="81073-109">For details, see [Install Monitoring Reports in Skype for Business Server](../../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>