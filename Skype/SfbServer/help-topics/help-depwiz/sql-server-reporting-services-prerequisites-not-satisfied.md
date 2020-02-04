---
title: SQL Server Reporting Services (未滿足先決條件)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeploySSRSPrereqNotSatisfied
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6be29df-b882-4ba8-ba40-8062eb3bb14d
description: 如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。
ms.openlocfilehash: 94a20ce6f1a48e5eeed098777494e2d1f16597c1
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/03/2020
ms.locfileid: "41687306"
---
# <a name="sql-server-reporting-services-prerequisites-not-satisfied"></a><span data-ttu-id="38200-104">SQL Server Reporting Services (未滿足先決條件)</span><span class="sxs-lookup"><span data-stu-id="38200-104">SQL Server Reporting Services (Prerequisites Not Satisfied)</span></span>

<span data-ttu-id="38200-p102">如果基礎結構中未部署監控伺服器，您會看到此頁面。這表示未達到部署監控伺服器報告的最小需求。</span><span class="sxs-lookup"><span data-stu-id="38200-p102">You will see this page if there is no Monitoring Server deployed in your infrastructure. This indicates that the minimum requirements for deploying Monitoring Server reports have not been met.</span></span>

<span data-ttu-id="38200-107">若要解決此問題，請確定您已將監視伺服器加入網域，且已在拓撲結構建立程式中定義，且已發佈拓撲。</span><span class="sxs-lookup"><span data-stu-id="38200-107">To resolve this issue, make sure that you have a Monitoring Server joined to the domain, that it is defined in Topology Builder, and that the topology has been published.</span></span> <span data-ttu-id="38200-108">Sql server Reporting Services 也必須在 SQL Server 上提供，且在 SQL Server 上的 [監視伺服器] 資料庫中已安裝為功能。</span><span class="sxs-lookup"><span data-stu-id="38200-108">SQL Server Reporting Services must also be available on the SQL Server, and installed as a feature into the Monitoring Server database on the SQL Server.</span></span>

<span data-ttu-id="38200-109">如需詳細資訊，請參閱[在商務用 Skype Server 2015 中安裝監視報告](../../deploy/deploy-monitoring/install-monitoring-reports.md)和[部署監視](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)。</span><span class="sxs-lookup"><span data-stu-id="38200-109">For details, see [Install Monitoring Reports in Skype for Business Server 2015](../../deploy/deploy-monitoring/install-monitoring-reports.md) and [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>


