---
title: 商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/19/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 692b7d99-1bc9-4c99-a050-2bc2be8688b2
description: 摘要：閱讀此主題以瞭解商務用 Skype Server 2015 中的持續性聊天伺服器的硬體和軟體需求。
ms.openlocfilehash: d4609d557e5c55b680c4c0761f24cc4f320afcbd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095107"
---
# <a name="hardware-and-software-requirements-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="391cd-103">商務用 Skype 2015 Server 中的 Persistent Chat Server 的硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="391cd-103">Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="391cd-104">**摘要：** 閱讀此主題以瞭解商務用 Skype Server 2015 中持續性聊天伺服器的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="391cd-104">**Summary:** Read this topic to learn about hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="391cd-105">Persistent Chat Server 可以與商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition 一起安裝。</span><span class="sxs-lookup"><span data-stu-id="391cd-105">Persistent Chat Server can be installed with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span> <span data-ttu-id="391cd-106">需求取決於您已安裝的商務用 Skype Server 2015 版本，以及您的業務效能需求。</span><span class="sxs-lookup"><span data-stu-id="391cd-106">Requirements depend on which edition of Skype for Business Server 2015 you have installed, and the performance requirements of your business.</span></span> <span data-ttu-id="391cd-107">Enterprise Edition 最多可支援80000並行使用者。Standard Edition 最多可支援20000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="391cd-107">Enterprise Edition can support up to 80,000 concurrent users; Standard Edition can support up to 20,000 concurrent users.</span></span> <span data-ttu-id="391cd-108">Persistent Chat 是由前端元件及後端 SQL 資料庫元件所組成。</span><span class="sxs-lookup"><span data-stu-id="391cd-108">Persistent Chat consists of a front-end component as well as a back-end SQL database component.</span></span>
  
<span data-ttu-id="391cd-109">在您部署 Persistent Chat Server 之前，您必須確定符合下列硬體及軟體需求：</span><span class="sxs-lookup"><span data-stu-id="391cd-109">Before you deploy Persistent Chat Server, you must ensure that the following hardware and software requirements are met:</span></span>
  
