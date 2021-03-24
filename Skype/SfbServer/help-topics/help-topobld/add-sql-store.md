---
title: 新增 SQL 存放區
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 若要定義新的 SQL 存放區，這表示您指定的是 SQL Server 資料庫和 SQL Server 實例（預設實例或命名實例），請指定下列各項。
ms.openlocfilehash: 28018a7320bc42761a668aaff385302016781592
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095597"
---
# <a name="add-sql-store"></a><span data-ttu-id="928c1-103">新增 SQL 存放區</span><span class="sxs-lookup"><span data-stu-id="928c1-103">Add SQL Store</span></span>

<span data-ttu-id="928c1-104">若要定義新的 SQL 存放區，這表示您指定的是 SQL Server 資料庫和 SQL Server 實例（預設實例或命名實例），請指定下列各項。</span><span class="sxs-lookup"><span data-stu-id="928c1-104">To define a new SQL Store, which means that you are specifying a SQL Server-based database and an instance of SQL Server—either a default instance or a named instance—you specify the following.</span></span>

<span data-ttu-id="928c1-105">指定將主控您所定義之資料庫實例之 SQL Server 的完整功能變數名稱 (FQDN) 。</span><span class="sxs-lookup"><span data-stu-id="928c1-105">Specify the fully qualified domain name (FQDN) of the SQL Server that will host the database instance that you are defining.</span></span>

<span data-ttu-id="928c1-106">指定將主控資料的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="928c1-106">Specify the instance of SQL Server that will host the data.</span></span> <span data-ttu-id="928c1-107">您可以指定預設實例，也可以指定命名實例。</span><span class="sxs-lookup"><span data-stu-id="928c1-107">You can specify the default instance, or you can specify a named instance.</span></span>

<span data-ttu-id="928c1-108">組合在特定實例中的資料庫，應明確瞭解。</span><span class="sxs-lookup"><span data-stu-id="928c1-108">Collocation of databases in specific instances should be very clearly understood.</span></span> <span data-ttu-id="928c1-109">如需伺服器組合及資料庫實例組合的詳細資訊，請參閱[Standard Edition Server 部署](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)中[前端集區部署](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment)和伺服器組合中的伺服器組合。</span><span class="sxs-lookup"><span data-stu-id="928c1-109">For details about server collocation and database instance collocation, see [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) and [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment).</span></span>