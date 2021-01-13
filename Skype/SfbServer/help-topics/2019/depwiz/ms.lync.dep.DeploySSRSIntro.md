---
title: SQL Server Reporting Services (簡介)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeploySSRSIntro
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f3cda686-6301-419c-af68-b49cc785e5fc
ROBOTS: NOINDEX, NOFOLLOW
description: 每個前端集區和 Survivable Branch Appliance 只能有一個相關聯的監控伺服器。當網站啟用監控時，監控伺服器會提供詳細通話記錄 (CDR) 和經驗品質 (QoE) 的資料收集與報告。
ms.openlocfilehash: e00399f77ae5cd8a755e6c1205c110a2b5542bcf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820393"
---
# <a name="sql-server-reporting-services-intro"></a><span data-ttu-id="3063f-104">SQL Server Reporting Services (簡介)</span><span class="sxs-lookup"><span data-stu-id="3063f-104">SQL Server Reporting Services (Intro)</span></span>
 
<span data-ttu-id="3063f-p102">每個前端集區和 Survivable Branch Appliance 只能有一個相關聯的監控伺服器。當網站啟用監控時，監控伺服器會提供詳細通話記錄 (CDR) 和經驗品質 (QoE) 的資料收集與報告。</span><span class="sxs-lookup"><span data-stu-id="3063f-p102">Each Front End pool and Survivable Branch Appliance can have only one Monitoring Server associated with it. When monitoring is enabled for the site, Monitoring Server provides call detail recording (CDR) and Quality of Experience (QoE) data collection and reporting.</span></span>
  
<span data-ttu-id="3063f-107">只要使用量不超出監控伺服器的容量，一個網站的所有集區和多個中央網站的集區可以使用同一個監控伺服器。</span><span class="sxs-lookup"><span data-stu-id="3063f-107">All pools at a site and the pools of multiple central sites can use the same Monitoring Server, if usage does not exceed the capacity of the Monitoring Server.</span></span> <span data-ttu-id="3063f-108">如需設計拓撲以支援監控的詳細資訊，請參閱部署檔中的在 [商務用 Skype Server 中建立監控儲存區與前端集區的關聯](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) 。</span><span class="sxs-lookup"><span data-stu-id="3063f-108">For details about designing a topology to support monitoring, see [Associate a monitoring store with a Front End pool in Skype for Business Server](../../../deploy/deploy-monitoring/associate-a-monitoring-store.md) in the Deployment documentation.</span></span>
  