- <span data-ttu-id="391cd-110">符合支援商務用 Skype Server 2015、Persistent Chat Server、資料庫伺服器及檔案伺服器的最低需求的硬體。</span><span class="sxs-lookup"><span data-stu-id="391cd-110">Hardware that meets minimum requirements to support Skype for Business Server 2015, Persistent Chat Server, database servers, and file servers.</span></span> <span data-ttu-id="391cd-111">如需詳細資訊，請參閱 [商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="391cd-111">For more information, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="391cd-112">支援的作業系統和資料庫軟體。</span><span class="sxs-lookup"><span data-stu-id="391cd-112">Supported operating system and database software.</span></span>
    
    <span data-ttu-id="391cd-113">如需支援的作業系統和資料庫軟體以及 Windows 更新需求的詳細資訊，請參閱 [商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="391cd-113">For details about supported operating systems and database software, and Windows update requirements, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
    
- <span data-ttu-id="391cd-114">商務用 Skype Server 2015 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="391cd-114">Skype for Business Server 2015 Front End Server.</span></span> <span data-ttu-id="391cd-115">前端伺服器是會話初始通訊協定 (SIP) 路由的基礎，它使得執行持續聊天伺服器的電腦與可能的持久聊天功能之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="391cd-115">The Front End Server is the foundation for Session Initiation Protocol (SIP) routing, which makes communication between computers running Persistent Chat Server and the Persistent Chat functionality possible.</span></span> 
    
- <span data-ttu-id="391cd-116">訊息佇列軟體。</span><span class="sxs-lookup"><span data-stu-id="391cd-116">Message Queuing software.</span></span> <span data-ttu-id="391cd-117">由 Persistent Chat Server 和 Persistent Chat 規章服務（若已部署）使用。</span><span class="sxs-lookup"><span data-stu-id="391cd-117">Used by the Persistent Chat Server and Persistent Chat Compliance service, if deployed.</span></span>
    
<span data-ttu-id="391cd-118">下列各節說明 Persistent Chat Server 和儲存 Persistent Chat 資料之資料庫的特定需求。</span><span class="sxs-lookup"><span data-stu-id="391cd-118">The following sections describe the specific requirements for Persistent Chat Server and the database that stores the Persistent Chat data.</span></span>

> [!NOTE] 
> <span data-ttu-id="391cd-119">商務用 Skype Server 2015 仍提供持續聊天，但商務用 Skype Server 2019 已不再支援。</span><span class="sxs-lookup"><span data-stu-id="391cd-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="391cd-120">小組中提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="391cd-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="391cd-121">如需詳細資訊，請參閱 [Microsoft 團隊升級快速](/microsoftteams/upgrade-start-here)入門。</span><span class="sxs-lookup"><span data-stu-id="391cd-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="391cd-122">如果您需要使用持續聊天，您可以選擇將需要這項功能的使用者遷移至小組，或是繼續使用商務用 Skype Server 2015。</span><span class="sxs-lookup"><span data-stu-id="391cd-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="front-end-server-requirements"></a><span data-ttu-id="391cd-123">前端伺服器需求</span><span class="sxs-lookup"><span data-stu-id="391cd-123">Front End Server requirements</span></span>

<span data-ttu-id="391cd-124">前端伺服器需求取決於您是否要使用商務用 Skype Server 2015 Enterprise Edition 或 Standard Edition 部署 Persistent Chat Server。</span><span class="sxs-lookup"><span data-stu-id="391cd-124">Front End Server requirements depend on whether you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition or Standard Edition.</span></span>
  
- <span data-ttu-id="391cd-125">若要使用商務用 Skype Server 2015 Enterprise Edition 部署 Persistent Chat Server，您可以在 Enterprise Edition 集區中的一或多台獨立電腦上部署 Persistent Chat Server 前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="391cd-125">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, you can deploy the Persistent Chat Server Front End Server on one or more standalone computers in the Enterprise Edition pool.</span></span> <span data-ttu-id="391cd-126">您無法在商務用 Skype Server 2015 前端伺服器上組合持久聊天前端伺服器。</span><span class="sxs-lookup"><span data-stu-id="391cd-126">You cannot collocate the Persistent Chat Front End Servers on the Skype for Business Server 2015 Front End Server.</span></span> 
    
    <span data-ttu-id="391cd-127">單一 Persistent Chat Server 前端伺服器可支援20000作用中的使用者。</span><span class="sxs-lookup"><span data-stu-id="391cd-127">A single Persistent Chat Server Front End Server can support 20,000 active users.</span></span> <span data-ttu-id="391cd-128">您可以有最多4個作用中前端的持久聊天伺服器集區，以支援所有80000並行使用者。</span><span class="sxs-lookup"><span data-stu-id="391cd-128">You can have a Persistent Chat Server pool with up to 4 active front ends thereby supporting a total of 80,000 concurrent users.</span></span> 
    
- <span data-ttu-id="391cd-129">若要使用商務用 Skype Server 2015 Standard Edition 部署 Persistent Chat Server，您可以組合與前端伺服器的持久聊天。</span><span class="sxs-lookup"><span data-stu-id="391cd-129">If you are deploying Persistent Chat Server with Skype for Business Server 2015 Standard Edition, you can collocate Persistent Chat with the Front End Server.</span></span> <span data-ttu-id="391cd-130">這種單一伺服器部署最多可支援20000使用者。</span><span class="sxs-lookup"><span data-stu-id="391cd-130">This single server deployment can support up to 20,000 users.</span></span> 
    
## <a name="persistent-chat-server-database-requirements"></a><span data-ttu-id="391cd-131">Persistent Chat Server 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="391cd-131">Persistent Chat Server database requirements</span></span>

<span data-ttu-id="391cd-132">Persistent Chat Server 需要 SQL Server 資料庫軟體，以儲存聊天室記錄和內容、設定資料、使用者布建資料，以及其他相關的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="391cd-132">Persistent Chat Server requires SQL Server database software to store chat room history and content, configuration data, user provisioning data, and other relevant metadata.</span></span> <span data-ttu-id="391cd-133">另外，它會使用 Persistent 聊天室規範資料庫來儲存規範資料。</span><span class="sxs-lookup"><span data-stu-id="391cd-133">Optionally, it uses the Persistent Chat Compliance database to store compliance data.</span></span> <span data-ttu-id="391cd-134">您可以在相同的 SQL Server 上組合持久的聊天室資料庫，也可以在相同的 SQL 實例上，與後端資料庫相同。</span><span class="sxs-lookup"><span data-stu-id="391cd-134">Persistent Chat databases can be collocated on the same SQL Server, or even the same SQL instance, as the back-end databases.</span></span> 
  
- <span data-ttu-id="391cd-135">若要以商務用 Skype Server 2015 Enterprise Edition 安裝 Persistent Chat Server，以確保取得最佳效能，建議您安裝 Persistent Chat file store。</span><span class="sxs-lookup"><span data-stu-id="391cd-135">If you are installing Persistent Chat Server with Skype for Business Server 2015 Enterprise Edition, to ensure optimum performance, it is recommended that you install the Persistent Chat file store.</span></span>
    
- <span data-ttu-id="391cd-136">若要使用商務用 Skype Server 2015 Standard edition 安裝 Persistent Chat Server，您可以在本機 SQL Server Express 實例上部署 Persistent 後端伺服器。</span><span class="sxs-lookup"><span data-stu-id="391cd-136">If you are installing Persistent Chat Server with Skype for Business Server 2015 Standard edition, you can deploy the Persistent Chat Store Back End Server on the local SQL Server Express instance.</span></span>
    
- <span data-ttu-id="391cd-137">Persistent Chat database (mgc) 與規範資料庫 (mgccomp) 可以位於相同的 SQL Server 實例或不同的 SQL Server 上。</span><span class="sxs-lookup"><span data-stu-id="391cd-137">The Persistent Chat database (mgc) and the compliance database (mgccomp) can be located in the same instance of SQL Server or on different SQL Servers.</span></span>
    
<span data-ttu-id="391cd-138">若要準備資料庫伺服器平臺，請確定每一部電腦都符合硬體需求，然後安裝必要軟體。</span><span class="sxs-lookup"><span data-stu-id="391cd-138">To prepare a database server platform, be sure that each computer meets the hardware requirements, and then install the prerequisite software.</span></span> <span data-ttu-id="391cd-139">Persistent Chat database servers 的伺服器平臺需要與商務用 Skype Server 2015 後端資料庫伺服器相同的硬體。</span><span class="sxs-lookup"><span data-stu-id="391cd-139">The server platform for the Persistent Chat database servers requires the same hardware as the Skype for Business Server 2015 back-end database server.</span></span> <span data-ttu-id="391cd-140">如需詳細資訊，請參閱 [商務用 Skype server 2015 的伺服器需求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="391cd-140">For details, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md).</span></span>
  
<span data-ttu-id="391cd-141">在資料庫伺服器上，確定已安裝下列其中一個軟體應用程式：</span><span class="sxs-lookup"><span data-stu-id="391cd-141">On the database server, be sure that one of the following software applications is installed:</span></span>

- <span data-ttu-id="391cd-142">Microsoft SQL Server 2017 搭配最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="391cd-142">Microsoft SQL Server 2017 with the latest service pack.</span></span>

- <span data-ttu-id="391cd-143">Microsoft SQL Server 2016 Service Pack 1，您必須使用商務用 Skype Server 累計更新7或更新版本執行。</span><span class="sxs-lookup"><span data-stu-id="391cd-143">Microsoft SQL Server 2016 with Service Pack 1, and you must run with Skype for Business Server Cumulative Update 7 or later releases.</span></span> <span data-ttu-id="391cd-144">建議使用最新的 service pack 來執行 SQL Server 2016。</span><span class="sxs-lookup"><span data-stu-id="391cd-144">We recommended running SQL Server 2016 with the latest service pack.</span></span> <span data-ttu-id="391cd-145">如需如何安裝 Microsoft SQL Server 2016 的詳細資訊，請參閱 [安裝 SQL server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016)。</span><span class="sxs-lookup"><span data-stu-id="391cd-145">For details about how to install Microsoft SQL Server 2016, see [Install SQL Server 2016](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2016).</span></span>

- <span data-ttu-id="391cd-146">Microsoft SQL Server 2014，必須使用商務用 Skype Server 累計更新6或更新版本執行。</span><span class="sxs-lookup"><span data-stu-id="391cd-146">Microsoft SQL Server 2014, and you must run with Skype for Business Server Cumulative Update 6 or later releases.</span></span> <span data-ttu-id="391cd-147">建議使用最新的 service pack 來執行 SQL Server 2014。</span><span class="sxs-lookup"><span data-stu-id="391cd-147">We recommended running SQL Server 2014 with the latest service pack.</span></span> <span data-ttu-id="391cd-148">如需如何安裝 Microsoft SQL Server 2014 的詳細資訊，請參閱 [安裝 SQL server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014)。</span><span class="sxs-lookup"><span data-stu-id="391cd-148">For details about how to install Microsoft SQL Server 2014, see [Install SQL Server 2014](/sql/database-engine/install-windows/install-sql-server?view=sql-server-2014).</span></span>

- <span data-ttu-id="391cd-149">Microsoft SQL Server 2012 (64-位版本) ，我們建議使用最新的 service pack 來執行。</span><span class="sxs-lookup"><span data-stu-id="391cd-149">Microsoft SQL Server 2012 (64-bit edition), and we recommended running with the latest service pack.</span></span> <span data-ttu-id="391cd-150">如需如何安裝 Microsoft SQL Server 2012 的詳細資訊，請參閱 [安裝 SQL server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110))。</span><span class="sxs-lookup"><span data-stu-id="391cd-150">For details about how to install Microsoft SQL Server 2012, see [Install SQL Server 2012](/previous-versions/sql/sql-server-2012/bb500395(v=sql.110)).</span></span>

## <a name="persistent-chat-server-certificate-requirements"></a><span data-ttu-id="391cd-151">Persistent Chat Server 憑證需求</span><span class="sxs-lookup"><span data-stu-id="391cd-151">Persistent Chat Server certificate requirements</span></span>

<span data-ttu-id="391cd-152">如需取得憑證、建立 SQL Server 資料庫及建立檔案存放區的詳細資訊，請參閱 [部署商務用 Skype Server 2015](../../deploy/deploy.md)。</span><span class="sxs-lookup"><span data-stu-id="391cd-152">For details about acquiring certificates, creating the SQL Server database, and creating file stores, see [Deploy Skype for Business Server 2015](../../deploy/deploy.md).</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="391cd-153">如需詳細資訊</span><span class="sxs-lookup"><span data-stu-id="391cd-153">For more information</span></span>

<span data-ttu-id="391cd-154">如需硬體和軟體需求的詳細資訊，請參閱下列主題：</span><span class="sxs-lookup"><span data-stu-id="391cd-154">For more information about hardware and software requirements, see the following topics:</span></span>
  
- [<span data-ttu-id="391cd-155">商務用 Skype Server 2015 的伺服器需求</span><span class="sxs-lookup"><span data-stu-id="391cd-155">Server requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
    
- [<span data-ttu-id="391cd-156">商務用 Skype Server 2015 的環境需求</span><span class="sxs-lookup"><span data-stu-id="391cd-156">Environmental requirements for Skype for Business Server 2015</span></span>](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)
