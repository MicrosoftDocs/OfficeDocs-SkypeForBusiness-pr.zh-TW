---
title: SQL Server Reporting Services (不符合必要條件)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。
ms.openlocfilehash: 792c9d3b6e7c398d517549eb55aaf85086badb64
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100009"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="b052d-104">SQL Server Reporting Services (不符合必要條件)</span><span class="sxs-lookup"><span data-stu-id="b052d-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="b052d-p102">如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。</span><span class="sxs-lookup"><span data-stu-id="b052d-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="b052d-107">若要解決此問題，請確定您已將監控伺服器加入至網域，該伺服器已在拓撲產生器中定義，而且拓撲已經發佈。</span><span class="sxs-lookup"><span data-stu-id="b052d-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="b052d-108">Sql server 上也必須提供 SQL Server Reporting Services，並將其安裝為 SQL Server 上的監控伺服器資料庫中的功能。</span><span class="sxs-lookup"><span data-stu-id="b052d-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="b052d-109">如需詳細資訊，請參閱 [Install Monitoring Reports In 商務用 Skype Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) 和 [部署監控](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="b052d-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>